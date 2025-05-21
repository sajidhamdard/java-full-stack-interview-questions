## ✅ What You Already Know

When you annotate a method or class with:

```java
@Transactional
public void myMethod() {
    // some DB logic
}
```

…it works **without you writing any boilerplate** like opening/committing/rolling back transactions.

---

## 🤖 So How Does It Actually Work?

### 🔧 1. **Spring AOP Proxy Mechanism**

Spring **wraps your bean in a proxy** at runtime if it sees `@Transactional`.

There are 2 types of proxies:

* **JDK Dynamic Proxy** – if your class implements an interface
* **CGLIB Proxy** – if your class does not implement an interface

🔁 These proxies wrap your bean method calls and allow Spring to **inject extra logic**, like transaction handling, before/after your actual method runs.

---

### 🔍 2. **What Happens at Runtime?**

When you call a transactional method like:

```java
userService.createUser();
```

This is what happens behind the scenes:

1. **Proxy intercepts the call**
2. Checks for `@Transactional`
3. Delegates to **TransactionInterceptor**
4. TransactionInterceptor interacts with **PlatformTransactionManager**
5. The transaction manager (e.g., `DataSourceTransactionManager` for JDBC) does:

   * Starts transaction (get connection, set autocommit false)
   * Executes your method
   * Commits if success, rolls back if exception

---

### 🔄 Internally: Important Classes

| Component                    | Role                                                                           |
| ---------------------------- | ------------------------------------------------------------------------------ |
| `@Transactional`             | Metadata that marks a method for transaction                                   |
| `TransactionInterceptor`     | Core logic to handle begin, commit, rollback                                   |
| `PlatformTransactionManager` | SPI for managing transactions (like JDBC, JPA)                                 |
| `TransactionAttributeSource` | Parses the attributes from `@Transactional`                                    |
| `TransactionManager`         | Concrete class (e.g., `DataSourceTransactionManager`, `JpaTransactionManager`) |

---

### 📦 Typical Flow Internally (Simplified)

```
Caller --> Proxy --> TransactionInterceptor
         --> TransactionManager (begin)
         --> Actual Method Call
         --> TransactionManager (commit or rollback)
```

---

### 💡 Even Without @Transactional?

If you call `repository.save()` without `@Transactional`, JPA (Hibernate) **defers DB writing until flush time** — but:

* If you're **inside a Spring-managed method with no `@Transactional`**, the **default is non-transactional**.
* Some operations may still work because Hibernate can work with its **session-level transaction** (but it’s risky).
* **Best practice**: use `@Transactional` at the service layer.

---

### 🧪 Example

```java
@Service
public class UserService {

    @Transactional
    public void registerUser(User user) {
        userRepository.save(user); // triggers DB insert
        // any exception here will rollback the transaction
    }
}
```

Here, Spring:

* Starts transaction at method entry
* Commits at method exit (if no exception)
* Rolls back if runtime exception is thrown

---

### 📌 Common Pitfall (Important)

* If you call a `@Transactional` method **from within the same class**, the proxy is bypassed. So transaction will **not work** as expected.

```java
public void outerMethod() {
   innerTransactionalMethod(); // doesn't go through proxy, so @Transactional is ignored
}
```

---

## 🧠 Summary

| Concept                    | How It Works                                           |
| -------------------------- | ------------------------------------------------------ |
| Proxy                      | Spring creates a proxy to intercept method calls       |
| @Transactional             | Parsed by AOP and injected into proxy logic            |
| TransactionInterceptor     | Applies begin, commit, rollback logic                  |
| PlatformTransactionManager | Concrete logic for JDBC, JPA, etc.                     |
| No manual code             | You just use `@Transactional` and Spring does the rest |

---

## 🔄 Calling `@Transactional` from Within the Same Class — Why It Fails

### ❗ The Problem: **Proxy Bypass**

Spring handles transactions using **AOP proxies**. That means:

* Your bean is wrapped in a **proxy object**
* When an **external class** calls a method like `userService.saveUser()`, it goes **through the proxy**, which handles the transaction logic.

BUT...

If a method **within the same class** calls another `@Transactional` method, it’s a **direct call**, like `this.someTransactionalMethod()`, which **bypasses the proxy**. So the transaction logic is **never triggered**.

---

### ✅ Working (external call)

```java
@Service
public class UserService {
    
    @Transactional
    public void saveUser(User user) {
        userRepository.save(user);
    }
}
```

```java
// External call goes through proxy — transaction starts
userService.saveUser(user);
```

✔ Transaction works because Spring's proxy intercepts the method call.

---

### ❌ Not Working (internal call)

```java
@Service
public class UserService {

    public void registerUser(User user) {
        // calling transactional method inside same class
        saveUser(user); // ❌ proxy is bypassed
    }

    @Transactional
    public void saveUser(User user) {
        userRepository.save(user);
    }
}
```

⛔ Here, `registerUser()` calls `saveUser()` directly inside the same class. So the call doesn't go through the proxy, and `@Transactional` is **ignored**.

---

## 🔍 So When Does `@Transactional` Work?

| Call Type                  | Goes Through Proxy | Transaction Applies |
| -------------------------- | ------------------ | ------------------- |
| Called from another bean   | ✅ Yes              | ✅ Yes               |
| Called from same class     | ❌ No               | ❌ No                |
| Called via `this.method()` | ❌ No               | ❌ No                |

---

## 🔄 How to Fix This?

### ✅ Best Practice:

Put transactional methods in a **separate service class**, so they're always called through a proxy.

---

## 🔎 Now, About This Example

```java
public void save(User user) {
  userRepository.save(user);
}
```

You asked why this works **without** `@Transactional`.

### ☑ Yes, it “works”… but it’s **not transactional** in the Spring sense.

* When you call `repository.save()` (e.g., JPA), Hibernate will **queue the insert** in its persistence context.
* If no transaction exists, the **actual SQL** might:

  * Run in **auto-commit mode** (one statement = one transaction)
  * Or may be **deferred** until flush

But:

| With `@Transactional`          | Without `@Transactional`                      |
| ------------------------------ | --------------------------------------------- |
| All operations in one unit     | Each statement might run in auto-commit       |
| Rollback possible on exception | No rollback; partial updates may happen       |
| Safe for multiple operations   | Risky if multiple steps depend on one another |

---

### ⚠️ Why Is This Risky?

Without `@Transactional`, if you're:

* Saving multiple entities
* Modifying multiple tables
* Doing multiple operations that depend on each other

…then failure in one step will not rollback the others!

---

## ✅ Summary

| Concept                                                                | Explanation |
| ---------------------------------------------------------------------- | ----------- |
| Spring uses AOP proxies to handle `@Transactional`                     |             |
| Internal method calls bypass proxies — transactions don’t apply        |             |
| Without `@Transactional`, DB may auto-commit after each statement      |             |
| Always annotate service-layer methods with `@Transactional` for safety |             |
| Use separate service classes if needed to avoid internal call issue    |             |

---

## ✅ Why Read Methods Work Without `@Transactional`

### 🧠 By default:

* Most JPA providers (like Hibernate) can **run read queries without needing a transaction**.
* They **auto-open a session** and execute the query.

For example:

```java
User user = userRepository.findById(1L).orElseThrow();
```

This works **without `@Transactional`**, and it fetches data just fine.

---

## 🚨 When You Might Still Want `@Transactional(readOnly = true)`

Even though it's optional for reads, you **may want to** add:

```java
@Transactional(readOnly = true)
```

### Why?

1. **Performance Boost**

   * Tells Hibernate: "This is a read-only operation"
   * So it skips dirty checking, caching, etc.

2. **Consistency**

   * For databases that require transactions even for reads (like PostgreSQL with repeatable reads), it ensures consistent reads.

---

## ⚠️ Caution: Lazy-Loaded Relationships

If you fetch an entity and try to access a **lazy-loaded relation (e.g., `user.getRoles()`)** **outside of a transaction**, you'll get:

> `LazyInitializationException`

Because Hibernate needs a **transactional context** to load the relation.

So for complex reads involving lazy relations, wrap in:

```java
@Transactional(readOnly = true)
public User getUserWithRoles(Long id) {
    User user = userRepository.findById(id).orElseThrow();
    user.getRoles().size(); // triggers lazy load
    return user;
}
```

---

## ✅ Summary

| Operation                           | Needs `@Transactional`?           | Notes                                |
| ----------------------------------- | --------------------------------- | ------------------------------------ |
| `findById()`, `findAll()`           | ❌ No                              | Works fine without it                |
| Complex reads with lazy loading     | ✅ Recommended (`readOnly = true`) | Prevents LazyInitializationException |
| Write operations (`save`, `delete`) | ✅ Required                        | Ensures rollback & atomicity         |



---

### 🧾 **Spring Data + Transactions Cheat Sheet**

#### ✅ **Transaction Management**

| Scenario                             | Notes                                             |
| ------------------------------------ | ------------------------------------------------- |
| ✅ Simple Reads                       | No `@Transactional` needed                        |
| ✅ Writes/Deletes                     | Use `@Transactional` to ensure commit/rollback    |
| 🚫 Internal method call (same class) | Proxy bypassed → `@Transactional` won't work      |
| ✅ `@Transactional(readOnly = true)`  | Optimized for performance on reads                |
| ✅ Batch save                         | Use `@Transactional` to group all saves/rollbacks |

#### 🔍 **Repository Types**

| Interface                    | Use Case                                                          |
| ---------------------------- | ----------------------------------------------------------------- |
| `Repository`                 | Marker interface                                                  |
| `CrudRepository`             | Basic CRUD                                                        |
| `PagingAndSortingRepository` | CRUD + Pagination/Sorting                                         |
| `JpaRepository`              | Full JPA support + Specifications                                 |
| `MongoRepository`            | For MongoDB-specific ops                                          |
| `ListCrudRepository`         | Same as `CrudRepository` but returns `List` instead of `Iterable` |

#### 🏗️ **Custom Repository**

| Concept                 | Purpose                                         |
| ----------------------- | ----------------------------------------------- |
| `@NoRepositoryBean`     | Prevents base repo instantiation                |
| `@RepositoryDefinition` | Use if not extending any Spring Data interfaces |
| `SimpleJpaRepository`   | Default internal implementation behind proxies  |

#### 🧠 **EntityManager**

| Use Case                                                            |
| ------------------------------------------------------------------- |
| Fine-grained control over persistence context (flush, detach, etc.) |
| Custom complex queries                                              |
| Batch inserts/updates with manual transaction control               |

#### 🛠️ **Spring Data Magic**

| Feature                 | Example                                                 |
| ----------------------- | ------------------------------------------------------- |
| Derived query method    | `findByEmailAndStatus()`                                |
| Custom query            | `@Query("SELECT u FROM User u WHERE ...")`              |
| Proxy-based transaction | Created by Spring AOP for methods with `@Transactional` |

---

### ⚠️ Common Gotchas

* Lazy load outside transaction → `LazyInitializationException`
* Calling `@Transactional` method from same class → **no transaction**
* Avoid mixing transactional and non-transactional logic in same method

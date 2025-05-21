## 🔄 Difference between `save`, `persist`, and `merge`

| Method    | Defined In             | Behavior                                                                   |
| --------- | ---------------------- | -------------------------------------------------------------------------- |
| `persist` | JPA (`EntityManager`)  | Inserts a **new** entity. Throws error if the entity already exists.       |
| `merge`   | JPA (`EntityManager`)  | Updates an **existing** entity or saves a **detached** one.                |
| `save`    | Spring Data Repository | Decides internally: uses `persist()` if entity is new, otherwise `merge()` |

#### Example:

```java
User user = new User();
entityManager.persist(user); // inserts new user

User detachedUser = new User();
detachedUser.setId(1L);
entityManager.merge(detachedUser); // updates user with ID 1

userRepository.save(user); // spring calls persist or merge depending on state
```

---

### 🧠 How Spring Data JPA decides between `persist` and `merge`

Spring internally uses `entityManager.save(entity)`, and based on the entity’s state, it either:

* calls `persist(entity)` if entity is **new** (not yet saved)
* or calls `merge(entity)` if it's an **existing** entity (already persisted once)

---

### 🧩 But how does Spring know if the entity is new?

#### 1. **By default, it checks `@Version` or `@Id` field**:

* If there's a `@Version` field and it's `null`, it's a new entity.
* If there's no `@Version`, it checks the `@Id`:

  * If `@Id` is `null`, it's considered new.
  * If `@Id` has a value, it's considered **existing**, and `merge()` is used.

#### ❗ Caveat:

This fails when you **manually set the ID**, because Spring sees non-null ID and assumes it's an existing entity (even if it's not saved yet). This causes unwanted `merge()` instead of `persist()`.

---

### ✅ Solution: Use `Persistable<T>` Interface

You can tell Spring exactly **how to detect newness** by overriding `isNew()`.

```java
@MappedSuperclass
public abstract class AbstractEntity<ID> implements Persistable<ID> {

  @Transient
  private boolean isNew = true;

  @Override
  public boolean isNew() {
    return isNew;
  }

  @PostPersist
  @PostLoad
  void markNotNew() {
    this.isNew = false;
  }
}
```

* `@Transient isNew` → Not saved in DB.
* `isNew()` → Spring uses this to decide whether to persist or merge.
* `@PostPersist/@PostLoad` → After saving or loading, mark entity as not new.

---

### 🗂️ Summary Table – Entity State Detection

| Strategy               | Description                                                  |
| ---------------------- | ------------------------------------------------------------ |
| **@Version (default)** | If present and `null`, entity is new.                        |
| **@Id (default)**      | If `null`, it's new; if not `null`, it's existing.           |
| **Persistable<T>**     | Override `isNew()` to control detection manually.            |
| **EntityInformation**  | Advanced: customize Spring’s internal logic (rarely needed). |

---

### 🤔 Why does this matter?

* If Spring **thinks it's new**, it will use `persist()` and insert a new row.
* If Spring **thinks it’s existing**, it will use `merge()` and try to update — which could lead to unexpected inserts/updates or errors.

---

### 🧪 Example Scenario

```java
User user = new User();
user.setId(100L); // manually assigned ID

userRepository.save(user); 
// Without isNew() logic, Spring thinks this is an existing user and tries to update it
// But DB throws error if that ID does not exist!
```

✅ Fix it by overriding `isNew()` or using an `@GeneratedValue` ID.

---

## 📝 JPA Save vs Persist vs Merge

| Method      | Source                 | Behavior                                                        |
| ----------- | ---------------------- | --------------------------------------------------------------- |
| `persist()` | `EntityManager` (JPA)  | Inserts a **new** entity. Fails if entity already exists.       |
| `merge()`   | `EntityManager` (JPA)  | Updates an **existing** or **detached** entity.                 |
| `save()`    | Spring Data Repository | Internally uses `persist()` or `merge()` based on entity state. |

---

## 🧠 How Spring Decides New vs Existing

| Detection Strategy               | Description                                                          |
| -------------------------------- | -------------------------------------------------------------------- |
| `@Version` field (non-primitive) | If `null`, considered **new**.                                       |
| `@Id` field (default strategy)   | If `null`, considered **new**; if non-null, considered **existing**. |
| `Persistable<T>` interface       | Implement `isNew()` to explicitly control new/existing logic.        |
| `EntityInformation` (advanced)   | Customize Spring internals (rarely used).                            |

---

## ⚠️ Common Problem

* If you **manually set the ID**, Spring might think it's **existing** and call `merge()` (even if it’s not saved yet), which may cause DB constraint errors.

---

## ✅ Best Practice Fix

Use `Persistable<T>` with a flag:

```java
@MappedSuperclass
public abstract class BaseEntity<ID> implements Persistable<ID> {
  @Transient
  private boolean isNew = true;

  @Override
  public boolean isNew() {
    return isNew;
  }

  @PostPersist @PostLoad
  void markNotNew() {
    this.isNew = false;
  }
}
```

---

## 🔁 Behavior Summary

| Case                        | `save()` Calls       | Notes                              |
| --------------------------- | -------------------- | ---------------------------------- |
| New entity with null ID     | `persist()`          | Default strategy                   |
| Entity with manually set ID | `merge()`            | May fail if ID doesn’t exist in DB |
| With `Persistable<T>`       | Depends on `isNew()` | Full control over behavior         |
| Detached entity             | `merge()`            | Safe to reattach and update        |

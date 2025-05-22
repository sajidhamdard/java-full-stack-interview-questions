## 🚩 What is the N+1 Problem?

Imagine you want to load a list of `Users` and each `User` has a `Role`.

* You write a query to get **all users**: that’s **1 query**.
* But `role` is a **lazy-loaded** field, so for **each user**, JPA issues **another query** to get their role.

So:

* 1 query to get all users
* * N queries to get each user's role (where N = number of users)

➡️ **Total = N + 1 queries**

---

### ❗ Why is it a problem?

Because:

* If you have **10 users**, that’s 11 queries.
* If you have **1000 users**, that’s 1001 queries!

This can **slow down your application drastically** and cause **database overload**.

---

### 🧾 Example

#### Entity

```java
@Entity
public class User {
  @ManyToOne(fetch = FetchType.LAZY)
  private Role role;
}
```

#### Repository method

```java
List<User> findAll(); // Only fetches users, not roles
```

When you loop through users:

```java
for (User user : userRepo.findAll()) {
    System.out.println(user.getRole().getName()); // triggers 1 query per user
}
```

💥 BOOM — N+1 problem.

---

### ✅ How to solve it

You can **fetch everything in one query** using:

#### 1. `@EntityGraph`

```java
@EntityGraph(attributePaths = "role")
List<User> findAll();
```

#### 2. `JOIN FETCH` in `@Query`

```java
@Query("SELECT u FROM User u JOIN FETCH u.role")
List<User> findAllWithRoles();
```

---

### 🧠 Summary

| Term        | Meaning                                                             |
| ----------- | ------------------------------------------------------------------- |
| N+1 Problem | 1 query to fetch main entities, N more for relations                |
| Cause       | Lazy loading + iteration over relations                             |
| Fix         | Use `@EntityGraph` or `JOIN FETCH` to fetch everything in one query |

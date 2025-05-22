## ❓ What is `@EntityGraph`?

When you load an entity (like `User`, `Order`, etc.), related entities (like `roles`, `addresses`, etc.) are **not fetched immediately** if they are marked as `LAZY`. This can lead to:

* **N+1 select problem** (lots of tiny SQL queries),
* Or `LazyInitializationException` when accessing a lazy field outside the transaction.

`@EntityGraph` lets you tell JPA **exactly which relationships to fetch eagerly** in a specific query, **without changing your entity mappings**.

---

### 🧠 Think of it like:

“I want to fetch `User` along with their `roles`, but I don’t want to mark `roles` as EAGER in the entity itself. Just for this query, fetch it eagerly.”

---

### 🧾 Example

Suppose you have this:

```java
@Entity
public class User {
  @Id
  private Long id;

  private String name;

  @ManyToOne(fetch = FetchType.LAZY)
  private Role role;
}
```

Now let’s say you want to fetch the `User` **with its `Role`** eagerly in one query.

### ✅ Without `@EntityGraph`:

```java
@Query("select u from User u join fetch u.role where u.name = ?1")
User findByName(String name);
```

**Problem**: You must write custom JPQL, and it always fetches `role`.

---

### ✅ With `@EntityGraph`:

```java
@EntityGraph(attributePaths = "role")
User findByName(String name);
```

Much cleaner! This tells Spring Data JPA:

> When running this method, join fetch the `role` too.

---

### 🔁 Multiple attributes:

```java
@EntityGraph(attributePaths = {"role", "address", "company"})
User findByName(String name);
```

---

### 🔄 Use with `@Query` (optional):

```java
@Query("select u from User u where u.name = ?1")
@EntityGraph(attributePaths = "role")
User findByName(String name);
```

---

### 📝 Notes:

* You don’t need to change `LAZY` to `EAGER` in your entities.
* It helps avoid performance problems (like N+1 queries).
* You can even define **named entity graphs** in the entity class and refer to them.

---

### 📌 Summary

| Annotation       | Purpose                                         |
| ---------------- | ----------------------------------------------- |
| `@EntityGraph`   | Fetch specific relationships eagerly in a query |
| `attributePaths` | List of fields (relationships) to fetch eagerly |
| Works with       | Repository methods, `@Query`, or both           |

---

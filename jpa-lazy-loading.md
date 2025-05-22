## `fetch = FetchType.LAZY`:

This controls **when** the related data (`Role`) is loaded from the database.

There are two options:

#### 💤 `LAZY` (lazy loading)

* **Don’t load the `Role` data immediately** when you load a `User`.
* Only load it **when it is accessed** (i.e., when you call `user.getRole()`).

> This is the **default** for `@OneToMany`, but **not** for `@ManyToOne`.

#### ⚡ `EAGER` (eager loading)

* Load the `Role` **immediately** along with the `User`.

---

### 🧠 Why Use `LAZY`?

Because it:

* Avoids loading unnecessary data
* Saves memory and improves performance
* Makes queries faster when you don’t always need the related entity

---

### ⚠️ But Be Careful

Lazy loading can lead to the **N+1 problem** or **`LazyInitializationException`** if you're not careful.

#### Example of a LazyInitializationException:

```java
User user = userRepo.findById(1L); // role is not fetched yet
entityManager.close(); // session is closed

user.getRole().getName(); // ❌ Throws LazyInitializationException!
```

Because `role` is fetched **lazily**, and the session is already closed.

---

### ✅ Best Practice

Use `LAZY` by default, but:

* Use `JOIN FETCH` or `@EntityGraph` when you know you’ll need the related data
* Be mindful of when the session is open

---

### 🧾 Final Example

```java
@Entity
public class User {

    @ManyToOne(fetch = FetchType.LAZY)
    private Role role;
}
```

This means:

* A user has one role
* The role will only be fetched from DB **when needed**

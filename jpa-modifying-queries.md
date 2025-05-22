# Modifying Queries in Spring Data JPA — Simple Explanation

### What are Modifying Queries?

* Most queries you write **fetch data** (like `select`).
* **Modifying queries** are used to **change data** (like `update` or `delete`).

---

### How to Write a Modifying Query?

1. You use `@Query` to write a custom update or delete query.
2. You **must** add `@Modifying` annotation to tell Spring Data JPA that this query changes data (not just reads it).

**Example: Update firstname for users with a certain lastname**

```java
@Modifying
@Query("update User u set u.firstname = ?1 where u.lastname = ?2")
int setFixedFirstnameFor(String firstname, String lastname);
```

* This query updates all users with the given lastname and sets their firstname.
* Returns an `int` indicating how many rows were updated.

---

### Important Notes about @Modifying:

* When you run modifying queries, the **EntityManager cache** (which holds entities in memory) is **not cleared automatically**.
* This means if you still have loaded User entities in your current transaction, their state might be out of sync after the update.
* You can tell Spring to clear the cache automatically by:

```java
@Modifying(clearAutomatically = true)
```

---

### What About Delete Queries?

* You can write **derived delete methods** without writing a query explicitly:

```java
void deleteByRoleId(long roleId);
```

* Or write a bulk delete with a custom query:

```java
@Modifying
@Query("delete from User u where u.role.id = ?1")
void deleteInBulkByRoleId(long roleId);
```

---

### What’s the Difference Between These Delete Methods?

| Method                              | How it Works                                  | Lifecycle Callbacks Invoked? | Performance                                                          |
| ----------------------------------- | --------------------------------------------- | ---------------------------- | -------------------------------------------------------------------- |
| `deleteByRoleId(long roleId)`       | Finds users with the role, deletes one-by-one | Yes                          | Slower, uses more memory because it loads entities into memory first |
| `deleteInBulkByRoleId(long roleId)` | Runs a single delete query on the database    | No                           | Faster, less memory use, but no entity lifecycle events              |

* **Lifecycle callbacks** like `@PreRemove` are only called if entities are loaded and deleted one by one.
* Bulk deletes skip these callbacks.

---

### When to Use Which?

* Use **derived delete methods** if you want lifecycle callbacks and don’t mind loading entities.
* Use **bulk delete queries** (`@Modifying @Query`) when performance matters and you don’t need callbacks.

---

### Summary

* Use `@Modifying` **with** `@Query` to write update or delete queries.
* Add `clearAutomatically = true` if you want to clear EntityManager cache after update/delete.
* Derived delete methods load entities and delete individually (trigger callbacks).
* Bulk delete queries run a direct delete in the database (better performance, no callbacks).

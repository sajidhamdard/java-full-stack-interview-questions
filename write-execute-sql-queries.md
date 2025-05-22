# How to Create and Execute Queries in Spring Data JPA

## 1. Simple Queries: Using Method Names or @Query Annotation

### a. Query Methods by Naming Convention

* Spring Data JPA generates queries based on method names.
* Examples:

```java
List<User> findByLastname(String lastname);
User findFirstByOrderByAgeDesc();
List<User> findByAgeGreaterThan(int age);
```

* Simple to use, no query writing needed.
* Good for straightforward queries with standard conditions.

### b. Using the `@Query` Annotation for Custom JPQL/HQL

* When method naming is not enough, write JPQL (Java Persistence Query Language) directly.
* Example:

```java
@Query("select u from User u where u.lastname = :lastname and u.age > :age")
List<User> findUsersByLastnameAndAge(@Param("lastname") String lastname, @Param("age") int age);
```

* Supports JPQL and native SQL (with `nativeQuery = true`).

---

## 2. Complex Queries: When @Query Is Not Enough

### a. Custom Repository Implementation

* Create your own repository implementation when queries are too complex or dynamic.
* Allows you to:

  * Use the **EntityManager** directly.
  * Write JPQL/HQL, Criteria API, or native SQL.
  * Use **Spring’s JdbcTemplate** or third-party database tools.

#### How to implement:

1. Define a custom repository interface:

```java
public interface UserRepositoryCustom {
    List<User> findComplexQuery(...);
}
```

2. Implement the interface:

```java
public class UserRepositoryCustomImpl implements UserRepositoryCustom {

    @PersistenceContext
    private EntityManager entityManager;

    @Override
    public List<User> findComplexQuery(...) {
        // Use EntityManager to create and run query
        String hql = "select u from User u where ... complex condition ...";
        return entityManager.createQuery(hql, User.class).getResultList();
    }
}
```

3. Extend your repository with the custom interface:

```java
public interface UserRepository extends JpaRepository<User, Long>, UserRepositoryCustom {
}
```

---

### b. Using Criteria API (Type-safe Query Builder)

* For dynamic and complex queries with flexible conditions.
* Use `CriteriaBuilder` and `CriteriaQuery` to build queries programmatically.
* Example:

```java
CriteriaBuilder cb = entityManager.getCriteriaBuilder();
CriteriaQuery<User> query = cb.createQuery(User.class);
Root<User> user = query.from(User.class);
query.select(user)
     .where(cb.and(
          cb.equal(user.get("lastname"), lastname),
          cb.greaterThan(user.get("age"), age)
     ));
List<User> results = entityManager.createQuery(query).getResultList();
```

---

### c. Native SQL Queries

* Use native SQL if JPQL does not support your complex queries.
* Example:

```java
@Query(value = "SELECT * FROM users WHERE lastname = :lastname", nativeQuery = true)
List<User> findByLastnameNative(@Param("lastname") String lastname);
```

---

### d. Using Stored Procedures and Database Functions

* Put complex logic inside the database as stored procedures or functions.
* Invoke using `@StoredProcedure` or `@Query` with CALL.

Example:

```java
@Procedure(name = "calculate_age")
Integer calculateAge(@Param("birth_date") Date birthDate);
```

Or:

```java
@Query(value = "CALL calculate_age(:birthDate)", nativeQuery = true)
Integer callCalculateAge(@Param("birthDate") Date birthDate);
```

---

# Summary Cheat-Sheet

| Query Approach              | When to Use                       | How to Implement                                  | Pros                              | Cons                                  |
| --------------------------- | --------------------------------- | ------------------------------------------------- | --------------------------------- | ------------------------------------- |
| Method Name Queries         | Simple conditions                 | Define method names in repository                 | No SQL writing, fast to implement | Limited complexity                    |
| `@Query` Annotation         | Moderate complexity, custom JPQL  | Write JPQL or native SQL in annotation            | More control over query           | Hard to maintain complex queries      |
| Custom Repository Impl      | Complex, dynamic queries          | Write your own repository impl with EntityManager | Full control, supports any query  | More code, manual management          |
| Criteria API                | Dynamic query building            | Use CriteriaBuilder, CriteriaQuery                | Type-safe, dynamic                | Verbose and complex syntax            |
| Native SQL                  | Complex queries, unsupported JPQL | Use nativeQuery=true in @Query                    | Full SQL power                    | Database-dependent, less portable     |
| Stored Procedures/Functions | Complex logic in DB               | Use @Procedure or CALL via @Query                 | Offloads logic to DB, efficient   | Requires DB knowledge and maintenance |

---

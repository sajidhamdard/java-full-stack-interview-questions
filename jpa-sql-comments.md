## **Adding Comments to Queries in Spring Data JPA** 

---

### Why add comments to queries?

* When you debug performance issues or analyze slow queries in the database, the actual SQL sent by JPA/Hibernate might look very different from what you wrote.
* Adding **comments** in your queries helps you identify which part of your application generated which SQL in the database logs.
* It makes it easier to track and understand queries when looking at database logs or monitoring tools.

---

### How to add comments?

* Use the **`@Meta` annotation** on repository methods.
* The comment you add will be included in the SQL query sent to the database.

Example:

```java
public interface RoleRepository extends JpaRepository<Role, Integer> {

    @Meta(comment = "find roles by name")
    List<Role> findByName(String name);

    @Meta(comment = "count roles for a given name")
    long countByName(String name);
}
```

* This means when you run `findByName()`, the generated SQL will have a comment like `/* find roles by name */` visible in database logs.

---

### What operations support comments?

* Queries (select)
* Count operations
* Exists operations
* Some delete operations

Note: Some JPA operations like simple `entityManager.find()` do **not** support comments.

---

### Enabling comments in Hibernate

Hibernate doesn’t log comments by default. To activate it:

* In **Java config**:

```java
Properties properties = new Properties();
properties.setProperty("hibernate.use_sql_comments", "true");
```

* In **persistence.xml**:

```xml
<property name="hibernate.use_sql_comments" value="true" />
```

* In **Spring Boot application.properties**:

```
spring.jpa.properties.hibernate.use_sql_comments=true
```

---

### Enabling comments in EclipseLink

For EclipseLink, you enable SQL logging including comments by setting the logging level to `FINE`:

* In **Java config**:

```java
Properties properties = new Properties();
properties.setProperty("eclipselink.logging.level.sql", "FINE");
```

* In **persistence.xml**:

```xml
<property name="eclipselink.logging.level.sql" value="FINE" />
```

* In **Spring Boot application.properties**:

```
spring.jpa.properties.eclipselink.logging.level.sql=FINE
```

---

### Summary:

* Use `@Meta(comment = "your comment")` on repository methods to add comments to queries.
* Enable SQL comments in your JPA provider’s config for these comments to show up in your database logs.
* This helps you track and debug SQL queries easily in complex applications.

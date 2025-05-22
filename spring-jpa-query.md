## ✅ 1. **Defining Query Methods**

There are **two ways** to create queries in Spring Data repositories:

### 🔹 Way 1: **By method name**

You write a method like this:

```java
List<User> findByUsername(String username);
```

Spring will **automatically build the query** by reading the method name.

---

### 🔹 Way 2: **By manually defining the query**

You can write the query yourself using annotations:

```java
@Query("SELECT u FROM User u WHERE u.username = ?1")
User findByUsername(String username);
```

---

## ✅ 2. **Query Lookup Strategies**

This tells Spring how to decide **which type of query** to use (method name or manually written):

| Strategy                        | What it does                                                           |
| ------------------------------- | ---------------------------------------------------------------------- |
| `CREATE`                        | Builds the query from the method name.                                 |
| `USE_DECLARED_QUERY`            | Uses only a declared (manually written) query. If not found, it fails. |
| `CREATE_IF_NOT_FOUND` (default) | Tries declared query first. If not found, it builds from method name.  |

👉 You can configure this using XML or annotation:

```java
@EnableJpaRepositories(queryLookupStrategy = QueryLookupStrategy.Key.CREATE_IF_NOT_FOUND)
```

---

## ✅ 3. **Query Creation from Method Names**

Spring can **build SQL queries automatically** just from the method name. You can even do advanced things like:

### 🔹 Examples:

```java
// Match email AND last name
List<Person> findByEmailAddressAndLastname(EmailAddress email, String lastname);

// Make the result distinct
List<Person> findDistinctPeopleByLastnameOrFirstname(String lastname, String firstname);

// Case-insensitive search
List<Person> findByLastnameIgnoreCase(String lastname);

// Case-insensitive for all properties
List<Person> findByLastnameAndFirstnameAllIgnoreCase(String lastname, String firstname);

// Sort results by firstname (ascending)
List<Person> findByLastnameOrderByFirstnameAsc(String lastname);

// Sort results by firstname (descending)
List<Person> findByLastnameOrderByFirstnameDesc(String lastname);
```

---

## ✅ 4. **How Spring Parses These Method Names**

### Method = Subject + Predicate

In this method:

```java
List<Person> findByLastnameOrderByFirstnameAsc(String lastname);
```

* `findBy` → This is the **subject** (tells Spring it's a search).
* `LastnameOrderByFirstnameAsc` → This is the **predicate** (what criteria to search by and how to sort).

---

## ✅ 5. **What Can You Do in Method Names?**

* Use **`And` / `Or`** to combine multiple conditions
* Use **operators** like:

  * `Between`, `LessThan`, `GreaterThan`, `Like`, etc.
* Use **`IgnoreCase`** for case-insensitive matches
* Use **`OrderBy...Asc/Desc`** for sorting
* Use **`Top` / `First`** to limit results (e.g., `findTop3ByLastname`)

---

## ✅ 6. **Things to Remember**

* Not all features (like `IgnoreCase`) are supported in all databases.
* You can only use properties that exist on the entity.
* For dynamic sorting (based on user input), use `Sort` or `Pageable`.

---

### 🔒 **Reserved Method Names in Spring Data Repositories**

Some method names like `findById`, `deleteById`, etc., are **reserved by Spring Data** and automatically understood as working on the **entity's primary key** — not a field called `id`.

#### 🧠 Example:

```java
class User {
  @Id Long pk;  // Primary key
  Long id;      // Just a regular field
}
```

```java
interface UserRepository extends Repository<User, Long> {
  Optional<User> findById(Long id);       // Works on pk (primary key), not the 'id' field!
  Optional<User> findByPk(Long pk);       // Clearly works on pk
  Optional<User> findUserById(Long id);   // Works on the actual 'id' field
}
```

So if you have a field called `id` that is **not the primary key**, **avoid using `findById()`** — it will confuse things because Spring thinks you're asking for the **primary key**.

---

### 🏡 **Property Expressions and Nested Fields**

You can create queries on **nested properties** of your entity.

#### 🧠 Example:

```java
class Person {
  Address address;
}

class Address {
  ZipCode zipCode;
}
```

Then in your repository:

```java
List<Person> findByAddressZipCode(ZipCode zipCode);
```

✅ Spring will **parse this** as:
`person.address.zipCode`

It figures this out by **splitting camel case words** intelligently.

---

### 😵 **What If It Gets Confused?**

If you have properties like `addressZip`, Spring might wrongly think:

```java
findByAddressZipCode() --> addressZip.code (WRONG!)
```

To avoid this, you can **manually guide Spring** by adding **underscores** in the method name:

```java
List<Person> findByAddress_ZipCode(ZipCode zipCode);
```

✅ Now it will go:
`address → zipCode` (correct)

---

### 🔠 **Special Field Name Rules**

| Case                                      | Example                           | What to Do                      |
| ----------------------------------------- | --------------------------------- | ------------------------------- |
| Field name starts with `_`                | `_name`                           | Use `_name` in method name      |
| Nested path with `_`                      | `user._name`                      | Use `user__name` in method name |
| Field is ALL CAPS                         | `USER`                            | Use `USER` in method name       |
| Field like `qCode` (camelCase)            | `qCode`                           | Use `QCode` in method name      |
| Path ambiguity (e.g. `q.code` vs `qCode`) | `Container(String qCode, Code q)` | Use `Q_Code` to access `q.code` |

---

### ✅ Summary

| Concept           | Example                        | Meaning                                           |
| ----------------- | ------------------------------ | ------------------------------------------------- |
| Reserved Method   | `findById()`                   | Refers to **@Id field**, not a regular `id` field |
| Derived Query     | `findByLastnameAndFirstname()` | Built from method name                            |
| Nested Property   | `findByAddressZipCode()`       | Traverses object properties                       |
| Disambiguation    | `findByAddress_ZipCode()`      | Uses `_` to clarify path                          |
| Underscore Fields | `_name` or `user__name`        | Must keep `_` and use `__` for nested             |

---

### ✅ **Common Return Types for Repository Methods**

When a query returns multiple results, you can return:

| Return Type        | Description                                                           |
| ------------------ | --------------------------------------------------------------------- |
| `List<T>`          | Common, ordered, may contain duplicates                               |
| `Set<T>`           | Unordered, no duplicates                                              |
| `Iterable<T>`      | Most generic form, used when you just want iteration                  |
| `Streamable<T>`    | Advanced alternative to `Iterable` with extra stream-based operations |
| `Vavr Collections` | Functional alternatives like `io.vavr.collection.List`, `Set`, etc.   |

---

### 🔁 **Streamable<T> – Spring Data's Enhanced Iterable**

`Streamable<T>` adds features like:

* `stream()`, `map()`, `filter()`
* `and(...)` to combine multiple `Streamable`s

#### Example:

```java
interface PersonRepository extends Repository<Person, Long> {
  Streamable<Person> findByFirstnameContaining(String name);
  Streamable<Person> findByLastnameContaining(String name);
}
```

```java
Streamable<Person> result = repository.findByFirstnameContaining("av")
  .and(repository.findByLastnameContaining("ea"));
```

✅ You get **lazy, chainable** queries that you can further operate on.

---

### 📦 **Custom Streamable Wrapper Types**

You can return your **own wrapper** instead of just a list/stream, as long as:

1. Your type **implements `Streamable<T>`**
2. It has a constructor or static factory method like `of(...)` that accepts `Streamable<T>`

#### Example:

```java
@RequiredArgsConstructor(staticName = "of")
class Products implements Streamable<Product> {

  private final Streamable<Product> streamable;

  public MonetaryAmount getTotal() {
    return streamable.stream()
      .map(Product::getPrice)
      .reduce(Money.of(0), MonetaryAmount::add);
  }

  @Override
  public Iterator<Product> iterator() {
    return streamable.iterator();
  }
}
```

Now in the repository:

```java
interface ProductRepository extends Repository<Product, Long> {
  Products findAllByDescriptionContaining(String text);
}
```

✅ This lets you return rich API results like `products.getTotal()` instead of just raw data.

---

### 🧪 **Vavr Collection Support**

If you’re using **Vavr**, Spring Data supports its collections as return types.

#### Supported Return Types:

| Declared Return Type     | You Get (Based on Actual Data)                |
| ------------------------ | --------------------------------------------- |
| `io.vavr.collection.Seq` | Vavr `List` or `Vector`                       |
| `io.vavr.collection.Set` | Vavr `LinkedHashSet`                          |
| `io.vavr.collection.Map` | Vavr `LinkedHashMap`                          |
| `Traversable`            | Derived from the result (`List`, `Set`, etc.) |

#### Example:

```java
interface UserRepository extends Repository<User, Long> {
  io.vavr.collection.List<User> findByActiveTrue();
}
```

✅ Spring Data will internally convert the returned `List` to a Vavr `List`.

---

### ✨ Summary

| Feature                     | Benefit                                                      |
| --------------------------- | ------------------------------------------------------------ |
| `List`, `Set`, `Iterable`   | Standard return types for collections                        |
| `Streamable<T>`             | Adds stream support and composition (e.g., `.and()`)         |
| Custom `Streamable` wrapper | Add business logic directly in result                        |
| Vavr collections            | Functional collection support with immutability and chaining |

---

## 🔁 **Streaming Query Results**

### Return Type: `Stream<T>`

Allows **lazy loading** and **incremental processing** of results.

### Example:

```java
@Query("select u from User u")
Stream<User> findAllByCustomQueryAndStream();
```

### Usage:

Always **close the stream** to avoid memory/resource leaks:

```java
try (Stream<User> stream = repository.findAllByCustomQueryAndStream()) {
  stream.forEach(System.out::println);
}
```

> ❗ Not all Spring Data modules support streaming with `Stream<T>`.

---

## ⚡ **Asynchronous Query Results**

You can make repository queries **non-blocking** using `@Async`.

### Return types:

* `Future<T>`
* `CompletableFuture<T>` (preferred)

### Example:

```java
@Async
CompletableFuture<User> findOneByFirstname(String firstname);
```

> ⚠ Do not mix async queries with reactive repositories (WebFlux).

---

## 📄 **Pagination, Sorting, and Limiting**

Spring Data supports dynamic pagination and sorting using the following parameters:

| Parameter        | Purpose                           |
| ---------------- | --------------------------------- |
| `Pageable`       | Pagination and sorting            |
| `Sort`           | Only sorting                      |
| `Limit`          | Restrict number of results        |
| `ScrollPosition` | For windowed scrolling pagination |

### Example Usages:

```java
Page<User> findByLastname(String lastname, Pageable pageable);
Slice<User> findByLastname(String lastname, Pageable pageable);
List<User> findByLastname(String lastname, Sort sort);
List<User> findByLastname(String lastname, Sort sort, Limit limit);
```

### Special Considerations:

* `Pageable` already includes `Sort` and `Limit`, so avoid combining:

  * ❌ `findBy…(Pageable pageable, Sort sort)`
  * ❌ `findBy…(Pageable pageable, Limit limit)`
* ✅ You *can* use `Top` with `Pageable`.

---

## Which Method is Appropriate? — Summary Table

| **Method**          | **Amount of Data Fetched**                      | **Query Structure**                                | **Constraints / Notes**                                                                                                                           |
| ------------------- | ----------------------------------------------- | -------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| **`List<T>`**       | All results                                     | Single query                                       | - Can exhaust memory for large data sets<br>- Fetching all data may be slow                                                                       |
| **`Streamable<T>`** | All results                                     | Single query                                       | - Same as List — can exhaust memory and be slow                                                                                                   |
| **`Stream<T>`**     | Chunked (one-by-one or batches)                 | Single query, typically uses cursors               | - Must **close** the stream after use to avoid resource leaks                                                                                     |
| **`Flux<T>`**       | Chunked (one-by-one or batches)                 | Single reactive query with reactive infrastructure | - Requires reactive store support                                                                                                                 |
| **`Slice<T>`**      | `Pageable.getPageSize() + 1`                    | One or many queries using offset and limit         | - Navigates only to the **next** slice<br>- Indicates if more data exists<br>- Offset queries inefficient with large offsets                      |
| **`Window<T>`**     | `limit + 1` at offset or keyset scroll position | One or many queries using offset or keyset         | - Navigates only to the **next** window<br>- Keyset-based is more efficient but requires indexed columns and no nulls in keys                     |
| **`Page<T>`**       | `Pageable.getPageSize()`                        | One or many queries with offset and limit          | - Triggers an additional `COUNT(*)` query to find total elements, which can be costly<br>- Offset-based queries get inefficient for large offsets |

---

## Detailed Explanation

### 1. **Fetching All Results: `List<T>` and `Streamable<T>`**

* Best for **small to medium** datasets.
* Fetches **all rows** in one go.
* Can **consume a lot of memory** and be slow if the dataset is large.

### 2. **Streaming Results: `Stream<T>` and `Flux<T>`**

* Results are fetched **incrementally**, often by using a **cursor**.
* **`Stream<T>`** is a Java 8 stream that must be **closed** to avoid leaking resources.
* **`Flux<T>`** is reactive (part of Reactor) and requires the data store to support reactive queries.
* Ideal for **large result sets** where you want to process data lazily.

### 3. **Pagination: `Slice<T>` and `Page<T>`**

* Use `Pageable` parameter to limit and offset results.
* **`Slice<T>`**: Efficient pagination when you only want to know if there are more results (next slice). No expensive count query.
* **`Page<T>`**: Gives total number of pages and elements by issuing a **count query**, which can be costly.
* Both are **offset-based**, and offset queries are inefficient for large offsets since the database must skip rows.

### 4. **Windowed Queries: `Window<T>` (Offset or Keyset)**

* Similar to `Slice`, but supports **windowed scrolling** with state maintained by `ScrollPosition`.
* Can be **offset-based** or **keyset-based**.
* **Keyset-based** is more efficient for large datasets but requires:

  * Proper indexes on sorting keys.
  * No null values in key columns.
  * Projection of all sorting keys in the result.

---

## How to Choose?

| Scenario                                                   | Recommended Return Type                 |
| ---------------------------------------------------------- | --------------------------------------- |
| Small datasets, all results needed                         | `List<T>` or `Streamable<T>`            |
| Large datasets, want to process results lazily             | `Stream<T>` or `Flux<T>`                |
| Need simple pagination with info if more exists            | `Slice<T>`                              |
| Need full pagination with total count                      | `Page<T>`                               |
| Large datasets, efficient scrolling without offset penalty | `Window<T>` with keyset-based scrolling |

---

## Bonus: **Sorting**

You can specify sorting in queries with:

### Simple property-based sorting:

```java
Sort sort = Sort.by("firstname").ascending()
  .and(Sort.by("lastname").descending());
```

### Type-safe sorting using method references:

```java
TypedSort<Person> person = Sort.sort(Person.class);

Sort sort = person.by(Person::getFirstname).ascending()
  .and(person.by(Person::getLastname).descending());
```

### Querydsl-based sorting (if supported by your store):

```java
QSort sort = QSort.by(QPerson.firstname.asc())
  .and(QSort.by(QPerson.lastname.desc()));
```

---

## How to Limit Query Results

### 1. Using **Limit** parameter:

* Pass a `Limit` argument dynamically to restrict the number of results.

```java
List<User> findByLastname(String lastname, Limit limit);
```

### 2. Using **First** or **Top** keywords:

* Use `First` or `Top` keywords in method names to limit results.
* Numeric value can be appended to specify max results (default is 1 if omitted).

Examples:

```java
User findFirstByOrderByLastnameAsc();               // returns 1 result (smallest lastname)
User findTopByLastnameOrderByAgeDesc(String lastname);  // returns 1 result with max age for lastname
List<User> findFirst10ByLastname(String lastname, Sort sort);  // returns first 10 sorted by Sort
List<User> findTop10ByLastname(String lastname, Pageable pageable); // returns top 10 with paging
Slice<User> findTop3By(Pageable pageable);           // top 3 with paging slice
Page<User> queryFirst10ByLastname(String lastname, Pageable pageable); // page with first 10 results
```

---

## Important Notes:

* **`First` and `Top`** are interchangeable but **cannot be mixed with `Limit`** parameter in the same method.
* You can combine **limiting** with **sorting** via `Sort` or `Pageable` parameters to fetch top or first K elements based on order.
* You can combine limiting with **distinct** if supported by your datastore.
* When applying pagination or slicing on a limiting query, the limit is applied **before** pagination (e.g., pages are within the limited subset).
* For queries returning a single result, you can wrap it in `Optional<T>` for safety:

```java
Optional<User> findFirstByLastname(String lastname);
```

---

### Summary Table:

| Usage                      | Example Method Signature                                                 | Returns              | Notes                       |
| -------------------------- | ------------------------------------------------------------------------ | -------------------- | --------------------------- |
| Limit param                | `List<User> findByLastname(String lastname, Limit limit);`               | Limited list         | Dynamic limit               |
| First or Top (default 1)   | `User findFirstByOrderByLastnameAsc();`                                  | Single User          | Returns 1 result            |
| First or Top with number   | `List<User> findFirst10ByLastname(String lastname, Sort sort);`          | List of limited size | Limited list with sorting   |
| First or Top with Pageable | `Page<User> queryFirst10ByLastname(String lastname, Pageable pageable);` | Page                 | Pageable + limit            |
| Slice with Top             | `Slice<User> findTop3By(Pageable pageable);`                             | Slice                | Pagination slice with limit |

---

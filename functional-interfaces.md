Below are simple examples of how Java's built-in functional interfaces (from `java.util.function` package) can be used with lambda expressions.

---

### 1. **Consumer<T>**

Takes one argument and returns nothing.

```java
import java.util.function.Consumer;

public class Test {
    public static void main(String[] args) {
        Consumer<String> consumer = (s) -> System.out.println("Hello " + s);
        consumer.accept("World");
    }
}
```

---

### 2. **Supplier<T>**

Takes no arguments and returns a value.

```java
import java.util.function.Supplier;

public class Test {
    public static void main(String[] args) {
        Supplier<String> supplier = () -> "Java is fun!";
        System.out.println(supplier.get());
    }
}
```

---

### 3. **Function\<T, R>**

Takes one argument and returns a result.

```java
import java.util.function.Function;

public class Test {
    public static void main(String[] args) {
        Function<Integer, String> function = (x) -> "Result: " + (x * 2);
        System.out.println(function.apply(5));
    }
}
```

---

### 4. **Predicate<T>**

Takes one argument and returns a boolean.

```java
import java.util.function.Predicate;

public class Test {
    public static void main(String[] args) {
        Predicate<Integer> isEven = (x) -> x % 2 == 0;
        System.out.println(isEven.test(4)); // true
        System.out.println(isEven.test(5)); // false
    }
}
```

---

### 5. **BiFunction\<T, U, R>**

Takes two arguments and returns a result.

```java
import java.util.function.BiFunction;

public class Test {
    public static void main(String[] args) {
        BiFunction<Integer, Integer, Integer> add = (a, b) -> a + b;
        System.out.println(add.apply(3, 4)); // 7
    }
}
```

---

### 6. **BiConsumer\<T, U>**

Takes two arguments and returns nothing.

```java
import java.util.function.BiConsumer;

public class Test {
    public static void main(String[] args) {
        BiConsumer<String, Integer> printer = (name, age) -> System.out.println(name + " is " + age + " years old");
        printer.accept("Alice", 30);
    }
}
```

---

### 7. **UnaryOperator<T>**

A specialization of `Function<T, T>` — takes one argument and returns a result of the same type.

```java
import java.util.function.UnaryOperator;

public class Test {
    public static void main(String[] args) {
        UnaryOperator<Integer> square = (x) -> x * x;
        System.out.println(square.apply(6)); // 36
    }
}
```

---

### 8. **BinaryOperator<T>**

A specialization of `BiFunction<T, T, T>` — takes two arguments of the same type and returns one of the same type.

```java
import java.util.function.BinaryOperator;

public class Test {
    public static void main(String[] args) {
        BinaryOperator<Integer> multiply = (a, b) -> a * b;
        System.out.println(multiply.apply(3, 7)); // 21
    }
}
```

---

Here’s a summary table of the most commonly used Java built-in functional interfaces from the `java.util.function` package with their descriptions, method names, and sample usage:

---

### ✅ **Java Functional Interfaces Summary Table**

| Interface                | Input(s) | Return Type | Method Name    | Example Expression                    |
| ------------------------ | -------- | ----------- | -------------- | ------------------------------------- |
| **Consumer<T>**          | T        | void        | `accept(T)`    | `x -> System.out.println(x)`          |
| **Supplier<T>**          | none     | T           | `get()`        | `() -> "Hello"`                       |
| **Function\<T, R>**      | T        | R           | `apply(T)`     | `x -> x + 10`                         |
| **Predicate<T>**         | T        | boolean     | `test(T)`      | `x -> x % 2 == 0`                     |
| **BiConsumer\<T, U>**    | T, U     | void        | `accept(T, U)` | `(x, y) -> System.out.println(x + y)` |
| **BiFunction\<T, U, R>** | T, U     | R           | `apply(T, U)`  | `(x, y) -> x + y`                     |
| **UnaryOperator<T>**     | T        | T           | `apply(T)`     | `x -> x * x`                          |
| **BinaryOperator<T>**    | T, T     | T           | `apply(T, T)`  | `(x, y) -> x + y`                     |

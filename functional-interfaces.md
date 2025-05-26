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

---

Below are **1–2 practical examples** of each major functional interface being used with **Java Streams**.

---

## 🔁 1. **Predicate<T>** – Used for filtering elements

```java
import java.util.List;
import java.util.stream.Collectors;
import java.util.function.Predicate;

public class Test {
    public static void main(String[] args) {
        List<Integer> numbers = List.of(1, 2, 3, 4, 5, 6);

        Predicate<Integer> isEven = x -> x % 2 == 0;

        List<Integer> evens = numbers.stream()
                                     .filter(isEven) // filter using Predicate
                                     .collect(Collectors.toList());

        System.out.println(evens); // [2, 4, 6]
    }
}
```

---

## 🎯 2. **Function\<T, R>** – Used for mapping (transformation)

```java
import java.util.List;
import java.util.stream.Collectors;
import java.util.function.Function;

public class Test {
    public static void main(String[] args) {
        List<String> names = List.of("alice", "bob");

        Function<String, String> toUpper = name -> name.toUpperCase();

        List<String> upperNames = names.stream()
                                       .map(toUpper) // map using Function
                                       .collect(Collectors.toList());

        System.out.println(upperNames); // [ALICE, BOB]
    }
}
```

---

## ✅ 3. **Consumer<T>** – Used with `forEach` to perform an action on each element

```java
import java.util.List;
import java.util.function.Consumer;

public class Test {
    public static void main(String[] args) {
        List<String> list = List.of("Java", "Python", "C++");

        Consumer<String> printer = x -> System.out.println("Language: " + x);

        list.stream().forEach(printer); // forEach using Consumer
    }
}
```

---

## 🛠 4. **Supplier<T>** – Typically not used *inside* stream pipelines, but useful *outside* to supply data

```java
import java.util.function.Supplier;
import java.util.stream.Stream;

public class Test {
    public static void main(String[] args) {
        Supplier<Double> randomSupplier = () -> Math.random();

        Stream.generate(randomSupplier) // generates infinite stream
              .limit(5)
              .forEach(System.out::println); // prints 5 random numbers
    }
}
```

---

## 🧪 5. **BiFunction\<T, U, R>** – Combine two inputs to produce an output (used via `.map()` or custom collectors)

```java
import java.util.function.BiFunction;

public class Test {
    public static void main(String[] args) {
        BiFunction<String, Integer, String> repeater = (str, times) -> str.repeat(times);

        System.out.println(repeater.apply("Hi ", 3)); // Hi Hi Hi 
    }
}
```

Usage in stream:

```java
import java.util.List;
import java.util.function.BiFunction;
import java.util.stream.IntStream;

public class Test {
    public static void main(String[] args) {
        List<String> words = List.of("Hi", "Bye");
        BiFunction<String, Integer, String> repeater = (s, count) -> s.repeat(count);

        IntStream.range(0, words.size())
                 .mapToObj(i -> repeater.apply(words.get(i), i + 1))
                 .forEach(System.out::println);
        // Hi
        // ByeBye
    }
}
```

---

## 💬 6. **BiConsumer\<T, U>** – Often used in `Map.forEach` or custom processing

```java
import java.util.Map;
import java.util.function.BiConsumer;

public class Test {
    public static void main(String[] args) {
        Map<String, Integer> map = Map.of("apple", 2, "banana", 3);

        BiConsumer<String, Integer> printer = (k, v) -> System.out.println(k + " -> " + v);

        map.forEach(printer); // BiConsumer with Map
    }
}
```

---

## 🔁 7. **UnaryOperator<T>** – Used in `map` when type doesn't change

```java
import java.util.List;
import java.util.function.UnaryOperator;
import java.util.stream.Collectors;

public class Test {
    public static void main(String[] args) {
        List<Integer> list = List.of(1, 2, 3);

        UnaryOperator<Integer> square = x -> x * x;

        List<Integer> squared = list.stream()
                                    .map(square) // same input and output type
                                    .collect(Collectors.toList());

        System.out.println(squared); // [1, 4, 9]
    }
}
```

---

## ➗ 8. **BinaryOperator<T>** – Used in `reduce()` to accumulate results

```java
import java.util.List;
import java.util.function.BinaryOperator;

public class Test {
    public static void main(String[] args) {
        List<Integer> nums = List.of(1, 2, 3, 4);

        BinaryOperator<Integer> sum = (a, b) -> a + b;

        int total = nums.stream().reduce(0, sum); // reduce using BinaryOperator

        System.out.println(total); // 10
    }
}
```

---

### ✅ Summary:

| Interface           | Common Stream Use                 |
| ------------------- | --------------------------------- |
| `Predicate<T>`      | `.filter()`                       |
| `Function<T, R>`    | `.map()`                          |
| `Consumer<T>`       | `.forEach()`                      |
| `Supplier<T>`       | `Stream.generate()`               |
| `BiFunction<T,U,R>` | custom `.map()` or `.reduce()`    |
| `BiConsumer<T,U>`   | `Map.forEach()`                   |
| `UnaryOperator<T>`  | `.map()` for same-type conversion |
| `BinaryOperator<T>` | `.reduce()`                       |

---

## ✅ **What is a `Supplier<T>`?**

* It represents a function that **takes no input** and **returns a value** of type `T`.
* Method: `T get()`
* Use case: When you want to **supply or generate values** on-demand (e.g., default values, random numbers, UUIDs, timestamps, etc.)

---

## 💡 Example: Generating Random OTPs using `Supplier<String>`

```java
import java.util.function.Supplier;
import java.util.Random;
import java.util.stream.Stream;

public class SupplierExample {
    public static void main(String[] args) {
        Supplier<String> otpSupplier = () -> {
            Random random = new Random();
            StringBuilder otp = new StringBuilder();
            for (int i = 0; i < 6; i++) {
                otp.append(random.nextInt(10)); // digit 0–9
            }
            return otp.toString();
        };

        // Generate 5 OTPs using Stream.generate + Supplier
        Stream.generate(otpSupplier)
              .limit(5)
              .forEach(System.out::println);
    }
}
```

---

### 📝 Output Example:

```
483920
129457
504612
877324
032185
```

Each time you run the program, it will generate 5 random 6-digit OTPs.

---

## 🔁 Use Cases of Supplier:

| Use Case                     | Example Output               |
| ---------------------------- | ---------------------------- |
| Generate random values       | Random number, OTP, UUID     |
| Provide default values       | Empty list, "N/A", 0         |
| Lazy initialization          | Only compute if needed       |
| Timestamp generation         | `Instant.now()`              |
| Resource loading (on-demand) | Read file/config when needed |

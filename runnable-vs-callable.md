In Java, both `Runnable` and `Callable` are interfaces used to define tasks that can be executed by multiple threads (usually via an `ExecutorService`). However, there are **key differences** between the two in terms of return value, exception handling, and usage.

---

## 🧵 1. **Runnable Interface**

### 🔹 Introduced in: Java 1.0

### 🔹 Package: `java.lang`

### ✅ Key Features:

* Does **not return** any result.
* Cannot throw a **checked exception**.
* Suitable for simple background tasks.

### 🔧 Syntax:

```java
Runnable task = () -> {
    System.out.println("Running a task");
};
```

### 🔁 Execution with Thread:

```java
Thread thread = new Thread(task);
thread.start();
```

### 🔁 Execution with ExecutorService:

```java
ExecutorService executor = Executors.newFixedThreadPool(1);
executor.submit(task);  // Returns a Future<?> but always null after completion
executor.shutdown();
```

---

## 📞 2. **Callable Interface**

### 🔹 Introduced in: Java 5 (with `java.util.concurrent`)

### 🔹 Package: `java.util.concurrent`

### ✅ Key Features:

* **Returns a result** (`V` generic type).
* Can throw **checked exceptions**.
* Useful when the task needs to return a value or may fail.

### 🔧 Syntax:

```java
Callable<Integer> task = () -> {
    return 123;
};
```

### 🔁 Execution with ExecutorService:

```java
ExecutorService executor = Executors.newFixedThreadPool(1);
Future<Integer> future = executor.submit(task); // Callable returns Future<T>

Integer result = future.get(); // Blocks until result is available
System.out.println("Result: " + result);
executor.shutdown();
```

---

## 🔍 Key Differences

| Feature               | `Runnable`                        | `Callable<V>`                             |
| --------------------- | --------------------------------- | ----------------------------------------- |
| **Returns a value**   | No                                | Yes (`V`)                                 |
| **Throws exceptions** | Only unchecked exceptions         | Can throw **checked exceptions**          |
| **Method**            | `void run()`                      | `V call()`                                |
| **Used with**         | `Thread`, `ExecutorService`       | `ExecutorService`                         |
| **Returns `Future`**  | Yes (but always `null` in result) | Yes (result available via `Future.get()`) |

---

## ✅ When to Use What?

| Use Case                               | Use `Runnable` | Use `Callable` |
| -------------------------------------- | -------------- | -------------- |
| Simple task without a return value     | ✅              |                |
| Task that needs to return a result     |                | ✅              |
| Task that can throw checked exceptions |                | ✅              |

---

## 🧪 Example: Runnable vs Callable

### ➤ Runnable Example:

```java
Runnable printTask = () -> System.out.println("Hello from Runnable");
new Thread(printTask).start();
```

### ➤ Callable Example:

```java
Callable<String> messageTask = () -> {
    Thread.sleep(1000);
    return "Hello from Callable";
};

ExecutorService executor = Executors.newSingleThreadExecutor();
Future<String> future = executor.submit(messageTask);
System.out.println(future.get()); // Output: Hello from Callable
executor.shutdown();
```


### ✅ **Exception Handling with `Callable` in Java**

One of the key benefits of `Callable` over `Runnable` is that **`Callable.call()` can throw checked exceptions**, which allows for more robust error handling when submitting tasks to an `ExecutorService`.

---

## 🔧 Basic Syntax Recap:

```java
Callable<T> task = () -> {
    // Code that may throw an exception
    return result;
};
```

You use `ExecutorService.submit(task)` which returns a `Future<T>`. To handle exceptions, you call `future.get()` inside a try-catch block.

---

## 💥 Example: Callable with Exception Handling

```java
import java.util.concurrent.*;

public class CallableExceptionExample {
    public static void main(String[] args) {
        ExecutorService executor = Executors.newSingleThreadExecutor();

        Callable<Integer> task = () -> {
            System.out.println("Task started");
            if (true) {
                throw new Exception("Something went wrong!");
            }
            return 42;
        };

        Future<Integer> future = executor.submit(task);

        try {
            // This will throw ExecutionException if the task throws an exception
            Integer result = future.get();  
            System.out.println("Result: " + result);
        } catch (ExecutionException e) {
            // Extract the actual exception thrown from the task
            Throwable cause = e.getCause();
            System.err.println("Task threw an exception: " + cause.getMessage());
        } catch (InterruptedException e) {
            System.err.println("Thread was interrupted while waiting for result");
        } finally {
            executor.shutdown();
        }
    }
}
```

---

## 🔍 Output:

```
Task started
Task threw an exception: Something went wrong!
```

---

## 📝 Notes:

* `Callable.call()` can throw any exception.
* If an exception occurs, it is wrapped inside an `ExecutionException` which is thrown when you call `future.get()`.
* You must extract the root cause using `e.getCause()`.

---

## 💡 Best Practices:

* Always wrap `future.get()` in `try-catch`.
* Use `invokeAll()` if you want to submit a batch of tasks and collect exceptions from each.
* Be cautious of blocking behavior: `future.get()` is blocking.

  Here’s a **short and clear example** showing how to use:

1. ✅ `invokeAll()` with multiple `Callable` tasks.
2. ⏰ `Future.get(timeout, TimeUnit)` to avoid indefinite blocking.

---

## 🔧 Example: `invokeAll()` + `get(timeout)`

```java
import java.util.concurrent.*;
import java.util.*;

public class InvokeAllExample {
    public static void main(String[] args) throws InterruptedException {
        ExecutorService executor = Executors.newFixedThreadPool(3);

        List<Callable<String>> tasks = Arrays.asList(
            () -> {
                Thread.sleep(1000);
                return "Task 1";
            },
            () -> {
                Thread.sleep(2000);
                return "Task 2";
            },
            () -> {
                Thread.sleep(3000);
                return "Task 3";
            }
        );

        // invokeAll waits for all tasks to complete
        List<Future<String>> results = executor.invokeAll(tasks);

        for (Future<String> future : results) {
            try {
                // Wait up to 2 seconds for each result
                String result = future.get(2, TimeUnit.SECONDS);
                System.out.println("Result: " + result);
            } catch (TimeoutException e) {
                System.err.println("Task timed out!");
            } catch (ExecutionException e) {
                System.err.println("Task failed: " + e.getCause().getMessage());
            }
        }

        executor.shutdown();
    }
}
```

---

## 🧾 Output:

```
Result: Task 1
Result: Task 2
Task timed out!
```

(Task 3 takes 3 seconds, but `get(2, TimeUnit.SECONDS)` times out.)

---

### here's a **complete example** that shows:

✅ `invokeAll()` with multiple `Callable` tasks
✅ `future.get(timeout, TimeUnit)` to avoid waiting too long
✅ `future.cancel(true)` for cancellation
✅ Handling of **partial failures** (some tasks fail or timeout)

---

## 🔧 Java Example: `invokeAll`, Timeout, Cancellation, Partial Failure

```java
import java.util.concurrent.*;
import java.util.*;

public class MixedCallableExample {
    public static void main(String[] args) throws InterruptedException {
        ExecutorService executor = Executors.newFixedThreadPool(3);

        List<Callable<String>> tasks = Arrays.asList(
            () -> {
                Thread.sleep(1000);
                return "✅ Task 1 done";
            },
            () -> {
                Thread.sleep(4000);  // Will timeout
                return "✅ Task 2 done";
            },
            () -> {
                throw new RuntimeException("❌ Task 3 failed");
            }
        );

        List<Future<String>> futures = executor.invokeAll(tasks);

        for (int i = 0; i < futures.size(); i++) {
            Future<String> future = futures.get(i);
            try {
                // Wait max 2 seconds for each task
                String result = future.get(2, TimeUnit.SECONDS);
                System.out.println("Result " + (i + 1) + ": " + result);
            } catch (TimeoutException e) {
                System.err.println("⚠️ Task " + (i + 1) + " timed out. Cancelling...");
                future.cancel(true); // Cancel the task if it's still running
            } catch (ExecutionException e) {
                System.err.println("❌ Task " + (i + 1) + " failed: " + e.getCause().getMessage());
            }
        }

        executor.shutdown();
    }
}
```

---

## 🧾 Example Output:

```
Result 1: ✅ Task 1 done
⚠️ Task 2 timed out. Cancelling...
❌ Task 3 failed: ❌ Task 3 failed
```

---

## ✅ What This Covers:

| Feature                              | Covered |
| ------------------------------------ | ------- |
| `invokeAll()` with `Callable`s       | ✅       |
| Timeout with `get()`                 | ✅       |
| Task cancellation                    | ✅       |
| Checked & runtime exception handling | ✅       |
| Partial success/failure handling     | ✅       |

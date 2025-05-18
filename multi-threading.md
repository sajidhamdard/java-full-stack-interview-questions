## **Introduction to Multithreading in Java**.

---

### **1. What is a Thread?**

A **thread** is a lightweight, independent path of execution within a process. A **Java application runs by default in a single thread**, known as the **main thread**. You can create multiple threads to perform tasks concurrently, improving efficiency especially for tasks like I/O operations, background processing, etc.

---

### **2. Process vs Thread**

| Feature       | Process              | Thread                           |
| ------------- | -------------------- | -------------------------------- |
| Memory        | Separate memory      | Shared memory with other threads |
| Communication | Complex (IPC needed) | Easy (shared objects)            |
| Overhead      | High                 | Low                              |
| Creation      | Slow                 | Fast                             |

---

### **3. Benefits of Multithreading**

* **Improved application performance** by utilizing CPU cores efficiently.
* **Non-blocking user interface**, especially in GUI apps.
* **Better resource utilization** by performing I/O and CPU tasks concurrently.
* **Simplified modeling** for some real-world problems like Producer-Consumer.

---

### **4. Thread Lifecycle**

A thread in Java goes through the following **states**:

1. **New** – Thread is created but not started.
2. **Runnable** – Thread is ready to run, waiting for CPU.
3. **Running** – Thread is currently executing.
4. **Blocked/Waiting** – Thread is paused, waiting for resources or signals.
5. **Timed Waiting** – Thread is sleeping or waiting with a timeout.
6. **Terminated** – Thread has completed execution or was stopped.

Java provides the `Thread.State` enum to inspect a thread's current state.

---

## **2. Creating Threads in Java**

Java provides **three primary ways** to create threads:

---

### **A. Extending the `Thread` Class**

```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread running: " + Thread.currentThread().getName());
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        t1.start(); // starts a new thread
    }
}
```

* `run()` contains the code that will execute in the new thread.
* `start()` actually starts the new thread and internally calls `run()`.

---

### **B. Implementing the `Runnable` Interface**

```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Runnable thread: " + Thread.currentThread().getName());
    }
}

public class Main {
    public static void main(String[] args) {
        Thread t1 = new Thread(new MyRunnable());
        t1.start();
    }
}
```

* This is preferred over extending `Thread` because it allows extending another class.
* Promotes better separation of task and thread management.

---

### **C. Using `ExecutorService` and `Callable`**

`ExecutorService` is part of the `java.util.concurrent` package and allows better thread management.

```java
import java.util.concurrent.*;

public class Main {
    public static void main(String[] args) throws Exception {
        ExecutorService executor = Executors.newSingleThreadExecutor();

        Callable<String> task = () -> {
            return "Task executed in: " + Thread.currentThread().getName();
        };

        Future<String> result = executor.submit(task);
        System.out.println(result.get()); // blocks and waits for result

        executor.shutdown();
    }
}
```

* `Callable` can return a result and throw exceptions.
* `Future` is used to retrieve the result asynchronously.

---

### Summary

| Method                     | Can Return Result | Allows Exception | Flexibility |
| -------------------------- | ----------------- | ---------------- | ----------- |
| Extends `Thread`           | No                | No               | Low         |
| Implements `Runnable`      | No                | No               | Medium      |
| Uses `Callable` + Executor | Yes               | Yes              | High        |

---

### **Java Example: ExecutorService with Thread Pool**

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

class Task implements Runnable {
    private int taskId;

    public Task(int taskId) {
        this.taskId = taskId;
    }

    @Override
    public void run() {
        System.out.println("Task " + taskId + " is running on thread: " + Thread.currentThread().getName());
        try {
            Thread.sleep(1000); // Simulate time-consuming task
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        System.out.println("Task " + taskId + " completed");
    }
}

public class Main {
    public static void main(String[] args) {
        // Create a fixed thread pool of size 3
        ExecutorService executor = Executors.newFixedThreadPool(3);

        // Submit 5 tasks to the executor
        for (int i = 1; i <= 5; i++) {
            Task task = new Task(i);
            executor.submit(task);
        }

        // Shutdown the executor (no new tasks will be accepted)
        executor.shutdown();
    }
}
```

---

### **Explanation**

* **Fixed thread pool of 3**: Only 3 threads run concurrently. The rest wait in a queue.
* **5 tasks** submitted: Tasks will be picked up by available threads.
* `submit()` adds the task to the pool.
* `shutdown()` gracefully stops accepting new tasks.

---

### **Sample Output (thread names may vary):**

```
Task 1 is running on thread: pool-1-thread-1
Task 2 is running on thread: pool-1-thread-2
Task 3 is running on thread: pool-1-thread-3
Task 1 completed
Task 2 completed
Task 3 completed
Task 4 is running on thread: pool-1-thread-1
Task 5 is running on thread: pool-1-thread-2
Task 4 completed
Task 5 completed
```

---

## **3. Thread Lifecycle & Common Methods**

### **Thread Lifecycle States in Java**

A thread can be in one of the following states (as defined in `Thread.State` enum):

1. **NEW** – Thread is created but not started.
2. **RUNNABLE** – Thread is ready to run or running.
3. **BLOCKED** – Thread is waiting for a lock (e.g., entering a `synchronized` block).
4. **WAITING** – Thread is waiting indefinitely for another thread to perform a particular action.
5. **TIMED\_WAITING** – Thread is waiting for a specified amount of time.
6. **TERMINATED** – Thread has finished executing.

---

### **Common Thread Methods**

| Method        | Description                                                                |
| ------------- | -------------------------------------------------------------------------- |
| `start()`     | Starts the thread and invokes `run()` in a new thread.                     |
| `run()`       | Contains the logic to be executed in the thread.                           |
| `sleep(ms)`   | Pauses current thread for specified milliseconds.                          |
| `join()`      | Waits for the thread to finish before continuing.                          |
| `yield()`     | Suggests current thread to pause and allow others of same priority to run. |
| `interrupt()` | Interrupts a sleeping or waiting thread.                                   |
| `isAlive()`   | Checks if thread is still running.                                         |

---

### **Example Demonstrating `start()`, `sleep()`, and `join()`**

```java
class MyThread extends Thread {
    private int id;

    public MyThread(int id) {
        this.id = id;
    }

    public void run() {
        System.out.println("Thread " + id + " started.");
        try {
            Thread.sleep(1000); // simulate some work
        } catch (InterruptedException e) {
            System.out.println("Thread " + id + " interrupted.");
        }
        System.out.println("Thread " + id + " finished.");
    }
}

public class Main {
    public static void main(String[] args) throws InterruptedException {
        MyThread t1 = new MyThread(1);
        MyThread t2 = new MyThread(2);

        t1.start();
        t2.start();

        // Wait for t1 and t2 to finish
        t1.join();
        t2.join();

        System.out.println("Main thread finished after t1 and t2.");
    }
}
```

---

### Key Notes:

* **`start()`** starts a new thread (don't call `run()` directly).
* **`sleep()`** pauses the thread without releasing locks.
* **`join()`** is useful when you want to wait for a thread to complete before continuing.
* **`interrupt()`** can be used to stop a thread that’s in `sleep()` or `wait()` state.

---

## **1. `sleep()`**

### Purpose:

* Pauses the **current thread** for a specified time.
* Keeps the monitor lock if inside a synchronized block.

### Example:

```java
Thread.sleep(1000); // Sleep for 1 second
```

### Notes:

* **Static method** (called on current thread).
* Throws `InterruptedException`.
* Doesn't release any lock.

---

## **2. `join()`**

### Purpose:

* Makes the **current thread wait** for another thread to finish execution.

### Example:

```java
Thread t = new Thread(() -> {
    System.out.println("Worker thread");
});
t.start();
t.join();  // Main thread waits until 't' finishes
System.out.println("Main thread continues");
```

### Notes:

* Called on another thread.
* Blocks until that thread dies or timeout elapses.
* Useful for sequencing threads.

---

## **3. `yield()`**

### Purpose:

* Suggests to the **scheduler** that the current thread is willing to pause and let others of same or higher priority run.

### Example:

```java
Thread.yield(); // Hint to scheduler
```

### Notes:

* **Static method**.
* No guarantee it will pause.
* Doesn’t release lock or sleep.
* Rarely used in practice.

---

## **4. `interrupt()`**

### Purpose:

* Sets the **interrupt flag** on a thread, which can be used to request stopping a thread.

### Example:

```java
Thread t = new Thread(() -> {
    try {
        Thread.sleep(5000);
    } catch (InterruptedException e) {
        System.out.println("Thread interrupted during sleep.");
    }
});
t.start();
t.interrupt(); // Interrupts the sleeping thread
```

### Notes:

* Doesn't forcibly kill a thread.
* Used to break `sleep()`, `wait()`, or manually check with `isInterrupted()`.

---

## **5. `wait()`**

### Purpose:

* Makes the **current thread wait** until another thread calls `notify()` or `notifyAll()` on the same object.

### Example:

```java
synchronized (obj) {
    obj.wait(); // waits until notified
}
```

### Notes:

* Must be called inside a `synchronized` block.
* Releases the lock.
* Paired with `notify()` / `notifyAll()`.

---

## **Comparison Table**

| Method        | Called On      | Blocks Current Thread | Releases Lock | Used For                       |
| ------------- | -------------- | --------------------- | ------------- | ------------------------------ |
| `sleep()`     | Current Thread | Yes                   | No            | Delay execution                |
| `join()`      | Another Thread | Yes                   | No            | Wait for another thread to end |
| `yield()`     | Current Thread | Maybe (hint)          | No            | Suggest giving up CPU          |
| `interrupt()` | Another Thread | No (sets flag)        | N/A           | Request thread to stop         |
| `wait()`      | Object         | Yes                   | Yes           | Wait for condition/signal      |

---


## **Problem Overview**

* **Producer**: adds items to a shared buffer.
* **Consumer**: removes items from that buffer.
* If the buffer is **full**, the producer must `wait()`.
* If the buffer is **empty**, the consumer must `wait()`.

We’ll use a shared `LinkedList` with capacity.

---

## **Java Code: Producer-Consumer with wait/notify**

```java
import java.util.LinkedList;

class SharedBuffer {
    private final LinkedList<Integer> buffer = new LinkedList<>();
    private final int CAPACITY = 5;

    public synchronized void produce(int item) throws InterruptedException {
        while (buffer.size() == CAPACITY) {
            System.out.println("Buffer full. Producer waiting...");
            wait(); // wait until space is available
        }
        buffer.add(item);
        System.out.println("Produced: " + item);
        notify(); // signal to consumer
    }

    public synchronized int consume() throws InterruptedException {
        while (buffer.isEmpty()) {
            System.out.println("Buffer empty. Consumer waiting...");
            wait(); // wait until something is available
        }
        int item = buffer.removeFirst();
        System.out.println("Consumed: " + item);
        notify(); // signal to producer
        return item;
    }
}

public class Main {
    public static void main(String[] args) {
        SharedBuffer buffer = new SharedBuffer();

        Thread producer = new Thread(() -> {
            int item = 0;
            try {
                while (true) {
                    buffer.produce(item++);
                    Thread.sleep(500); // simulate time to produce
                }
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        });

        Thread consumer = new Thread(() -> {
            try {
                while (true) {
                    buffer.consume();
                    Thread.sleep(800); // simulate time to consume
                }
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        });

        producer.start();
        consumer.start();
    }
}
```

---

## **Explanation**

* `SharedBuffer` is synchronized to avoid race conditions.
* `wait()` suspends the thread and releases the lock.
* `notify()` wakes up one waiting thread.
* `while` loops prevent spurious wakeups.

---

## **Sample Output**

```
Produced: 0
Consumed: 0
Produced: 1
Produced: 2
Consumed: 1
...
```

---

## **4. Thread Synchronization in Java**

### **Why Synchronization?**

When multiple threads access **shared resources** (variables, collections, files, etc.), there's a risk of **race conditions**—where threads interleave in an unexpected way and cause data corruption.

### **Goal of Synchronization**

Ensure that **only one thread** can access critical sections of code (shared data) at a time.

---

## **Ways to Synchronize in Java**

### **1. `synchronized` Keyword**

#### a) **Synchronized Method**

Locks the object (for instance methods) or class (for static methods).

```java
public synchronized void increment() {
    counter++;
}
```

#### b) **Synchronized Block**

Gives you more control—can lock on a specific object.

```java
public void increment() {
    synchronized (this) {
        counter++;
    }
}
```

---

### **2. Lock Interface (`java.util.concurrent.locks.Lock`)**

Provides more flexible lock mechanisms than `synchronized`.

```java
import java.util.concurrent.locks.ReentrantLock;

class Counter {
    private int count = 0;
    private final ReentrantLock lock = new ReentrantLock();

    public void increment() {
        lock.lock(); // acquire lock
        try {
            count++;
        } finally {
            lock.unlock(); // always release
        }
    }
}
```

---

### **Key Differences: `synchronized` vs `Lock`**

| Feature           | `synchronized`     | `Lock`                                |
| ----------------- | ------------------ | ------------------------------------- |
| Reentrant         | Yes                | Yes                                   |
| Interruptible     | No                 | Yes                                   |
| Try lock          | No                 | Yes (`tryLock()`)                     |
| Fairness control  | No                 | Yes (e.g., `new ReentrantLock(true)`) |
| Condition support | No (`wait/notify`) | Yes (`newCondition()`)                |

---

### **Example: Race Condition Without Synchronization**

```java
class Counter {
    int count = 0;

    public void increment() {
        count++;
    }
}

public class Main {
    public static void main(String[] args) throws InterruptedException {
        Counter counter = new Counter();

        Thread t1 = new Thread(() -> {
            for (int i = 0; i < 10000; i++) counter.increment();
        });

        Thread t2 = new Thread(() -> {
            for (int i = 0; i < 10000; i++) counter.increment();
        });

        t1.start();
        t2.start();
        t1.join();
        t2.join();

        System.out.println("Final count: " + counter.count); // not always 20000
    }
}
```

---

### **With Synchronization**

Add `synchronized` to fix the race condition:

```java
public synchronized void increment() {
    count++;
}
```

---

## **5. Concurrent Collections and Atomic Variables**

### Problem with Normal Collections:

Collections like `ArrayList`, `HashMap` are **not thread-safe**. If multiple threads modify them concurrently, it can lead to **race conditions or `ConcurrentModificationException`**.

---

## **1. Concurrent Collections (from `java.util.concurrent`)**

### **a) `ConcurrentHashMap`**

* Allows concurrent read and limited concurrent write access.
* Does not throw `ConcurrentModificationException`.

```java
import java.util.concurrent.*;

public class Example {
    public static void main(String[] args) {
        ConcurrentHashMap<String, Integer> map = new ConcurrentHashMap<>();

        Runnable task = () -> {
            for (int i = 0; i < 1000; i++) {
                map.merge("count", 1, Integer::sum);
            }
        };

        Thread t1 = new Thread(task);
        Thread t2 = new Thread(task);
        t1.start(); t2.start();
        try { t1.join(); t2.join(); } catch (InterruptedException e) {}

        System.out.println("Final count: " + map.get("count")); // Should be 2000
    }
}
```

---

### **b) `CopyOnWriteArrayList`**

* Ideal for **read-heavy** scenarios.
* On every write, it creates a **new copy** of the underlying array.
* No need to explicitly synchronize during iteration.

```java
CopyOnWriteArrayList<String> list = new CopyOnWriteArrayList<>();
list.add("Hello");
list.add("World");

for (String item : list) {
    list.add("New");  // No ConcurrentModificationException
    System.out.println(item);
}
```

---

## **2. Atomic Variables (from `java.util.concurrent.atomic`)**

### Purpose:

For performing **lock-free, thread-safe operations** on single variables.

### **a) `AtomicInteger`**

```java
import java.util.concurrent.atomic.AtomicInteger;

class Counter {
    AtomicInteger count = new AtomicInteger();

    public void increment() {
        count.incrementAndGet(); // atomic operation
    }
}
```

### Benefits:

* No explicit locking.
* Very fast for simple counters, flags, etc.

---

## When to Use What?

| Use Case                         | Solution                         |
| -------------------------------- | -------------------------------- |
| Thread-safe map                  | `ConcurrentHashMap`              |
| Thread-safe list with many reads | `CopyOnWriteArrayList`           |
| Simple counter/flag              | `AtomicInteger`, `AtomicBoolean` |
| Complex coordination             | Locks / Synchronization          |

---

## **6. Deadlocks in Java**

### **What is a Deadlock?**

A **deadlock** occurs when two or more threads are **waiting for each other** to release resources, and none of them can proceed.

---

### **Real-world analogy**

Imagine:

* **Thread A** holds **Lock 1**, waiting for **Lock 2**.
* **Thread B** holds **Lock 2**, waiting for **Lock 1**.
  Both are stuck—this is a deadlock.

---

### **Code Example: Deadlock in Java**

```java
public class DeadlockExample {
    private static final Object Lock1 = new Object();
    private static final Object Lock2 = new Object();

    public static void main(String[] args) {
        Thread t1 = new Thread(() -> {
            synchronized (Lock1) {
                System.out.println("Thread 1: Holding Lock1...");
                try { Thread.sleep(100); } catch (InterruptedException e) {}
                System.out.println("Thread 1: Waiting for Lock2...");
                synchronized (Lock2) {
                    System.out.println("Thread 1: Acquired Lock2!");
                }
            }
        });

        Thread t2 = new Thread(() -> {
            synchronized (Lock2) {
                System.out.println("Thread 2: Holding Lock2...");
                try { Thread.sleep(100); } catch (InterruptedException e) {}
                System.out.println("Thread 2: Waiting for Lock1...");
                synchronized (Lock1) {
                    System.out.println("Thread 2: Acquired Lock1!");
                }
            }
        });

        t1.start();
        t2.start();
    }
}
```

---

### **Output (stuck in deadlock)**

```
Thread 1: Holding Lock1...
Thread 2: Holding Lock2...
Thread 1: Waiting for Lock2...
Thread 2: Waiting for Lock1...
```

Now both threads are waiting **forever**—deadlock!

---

## **How to Avoid Deadlocks**

### 1. **Always lock resources in the same order**

```java
// Always lock Lock1, then Lock2 in all threads
synchronized (Lock1) {
    synchronized (Lock2) {
        // Safe block
    }
}
```

### 2. **Use `tryLock()` from `ReentrantLock`**

This avoids waiting forever. Threads can back off and retry later.

```java
import java.util.concurrent.locks.*;

Lock lock1 = new ReentrantLock();
Lock lock2 = new ReentrantLock();

if (lock1.tryLock()) {
    if (lock2.tryLock()) {
        try {
            // critical section
        } finally {
            lock2.unlock();
            lock1.unlock();
        }
    } else {
        lock1.unlock();
    }
}
```

### 3. **Use timeout**

Detect and avoid long waits.

---

### 4. **Deadlock Detection Tools**

* JVM won’t prevent deadlocks, but you can detect them:

  * Use `jconsole`, `jvisualvm`, or `ThreadMXBean` from Java.

---

## **7. Thread Coordination Tools in Java**

These tools help coordinate multiple threads, making them wait for each other or control access to shared resources.

---

### **1. CountDownLatch**

* Allows one or more threads to wait until a set of operations complete.
* Initialized with a count; threads wait until count reaches zero.

**Example:**

```java
import java.util.concurrent.CountDownLatch;

public class CountDownLatchExample {
    public static void main(String[] args) throws InterruptedException {
        CountDownLatch latch = new CountDownLatch(3);

        Runnable worker = () -> {
            System.out.println(Thread.currentThread().getName() + " finished work.");
            latch.countDown();
        };

        new Thread(worker, "Thread 1").start();
        new Thread(worker, "Thread 2").start();
        new Thread(worker, "Thread 3").start();

        System.out.println("Main thread waiting for workers...");
        latch.await();  // waits until count reaches zero
        System.out.println("All workers done, main thread proceeds.");
    }
}
```

---

### **2. CyclicBarrier**

* Allows a fixed number of threads to wait for each other at a common barrier point.
* Can be reused (reset after all threads reach barrier).

**Example:**

```java
import java.util.concurrent.CyclicBarrier;

public class CyclicBarrierExample {
    public static void main(String[] args) {
        CyclicBarrier barrier = new CyclicBarrier(3, () -> System.out.println("All threads reached barrier."));

        Runnable task = () -> {
            try {
                System.out.println(Thread.currentThread().getName() + " working...");
                Thread.sleep(1000);
                barrier.await();  // wait for others
                System.out.println(Thread.currentThread().getName() + " continues.");
            } catch (Exception e) {
                e.printStackTrace();
            }
        };

        new Thread(task, "Thread A").start();
        new Thread(task, "Thread B").start();
        new Thread(task, "Thread C").start();
    }
}
```

---

### **3. Semaphore**

* Controls access to a shared resource with a limited number of permits.
* Useful for resource pooling.

**Example:**

```java
import java.util.concurrent.Semaphore;

public class SemaphoreExample {
    static Semaphore semaphore = new Semaphore(2);

    public static void main(String[] args) {
        Runnable task = () -> {
            try {
                semaphore.acquire();
                System.out.println(Thread.currentThread().getName() + " acquired semaphore.");
                Thread.sleep(2000); // simulate resource usage
            } catch (InterruptedException e) {
                e.printStackTrace();
            } finally {
                System.out.println(Thread.currentThread().getName() + " releasing semaphore.");
                semaphore.release();
            }
        };

        for (int i = 1; i <= 5; i++) {
            new Thread(task, "Thread " + i).start();
        }
    }
}
```

---

## **8. ThreadLocal in Java**

### **What is ThreadLocal?**

* A `ThreadLocal` provides **thread-local variables**.
* Each thread accessing a `ThreadLocal` variable has its **own, independently initialized copy**.
* This helps avoid sharing state between threads without synchronization.

---

### **Why use ThreadLocal?**

* To keep **per-thread context or state** that shouldn’t be shared.
* Common use cases: user sessions, transaction IDs, SimpleDateFormat instances (which are not thread-safe).

---

### **Basic Example**

```java
public class ThreadLocalExample {
    // ThreadLocal holding Integer value
    private static ThreadLocal<Integer> threadLocal = ThreadLocal.withInitial(() -> 0);

    public static void main(String[] args) {
        Runnable task = () -> {
            int value = threadLocal.get();
            value += 5;
            threadLocal.set(value);
            System.out.println(Thread.currentThread().getName() + ": " + threadLocal.get());
        };

        Thread t1 = new Thread(task, "Thread-1");
        Thread t2 = new Thread(task, "Thread-2");

        t1.start();
        t2.start();
    }
}
```

**Output:**

```
Thread-1: 5
Thread-2: 5
```

Each thread has its own copy of the value.

---

### **Important Notes**

* `ThreadLocal` variables **do not get shared** between threads.
* Always **remove** the value after use to avoid memory leaks in thread pools:

```java
threadLocal.remove();
```

---

## 9. Java Memory Model (JMM) & Happens-Before Principle

### What is the Java Memory Model?

* Defines how **threads interact through memory**.
* Specifies rules about **visibility** and **ordering** of reads/writes of variables between threads.
* Without proper synchronization, threads may see **stale values**.

---

### Happens-Before Principle

* If one action **happens-before** another, then the first is **visible and ordered before** the second.
* This guarantees **visibility** and **ordering** between threads.

---

### Common Happens-Before Rules:

| Happens-Before Relationship | Description                                                                                         |
| --------------------------- | --------------------------------------------------------------------------------------------------- |
| **Program order rule**      | Within a single thread, statements happen in program order.                                         |
| **Monitor lock rule**       | Unlocking a monitor (e.g., `synchronized` block exit) happens-before locking it again.              |
| **Volatile variable rule**  | Writes to a volatile variable happen-before subsequent reads of that volatile.                      |
| **Thread start rule**       | A thread calling `start()` happens-before the started thread runs.                                  |
| **Thread join rule**        | Actions in a thread happen-before another thread successfully returns from `join()` on that thread. |

---

### Why Does This Matter?

Without these guarantees, threads can:

* Read outdated variable values (visibility problem).
* Execute instructions in unexpected order (reordering).

---

### Example: Visibility Problem Without `volatile`

```java
class Flag {
    boolean running = true;

    void stop() {
        running = false;
    }

    void run() {
        while (running) {
            // do work
        }
        System.out.println("Stopped");
    }
}
```

If `running` is not declared **volatile**, the thread running `run()` might **never see the update** from `stop()` and loop forever.

Fix:

```java
volatile boolean running = true;
```

---

### Summary:

* Use **`volatile`**, **`synchronized`**, or **other concurrency tools** to establish happens-before relationships.
* Understanding JMM is crucial for writing correct multithreaded code.

---


## **10. `volatile`, `synchronized`, and Advanced Locks**

These are core tools to ensure **visibility** and **atomicity** in multithreading.

---

### **1. `volatile` Keyword**

#### Purpose:

* Ensures visibility of variable changes across threads.
* Does **not** guarantee atomicity (e.g., `count++` is not atomic).

#### Example:

```java
class VolatileExample {
    volatile boolean running = true;

    void stop() {
        running = false;
    }

    void run() {
        while (running) {
            // do work
        }
        System.out.println("Thread stopped");
    }
}
```

Without `volatile`, the `run()` thread may **never see** the update to `running`.

---

### **2. `synchronized` Keyword**

#### Purpose:

* Provides **mutual exclusion** and establishes **happens-before** relationships.

#### Usage:

```java
synchronized (object) {
    // critical section
}
```

* Can be used on methods or blocks.
* Only one thread can hold the lock for the synchronized block/object at a time.

---

### **3. `ReentrantLock` (from `java.util.concurrent.locks`)**

#### Why use it over `synchronized`?

* More control (tryLock, timed lock, interruptible lock)
* Can use with `Condition` variables (like `wait/notify`, but more powerful)

#### Example:

```java
import java.util.concurrent.locks.ReentrantLock;

class ReentrantLockExample {
    private final ReentrantLock lock = new ReentrantLock();

    void doWork() {
        lock.lock();
        try {
            System.out.println(Thread.currentThread().getName() + " working...");
        } finally {
            lock.unlock();
        }
    }
}
```

---

### **4. ReadWriteLock**

* Allows **multiple readers** or **one writer**, but not both.
* Useful for read-heavy shared data access.

#### Example:

```java
import java.util.concurrent.locks.*;

class ReadWriteLockExample {
    private final ReadWriteLock rwLock = new ReentrantReadWriteLock();
    private int data = 0;

    void readData() {
        rwLock.readLock().lock();
        try {
            System.out.println("Reading data: " + data);
        } finally {
            rwLock.readLock().unlock();
        }
    }

    void writeData(int value) {
        rwLock.writeLock().lock();
        try {
            data = value;
            System.out.println("Wrote data: " + data);
        } finally {
            rwLock.writeLock().unlock();
        }
    }
}
```

---

## **11. Thread Dump in Java**

### **What is a Thread Dump?**

* A **thread dump** is a snapshot of **all active threads** in a Java Virtual Machine (JVM) at a given point in time.
* It shows:

  * Thread names and states (RUNNABLE, WAITING, BLOCKED, etc.)
  * Stack traces for each thread
  * Locks held or waited upon
* It’s a **critical tool for debugging** issues like:

  * Deadlocks
  * Thread contention
  * High CPU usage
  * Application hangs

---

### **How to Take a Thread Dump**

#### **1. Using `jstack` (standard way)**

```bash
jstack <pid>
```

* Get PID via: `jps` or `ps -ef | grep java`
* Example:

  ```bash
  jstack 12345 > threaddump.txt
  ```

#### **2. On Linux/Mac: Using `kill -3`**

```bash
kill -3 <pid>
```

* The thread dump will be printed to the application’s **standard output** (usually in logs like `catalina.out` for Tomcat).

#### **3. In IDEs (like IntelliJ or Eclipse)**

* You can get a thread dump while debugging or running an app via the **"Thread" tab** in the Debug view.

#### **4. Using Java VisualVM**

* Connect to the running Java process.
* Go to the **"Threads"** tab.
* Click **"Thread Dump"**.

---

### **How to Analyze a Thread Dump**

#### 1. **Check Thread States**

* `RUNNABLE`: Actively running on CPU
* `WAITING`: Waiting indefinitely for another thread (`wait()`, `join()`)
* `TIMED_WAITING`: Waiting with timeout (`sleep()`, `wait(timeout)`, `join(timeout)`)
* `BLOCKED`: Waiting to acquire a monitor lock (e.g., `synchronized`)

#### 2. **Look for Deadlocks**

* Search for phrases like:

  ```
  Found one Java-level deadlock:
  ```
* Threads involved in a deadlock will be waiting on each other’s locks.

#### 3. **Check High CPU Threads**

* If CPU usage is high, look for multiple threads in `RUNNABLE` with tight loops.
* Tools like `top -H -p <pid>` can help identify which thread (TID) uses most CPU. Convert the TID to hex to match in the dump.

#### 4. **Look for Lock Contention**

* See if many threads are `BLOCKED` on the same object.
* Example:

  ```text
  - waiting to lock <0x00000000d55f00a8> (a java.lang.Object)
  ```

#### 5. **Analyze Stack Traces**

* Identify repetitive patterns.
* Check stuck methods or bottlenecks.

---

### Example Snippet from Thread Dump

```text
"Thread-1" #12 prio=5 os_prio=0 tid=0x000000001eac4800 nid=0x3d38 waiting on condition [0x00000000225fe000]
   java.lang.Thread.State: WAITING (on object monitor)
	at java.lang.Object.wait(Native Method)
	at com.example.MyClass.waitMethod(MyClass.java:50)
	- locked <0x00000000d55f00a8> (a java.lang.Object)
```

* Thread is in `WAITING` state on a monitor (object lock).
* Locked object and exact code location are visible.

---

### Tools for Visual Analysis

* **[FastThread.io](https://fastthread.io/)** – Paste your thread dump and get a clean visual report.
* **Java VisualVM** – Live monitoring and thread dump analysis.

---

### **12. What is a Race Condition in Java?**

A **race condition** occurs when **two or more threads access shared data** at the same time and try to **modify it concurrently**, and the final outcome **depends on the timing** of their execution.

It leads to **unpredictable behavior**, **bugs**, and **data corruption** if not handled properly.

---

### **Example of Race Condition**

```java
class Counter {
    int count = 0;

    void increment() {
        count++;
    }
}

public class RaceConditionExample {
    public static void main(String[] args) throws InterruptedException {
        Counter counter = new Counter();

        Thread t1 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) counter.increment();
        });

        Thread t2 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) counter.increment();
        });

        t1.start();
        t2.start();

        t1.join();
        t2.join();

        System.out.println("Final Count: " + counter.count); // Often < 2000
    }
}
```

**Expected Output:** `2000`
**Actual Output:** Varies, often less than 2000 due to lost updates.

---

### **Why It Happens**

* `count++` is **not atomic**.
  Internally:

  ```java
  int temp = count;
  temp = temp + 1;
  count = temp;
  ```
* If two threads execute this at the same time, one update can **overwrite** the other.

---

### **How to Fix Race Conditions**

#### 1. **Using `synchronized`**

```java
synchronized void increment() {
    count++;
}
```

#### 2. **Using `AtomicInteger`**

```java
AtomicInteger count = new AtomicInteger();

void increment() {
    count.incrementAndGet();
}
```

#### 3. **Using Locks (e.g., ReentrantLock)**

---

### **Summary**

| Aspect     | Race Condition                                                                      |
| ---------- | ----------------------------------------------------------------------------------- |
| Caused by  | Concurrent, unsynchronized access to shared data                                    |
| Results in | Unpredictable outcomes, bugs                                                        |
| Fix using  | `synchronized`, `volatile` (in visibility-only cases), `Atomic` classes, or `Locks` |

---

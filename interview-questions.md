# Java FUll Stack Interview Questions  

## Core Java

1. What is the difference between "super" and "this" in Core Java?
2. Explain the usage of "super()" and "this()" calls in constructors in Java.
3. Differentiate between a "static" method and a "static" block in Java.
4. Describe the components of the JVM architecture, including Classloader, Bytecode Verifier, Memory Area, and Execution Engine.
5. What are the drawbacks of using System.out.println() for output in Java?
6. List the key features introduced in Java 7, Java 8, and Java 9.
7. Discuss the concept of garbage collection in Java, including its uses and working principles.
8. How is memory management handled in the Java programming language?
9. Can the "main()" method be overridden in Java?
10. Is it possible to overload the "main()" method in Java?
11. Can the "main" method be declared as "final" in Java?
12. Explain the concept of object cloning in Java.
13. Differentiate between deep copy and shallow copy in Java.
14. If the "compareTo()" method is implemented in a class, what is the need to implement the "equals" method as well?
15. Highlight the importance of using a singleton object in Java.
16. Describe the Factory pattern and other commonly used design patterns in Java.
17. Why would you use a final class when its methods cannot be overridden?
18. Is it possible to override a private method in a class if the class itself is declared as final?
19. Can changes be made to a final or immutable class using reflection in Java?
20. What is the garbage collector algorithm used by the JVM, and is it the same for every operating system?
21. When does the Garbage Collector invoke itself in Java?
22. How can you create an Enumeration in Java, and what are its common uses?
23. What is the purpose of the "rt.jar" file in Java?
24. Explain the significance of the Manifest file in Java.
25. Differentiate between method overriding and method overloading in Java.
26. Why might you choose to use an interface over an abstract class in Java?
27. Can you reassign a value to a final variable in Java?
28. How can you iterate through a List using Lambda Expressions in Java?
29. What is type inference in Java?
30. Compare and contrast stateful and stateless programming in Java.
31. Explain the concept of Wrapper Classes in Java.
32. Distinguish between primitive and non-primitive data types in Java.
33. What is an Anonymous Object in Java?
34. Is it possible to overload methods in a child class in Java?
35. Can you change the return type of an overloaded method in Java?
36. Can you change the return type of an overriding method in Java?
37. Discuss the differences between compile-time binding and runtime binding, as well as compile-time polymorphism and runtime polymorphism.
38. Explain the concepts of Static Binding and Dynamic Binding in Java. How does polymorphism work in the case of overloading and overriding?
39. What is a covariant return type in method overriding, and does it support overloading as well?
40. What are the advantages and disadvantages of using log4j for logging in Java?
41. Explain the concepts of coupling and collision in software engineering.
42. Which sorting algorithm is considered the best in Java, and why?
43. What is the significance of the "java.lang" package in Java?
44. Describe the purpose and usage of the "final" keyword in Java.
45. Why can private members be accessed through reflection in Java?
46. Discuss the different scopes of member variables in Java.
47. What is reflection in Java, and what are its common uses?
48. Is the FileNotFoundException a checked or unchecked exception in Java?
49. How can you reverse an array of integers in Java with optimization, using a single array and temporary variable swapping?
50. Provide a Java program for binary search.
51. What is an inner class in Java?
52. How do you create an object of an inner class in Java?
53. What is the name of the compiled inner class in Java?
54. In what situations would you use an inner class in Java?
55. Explain the difference between a static class and a static inner class in Java.
56. What are the access modifiers available in Java?
57. How do access modifiers behave in the context of inheritance and method overriding in Java?
58. What is Serialization and Deserialization in Java?
59. How do you implement Serialization in Java?
60. How does the JVM operate on serialized objects in Java?
61. Explain the difference between a method and a function in Java.
62. What is an Annotation in Java, and how do you create a custom annotation?
63. Can you declare a class as both private and protected in Java?
64. What is the purpose of the "transient" keyword in Java?
65. What is the meaning of the Serial Version UID in Java Serialization?
66. Explain the difference between the "path" and "classpath" variables in Java.
67. Define and differentiate between Static Import, Static Block, Static Method, Static Variable, and Static Class in Java.
68. What are the differences between HTTP and HTTPS (HTTP Secure)?
69. What is the JVM (Java Virtual Machine)?
70. Explain the concept of platform independence in Java.
71. Is the JVM platform-independent?
72. Who calls the main method in Java?
73. Differentiate between JDK, JRE, and JVM in Java.
74. What are the different memory areas inside the JVM in Java?
75. Describe the Heap Area in the JVM.
76. What happens to the JVM when an error or exception occurs in Java?
77. Is the String constant pool part of the Heap Area in Java?
78. Why was the String constant pool introduced when we have the Heap Area in Java? What are Native Method Stacks?
79. How does the class loader work in Java?
80. What details are stored inside the Method Area in Java?
81. Explain JIT (Just-in-Time) compilation in Java.
82. Describe the Garbage Collector in Java.
83. How do you invoke the garbage collector in Java?
84. Can you guarantee the invocation of the garbage collector in Java?
85. What is a .class file in Java?
86. Can you run a .class file on any JVM on different systems in Java?
87. What is bytecode in Java?
88. How do you increase or decrease the allocated RAM for a runtime JVM in Java?
89. What is an OutOfMemoryError in Java, and how can you solve it?
90. What is a Heap Dump in Java?
91. Explain a few ways to fix memory issues in Java.
92. Differentiate between hashCode() and equals() in Java.
93. Describe the real use of interfaces and abstract classes in Java.
94. Provide an example of a Marker Interface in Java.
95. Explain the real use of Marker Interfaces in Java.
96. If we have an abstract method in an interface, can the same method be declared in an abstract class? In this case, why choose an interface over an abstract class in Java?
97. How can you achieve multiple inheritance in Java?
98. Explain all the object-oriented programming concepts in Java.
99. Differentiate between Encapsulation and Abstraction in Java.
100. Discuss the significance of object-oriented programming in Java.
101. How are polymorphism and abstraction related in object-oriented programming?
102. Is it possible to create an object of an abstract class inside the same abstract class in Java?
103. What does OOP (Object-Oriented Programming) refer to?
104. Define the concept of a Class in object-oriented programming.
105. Define the concept of an Object in object-oriented programming.
106. Explain the concept of Encapsulation in object-oriented programming.
107. Explain the concept of Abstraction in object-oriented programming.
108. What is Inheritance in object-oriented programming?
109. Explain the concept of Polymorphism in object-oriented programming.
110. Can you provide real-life examples illustrating all the concepts of object-oriented programming?
111. Discuss the differences between Inheritance and Polymorphism in object-oriented programming.
112. What is Overriding and Overloading in Java, and what is the difference between them?
113. Explain the rules for access modifiers when overriding methods in Java.
114. What is a Covariant Type in Java?
115. Define Static Binding, Runtime Binding, Compile-time Polymorphism, and Runtime Polymorphism in Java.
116. Explain the concepts of IS-A and HAS-A relationships in Java.
117. What are Association, Composition, and Aggregation in Java?
118. Explain the usage and significance of the "super" and "this" keywords in Java.
119. What is an interface in Java, and can you instantiate an interface?
120. Define multi-level and multiple level inheritance in Java.
121. What is the diamond problem in object-oriented programming, and how is it resolved?
122. Explain the protected access specifier in the context of inheritance in Java.
123. How is Exception Handling implemented in inheritance in Java, and what are the rules associated with it?
124. Define Data Hiding in the context of inheritance in Java.
125. Compare and contrast String, StringBuilder, and StringBuffer in Java.
126. What does it mean for a class to be immutable, and how can you make a class immutable in Java?
127. What are the properties of an Immutable object in Java?
128. Explain the differences between String literals and String objects in Java.
129. Describe the concept of the String pool in Java.
130. What happens when you compare "==" and ".equals" for String and new String objects in Java?
131. What are the results of comparing "==" and ".equals" for String and StringBuffer objects in Java?
132. Explain the output of the expression "A"+"B"+"C"+"D" in Java.
133. Why are StringBuilder and StringBuffer classes declared as "final" in Java?
134. Why is String immutable in Java, whereas StringBuilder and StringBuffer are not?
135. Describe the "intern()" method in Java for Strings.
136. How can you perform a Deep copy in the case of String objects in Java?
137. Is it possible to store StringBuffer objects in a TreeSet in Java?
138. What is the purpose of the "ensureCapacity" method in Java?

## Collection

139. What is the default size of collection classes like ArrayList and Vector in Java?
140. Explain the dynamic size increment in ArrayList and provide details about how it works.
141. What is the role of the "threshold" in a HashMap in Java?
142. What is the significance of the Load Factor in Java Collections, and can you provide an example?
143. Explain the concepts of Hashing and Rehashing in the context of collections.
144. What is the load factor of Vector, and what is the default size of a Vector in Java?
145. Differentiate between Hashtable and HashMap in Java.
146. Compare and contrast Vector and ArrayList in Java.
147. Can the hash codes of two objects be the same or different in Java?
148. What is Hashcode Collision, and how is it handled in Java?
149. Explain the internal working of a HashMap in Java.
150. Compare the usage of "for each" loops and Iterators in Java.
151. Differentiate between Iterator and ListIterator in Java.
152. Explain the concepts of Comparable and Comparator in Java.
153. Provide Java code to sort employee objects using employee ID.
154. Provide Java code to sort employee objects using both employee ID and employee name.
155. Why is the Iterable interface located in the java.lang package in Java?
156. Discuss the uses of the Arrays and Collections classes in Java.
157. Explain why the Map interface is not part of the Collection interface hierarchy in Java.
158. Can collections in Java contain null values, and what about concurrent collections?
159. Which collection types in Java can have null values?
160. Name some synchronized and non-synchronized collection classes in Java.
161. What is Generics in Java?
162. Why were Generics introduced in Java?
163. Describe the internal implementation of HashMap in Java and the algorithms used internally.
164. Why is the Comparable interface implemented in classes when the hashCode method is present to compare objects?
165. What implementations are required for an object to be used as a key in a TreeMap in Java?
166. Explain different ways to iterate through a map in Java.
167. What does the "Iterator.next()" method return in Java?
168. How can you make any collection immutable in Java, ensuring that it cannot be modified (no add/remove/update actions allowed)?
169. What is the use of a question mark (?) in collections and generics in Java?
170. With which collection types do we use Comparable or Comparator in Java?
171. What is the difference between Hashtable and ConcurrentMap in Java?
172. Explain the hierarchy of the Collection interface, from Iterable to various interfaces and classes in Java.
173. When should you implement the hashCode() and equals() methods in your class in Java?
174. How can you allow duplicate values in hashCode in Java?
175. How does ConcurrentHashMap work in a multithreaded environment in Java?
176. How can you make an object immutable when it has mutable objects as member variables in Java?
177. What is a Multivalue Map in Java?
178. How do you sort an array with and without using the Arrays or Collections classes in Java?
179. How would you sort a list of employee objects in Java?
180. Explain the differences between arrays and the Collections class in Java.
181. What is a Priority Queue in Java?
182. What is a Blocking Priority Queue in Java?
183. Is it possible to create an object of an interface in Java?
184. Discuss the differences between an interface and an abstract class in Java.
185. Explain the idea behind an abstract class in Java.
186. Can you create an object of an abstract class in Java?
187. What is a Functional Interface in Java?
188. Can you declare variables in an interface in Java?
189. List and differentiate between different types of cursors in Java.
190. What is Enumeration in Java?
191. What is an Iterator in Java?
192. What is a ListIterator in Java?
193. Explain the differences between Enumeration and Iterator in Java.
194. Explain the differences between Enumeration and ListIterator in Java.
195. Explain the differences between ListIterator and Iterator in Java.
196. Describe scenarios in which you would use Enumeration, Iterator, or ListIterator in Java.
197. List a few methods commonly used with Enumeration, Iterator, and ListIterator in Java.
198. Discuss the differences between the "for each" loop and ListIterator/Iterator/Enumeration in Java.
199. Explain when to use a "for" loop and when to use Iterators in Java.
200. Why does ArrayList implement interfaces like java.util.RandomAccess, java.lang.Cloneable, and java.io.Serializable in Java?
201. Why has ArrayList extended the java.util.AbstractList class in Java?
202. Why has LinkedList extended the java.util.AbstractSequentialList class instead of java.util.AbstractList class in Java?
203. Why has LinkedList not implemented the java.util.RandomAccess interface in Java?
204. What is a Marker Interface in Java, and can you provide examples related to ArrayList and LinkedList?
205. Why doesn't LinkedList support a constructor with a size parameter, like new LinkedList<>(size), in Java?
206. Why are Java Vector and Stack classes considered obsolete or deprecated?
207. Why does the indexing of arrays start at zero in Java?
208. What are the differences between the Collection and Collections classes in Java?
209. What are heterogeneous objects in Java, and how are they related to collections?
210. Explain the extra methods available in the LinkedList class that are not present in the ArrayList class and are used for creating Queue and Stack in Java.
211. What is the default size of a Vector in Java?
212. How does a Vector dynamically increase in size in Java, and what is the formula behind it?
213. Differentiate between the "peek" and "pop" methods of the Stack class in Java.
214. What is the default size of an ArrayList in Java?
215. How can you dynamically increase the size of an ArrayList in Java, and what is the formula for it?
216. Explain the differences between ArrayList and LinkedList in Java.
217. Describe the internal structure of an ArrayList in Java.
218. Describe the internal structure of a LinkedList in Java.
219. What is the load factor in an ArrayList in Java?
220. What is the threshold in an ArrayList in Java?
221. Provide the formula used to calculate the new size of an ArrayList in Java.
222. Why is an ArrayList considered slow for modifications in Java?
223. Explain the mostly used methods of the List interface in Java.
224. Describe how to convert an array to an ArrayList in Java.
225. Compare and contrast ArrayList and Vector in Java.
226. What are legacy classes in Java Collections?
227. In which version of Java was ArrayList introduced?
228. Compare and contrast arrays, ArrayList, and LinkedList in Java.
229. What is meant by insertion order in Java?
230. How do you sort an ArrayList in Java?
231. Is ArrayList synchronized in Java?
232. How can you make an ArrayList synchronized in Java?
233. Can you provide examples of situations where ArrayList is commonly used in Java?
234. What is a Stack, and what is a Vector class in Java?
235. Why are Stack and Vector classes used less frequently compared to List classes in Java?
236. Which implemented class of the List interface is typically used to design a Queue in Java?
237. What is the purpose of the RandomAccess interface implemented by List classes in Java?
238. Which List class is preferred in a multi-threaded application in Java?
239. What is the difference between "new ArrayList<>()" and "new ArrayList<>(size)" in Java, and can you explain with examples?
240. Which package do collection classes belong to in Java?
241. Explain the difference between "import java.util.*" and "import java.util.ArrayList;" in Java.
242. What is an Iterable, and what is an Iterator in Java?
243. When should you use an Iterator instead of a "for each" loop in Java?
244. How can you iterate through a List in reverse order in Java?
245. What are the differences between an Array and an ArrayList in Java?
246. In which situations is an Array or an ArrayList best suited in Java?
247. Why does an array start with an index of 0 in Java?
248. Can you add any type of element to an ArrayList in Java?
249. How can you make an ArrayList type-safe in Java?
250. What is the understanding of the Collection diagram, including various interfaces and classes in Java?
251. What is the time complexity of operations for Array and ArrayList in Java? For example, searching with an index is O(1), but without an index, it's O(n) in the worst case.
252. What is the understanding of the basic methods in the Collection interface in Java?
253. What are the extra methods available in each interface, for example, List, in Java?
254. What is an Iterable, and why is it important in Java?
255. How do you understand extra methods available in each interface, such as List, in Java?
256. What is an Iterable in Java?
257. In which situations is an Array preferred in Java?
258. In which situations is an ArrayList preferred in Java?

## CONSTRUCTOR	

259. What is the primary use of constructors in Java?
260. Explain the concept of a default constructor in Java.
261. What is a parameterized constructor in Java, and can you explain its properties?
262. What is a BitSet in Java, and what is its purpose?
263. How does your code behave when both a default constructor and a parameterized constructor are present in a Java class?
264. Define constructor overloading, constructor overriding, and constructor chaining in Java.
265. Why are "this" and "super" used in constructors in Java? What access modifiers can be used with constructors?
266. Is it possible to give a constructor a different name other than the class name in Java? Explain what a default constructor is.
267. What is a parameterized constructor in Java, and how is object creation related to constructors?
268. Explain the logical flow of constructors in the context of inheritance in Java. Is there a return type for constructors?
269. What is a private constructor, a static constructor, and a final constructor in Java?
270. Can you have an abstract constructor, and can constructors exist within interfaces in Java?
271. Is it possible to have both "this" and "super" in the same constructor in Java?
272. Can you call a subclass constructor from a superclass constructor in Java? Can an abstract class in Java have a constructor?
273. How are exceptions handled in constructors in Java?
274. Explain the different types of constructors available in Java.
275. Is it possible to have a constructor inside an abstract class in Java?
276. Explain the concept of constructor chaining in Java.

## EXCEPTION HANDLING

277. Explain the concepts of try-catch, try with multiple catch blocks, and try with resources in Java.
278. Describe the hierarchy of exceptions in Java.
279. Differentiate between an exception and an error in Java.
280. What is the difference between a runtime exception and a compile-time (CE) exception in Java?
281. Explain the differences between checked exceptions and unchecked exceptions in Java.
282. Which exceptions are children of checked exceptions in Java?
283. Describe the usage and purpose of try-catch-finally blocks in Java.
284. Provide examples of errors in Java.
285. Can you control errors in Java, and how would you do so?
286. Explain the usage of "throw" and "throws" in Java for exception handling.
287. Can you use "try" without a "catch" block in Java?
288. Explain the concept of "try with resources" in Java.
289. What types of resources can be used in a "try with resources" block in Java?
290. How can you create custom exceptions in Java?
291. Describe the process of throwing an exception in Java.
292. Explain the concept of checked and unchecked exceptions in the context of method overriding in Java.
293. What would happen if an unchecked exception is not handled properly in Java?
294. Discuss the hierarchy of exceptions in Java.
295. What is Exception Propagation, and how does it work in Java?

## SERVLET & JSP

296. Explain the life cycle of a servlet in Java.
297. Describe the hierarchy of servlet classes in Java.
298. What is the purpose of the init() method in the servlet's life cycle?
299. How do servlets work in conjunction with JSP (Java Server Pages)?
300. Explain the life cycle of a JSP (Java Server Pages) in Java.
301. What is the Scriplet tag in JSP, and how is it used?
302. List and explain the various objects available in JSP.
303. Does every new request create a new thread of the servlet in Java?

## MULTI-THREADING

304. Explain the concepts of the Thread class, Runnable interface, and Callable interface in Java.
305. What are the main differences between the Runnable and Callable interfaces in Java?
306. Describe different ways of creating threads in Java.
307. Discuss the differences between multithreading methods like wait, notify, and notifyAll in Java.
308. Explain the concepts of Executor, Executor Service, Thread Pool Executor, Thread Pool Task Executor, Future, and FutureTask in Java.
309. Describe the Producer and Consumer problem in the context of multithreading.
310. Explain the concepts of CountdownLatch and CyclicBarrier in Java.
311. What are the key differences between the ReentrantLock and synchronized keyword in Java?
312. Why must wait() and notify() methods be called from a synchronized block, and why are these methods part of the Object class in Java?
313. Compare Collection.synchronized() and concurrent collections in Java.
314. Discuss the differences between synchronized blocks and synchronized methods in Java.
315. Explain the use of a log object within a synchronized block in Java.
316. What is static synchronized in Java, and how is it used?
317. Describe how to implement synchronization without using the synchronized keyword or any other consistent or synchronized data structure in Java.
318. In which version of Java was the Executor Service included?
319. How can you share a copy of a single object among multiple threads without making that object static and final in Java?
320. Explain the concurrent package in the context of multithreading in Java.
321. Discuss the differences between the sleep() and wait() methods in Java.
322. Explain the concepts of volatile and thread-local variables in Java.
323. What are the differences between a thread and a process in Java?
324. Describe the lifecycle of a thread in Java.
325. Differentiate between the yield() and join() methods in Java.
326. How can you create a thread in Java without using the Runnable interface and Thread class?
327. What happens to a thread once it has completed its execution, and will it be garbage collected in Java?

## SPRING BOOT

328. Explain the concepts of Filters and Interceptors in the context of web applications.
329. What is the purpose of the @SpringBootApplication annotation in Spring Boot?
330. Describe the usage of @GetMapping, @PostMapping, @PutMapping, @DeleteMapping, and @RequestMapping annotations in Spring Boot.
331. What is the role of the @Controller annotation in Spring Boot?
332. Explain the @RestController annotation in Spring Boot.
333. How is the @Autowired annotation used in Spring Boot?
334. What is the purpose of the @Configuration annotation in Spring Boot?
335. Describe the usage of the @ComponentScan annotation in Spring Boot.
336. Explain the role of the @Bean annotation in Spring Boot.
337. Describe the usage of the @Component, @Repository, and @Service annotations in Spring Boot.
338. How is the @ExceptionHandler annotation used in Spring Boot?
339. What is the significance of the @Service annotation in Spring Boot?
340. Compare Spring Boot with the traditional Spring framework.
341. Explain the concepts of Spring Boot Starter dependencies and Spring Boot dependency management.
342. What is Spring Initializer, and how can it be used?
343. Can Spring Boot be used to create non-web projects? If so, how?
344. How can you change the default port used by a Spring Boot application?
345. Is it possible to override or replace the embedded Tomcat server in Spring Boot? Why would you choose to do so?
346. What are the reasons for using a separate Tomcat server instead of the default embedded one in Spring Boot?
347. How can you create different properties files for each environment in Spring Boot?
348. Explain the concept of Actuators in Spring Boot.
349. How do you enable Actuators in a Spring Boot application?
350. What is the process for enabling debugging logs in Spring Boot?
351. What is Dependency Injection in Spring Boot, and how is it achieved?
352. Explain the concept of an IOC (Inversion of Control) container in Spring Boot.
353. What are the required properties when using JPA (Java Persistence API) dependencies in the pom.xml file?
354. How can you disable a specific auto-configuration in Spring Boot?
355. Explain the concept of packaging a Spring Boot application as a JAR or WAR file.
356. What is the purpose of Spring DevTools in Spring Boot?
357. Should configuration be defined using a .properties file or a .yaml file in Spring Boot, and why?
358. What are Spring Boot starters, and what are some available starters?
359. When and why would you use profiles in Spring Boot?
360. What is Thymeleaf, and how is it used in Spring Boot?

## Modern Java Interview Questions

# Java Full Stack Senior Engineer — Interview Questions and Answers

## Section 1: Core Java (Collections, Threading, OOPS)

### Collections

1. **Difference between List, Set, and Map?**
- **List**: Ordered, allows duplicates (Ex: `ArrayList`)
- **Set**: Unordered, no duplicates (Ex: `HashSet`)
- **Map**: Key-value pairs, unique keys (Ex: `HashMap`)

2. **Difference between HashMap and ConcurrentHashMap?**
- **HashMap**: Not thread-safe
- **ConcurrentHashMap**: Thread-safe, locks at bucket level

3. **What is HashSet backed by?**
- HashSet uses a **HashMap** internally

4. **Difference between ArrayList and LinkedList?**
- **ArrayList**: Fast random access (O(1)), slower insert/delete
- **LinkedList**: Slow random access (O(n)), faster insert/delete at start/middle

5. **Fail-fast vs Fail-safe?**
- **Fail-fast**: Throws `ConcurrentModificationException` (e.g., `ArrayList`)
- **Fail-safe**: Works on a copy (e.g., `ConcurrentHashMap`)

6. **Difference between HashMap and Hashtable?**
- **HashMap**: Not synchronized
- **Hashtable**: Synchronized (legacy)

7. **Difference between TreeMap and HashMap?**
- **TreeMap**: Sorted by keys (O(log n))
- **HashMap**: Unordered (O(1))

8. **What is Comparable vs Comparator?**
- **Comparable**: Natural ordering (`compareTo()` inside class)
- **Comparator**: Custom ordering (external)

9. **What is BlockingQueue?**
- Thread-safe queue that blocks when empty/full (Ex: `ArrayBlockingQueue`)

### Threading

1. **Difference between Runnable and Callable?**
- **Runnable**: No result, no exception
- **Callable**: Returns result, can throw exception

2. **Synchronized vs Lock?**
- **Synchronized**: Simpler, intrinsic lock
- **Lock (ReentrantLock)**: Explicit locking, tryLock, fair lock

3. **What is volatile keyword?**
- Ensures visibility of changes to variables across threads

4. **Difference between wait(), sleep(), and yield()?**
- **wait()**: Releases lock, inter-thread communication
- **sleep()**: Pauses thread, holds lock
- **yield()**: Hints scheduler to switch thread (no guarantee)

5. **Thread-safe Singleton implementation?**
```java
public class Singleton {
    private static volatile Singleton instance;
    private Singleton() {}
    public static Singleton getInstance() {
        if (instance == null) {
            synchronized (Singleton.class) {
                if (instance == null) instance = new Singleton();
            }
        }
        return instance;
    }
}
```

6. **Difference between ExecutorService and ForkJoinPool?**
- **ExecutorService**: Thread pool for independent tasks
- **ForkJoinPool**: Divide and conquer tasks (work stealing)

7. **What is ThreadLocal?**
- Provides thread-confined variables (one copy per thread)

### OOPS

1. **4 Pillars of OOPS?**
- Encapsulation, Abstraction, Inheritance, Polymorphism

2. **Abstract class vs Interface?**
- **Abstract**: Can have fields, constructor, behavior
- **Interface**: Only method signatures (pre-Java 8), supports multiple inheritance

3. **Overloading vs Overriding?**
- **Overloading**: Same method name, different params (compile time)
- **Overriding**: Same signature, subclass modifies (runtime)

4. **What is encapsulation?**
- Hiding internal details and exposing only necessary parts (via getters/setters)

5. **What is polymorphism?**
- Same method name behaves differently (compile/runtime)

6. **What is composition vs inheritance?**
- **Composition**: HAS-A relationship (more flexible)
- **Inheritance**: IS-A relationship (tight coupling)

7. **What is marker interface?**
- Interface with no methods (Ex: `Serializable`)

## Section 2: Java 8, 9, 10, 11+ Features

### Java 8

1. **What is a Lambda Expression?**
- A concise way to represent functional interfaces

2. **What is a Functional Interface?**
- Interface with exactly one abstract method

3. **Difference between map() and flatMap()?**
- **map()**: Transforms each element
- **flatMap()**: Flattens nested structures

4. **What is Optional?**
- Container to avoid `NullPointerException`

5. **Default and Static methods in Interface?**
- **Default**: Provide method body
- **Static**: Utility methods

6. **Stream API?**
- Process sequences of elements using functional-style ops

7. **Method Reference?**
- Short syntax for lambdas

8. **Date and Time API?**
- Immutable, thread-safe (LocalDate, LocalDateTime)

9. **Predicate, Function, Supplier, Consumer?**
- Functional interfaces in java.util.function

10. **What is Collectors.toMap() and Collectors.groupingBy()?**
- Terminal operations for collecting results into maps/groups

11. **Difference between intermediate and terminal Stream operations?**
- **Intermediate**: map(), filter() → return Stream
- **Terminal**: collect(), forEach(), reduce() → return result

### Java 9

1. **Module System (Project Jigsaw)?**
- Split JDK into modules

2. **JShell?**
- Interactive REPL for Java

3. **Stream API Enhancements?**
- `takeWhile()`, `dropWhile()`, `ofNullable()`

4. **Optional.or() method?**
- Provides fallback Optional

### Java 10

1. **Local variable type inference (var)?**
```java
var list = new ArrayList<String>();
```

2. **Unmodifiable collections (copyOf)?**
```java
List<String> immutableList = List.copyOf(list);
```

### Java 11

1. **New String methods?**
- `isBlank()`, `lines()`, `strip()`, `repeat()`

2. **HTTP Client API?**
- Simplified HTTP calls (replaces HttpURLConnection)

### Java 12+

1. **Switch Expressions** (Java 14)
2. **Records** (Java 16)
3. **Text blocks** (Java 15)
4. **Pattern Matching for instanceof** (Java 16)
5. **Sealed Classes** (Java 17)


Perfect — let's move to **Section 4: Microservices**  
Here’s a **focused list of most-asked Microservices interview questions with short crisp answers** for senior roles.  

---

# 📂 **Microservices**

### 1️⃣ What is Microservices Architecture?  
- Design style where an application is a **collection of small, loosely coupled services**, each responsible for a single business capability.

---

### 2️⃣ Monolithic vs Microservices  
| Monolithic | Microservices |
|------------|---------------|
| Single deployable unit | Independent deployable services |
| Tight coupling | Loose coupling |
| Difficult to scale specific parts | Independent scaling |
| Technology lock-in | Polyglot (multiple tech possible) |

---

### 3️⃣ How do Microservices communicate?  
- **Synchronous**: REST, gRPC  
- **Asynchronous**: Kafka, RabbitMQ, JMS

---

### 4️⃣ What is service discovery?  
- Process where services **register themselves** and **discover other services dynamically**  
Example: **Eureka**, **Consul**, **Zookeeper**

---

### 5️⃣ API Gateway - Why is it needed?  
- Entry point for all clients → handles routing, load balancing, security, rate limiting  
Examples: **Spring Cloud Gateway**, **Zuul**, **Kong**, **NGINX**

---

### 6️⃣ How to handle failures in Microservices?  
- **Circuit Breaker** (Resilience4j, Hystrix)  
- **Retry**, **Fallback**, **Timeouts**, **Bulkhead pattern**  
- **Service mesh** (Istio, Linkerd)

---

### 7️⃣ What is Circuit Breaker Pattern?  
- Prevents a service from making calls to a failing service.  
If failures cross a threshold → circuit “opens” → skips calls → avoids cascading failure.

---

### 8️⃣ How to handle distributed transactions?  
- **Saga Pattern** (Orchestration / Choreography)  
- **Two-Phase Commit (2PC)** — less recommended due to complexity and locking.

---

### 9️⃣ What is Saga Pattern?  
- **Orchestration**: Central coordinator controls transactions  
- **Choreography**: Services communicate via events (no central coordinator)

---

### 1️⃣0️⃣ What is Idempotency?  
- Same request can be executed multiple times → result remains same  
Example: `DELETE /user/1` should always return success even if user is already deleted

---

### 1️⃣1️⃣ What is eventual consistency?  
- In distributed systems → all services **will become consistent over time**, but not immediately (vs strong consistency)

---

### 1️⃣2️⃣ How do you secure Microservices?  
- OAuth2, OpenID Connect  
- JWT Tokens (Stateless auth)  
- API Gateway as security layer  
- Mutual TLS (mTLS) between services

---

### 1️⃣3️⃣ What is service mesh?  
- Dedicated infrastructure layer to handle **service-to-service communication**  
Features: **Load balancing, retries, security, telemetry**  
Examples: **Istio**, **Linkerd**

---

### 1️⃣4️⃣ Key Microservice Design Patterns?  
✅ Circuit Breaker  
✅ API Gateway  
✅ Saga Pattern  
✅ Strangler Fig Pattern (migrating monolith to microservices)  
✅ Bulkhead  
✅ Retry  
✅ Service Discovery

---

### 1️⃣5️⃣ What is config server in Microservices?  
- Centralized external configuration management  
Example: **Spring Cloud Config Server**

---

### 1️⃣6️⃣ What is Resilience4j?  
- Lightweight fault-tolerance library for Java  
Supports: Circuit Breaker, Retry, RateLimiter, Bulkhead

---

### 1️⃣7️⃣ What is distributed tracing?  
- Track requests across multiple services  
Tools: **Zipkin**, **Jaeger**, **Sleuth**

---

### 1️⃣8️⃣ How do you monitor Microservices?  
- **Logging**: ELK (Elasticsearch, Logstash, Kibana)  
- **Tracing**: Zipkin, Jaeger  
- **Metrics**: Prometheus, Grafana  
- **Health Checks**: /actuator/health (Spring Boot)

---

### 1️⃣9️⃣ How does load balancing work?  
- **Client-side** (Ribbon)  
- **Server-side** (API Gateway, NGINX)

---

### 2️⃣0️⃣ How to version Microservices APIs?  
- URI versioning (`/api/v1/users`)  
- Request Header versioning

---

### 2️⃣1️⃣ How to manage dependencies between microservices?  
- Keep services **loosely coupled**  
- Use **asynchronous communication** where possible (events/Kafka)
---

## 🟠 **Oracle / SQL**

### 1️⃣ Difference between `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`  
- `INNER JOIN`: only matching rows  
- `LEFT JOIN`: all rows from left + matching from right  
- `RIGHT JOIN`: all rows from right + matching from left

---

### 2️⃣ What is normalization?  
- Organizing data to reduce **redundancy** and improve **data integrity**  
- Normal forms: **1NF**, **2NF**, **3NF**, **BCNF**

---

### 3️⃣ ACID properties  
✅ **Atomicity** — All or nothing  
✅ **Consistency** — Valid state  
✅ **Isolation** — Concurrent txn isolation  
✅ **Durability** — Persist after commit

---

### 4️⃣ Difference between `WHERE` and `HAVING`?  
- `WHERE`: filters rows **before grouping**  
- `HAVING`: filters **after grouping**

---

### 5️⃣ Index vs Unique Key vs Primary Key  
| Feature | Index | Unique Key | Primary Key |
|---------|-------|-----------|-------------|
| Uniqueness | No | Yes | Yes |
| NULL allowed | Yes | Yes (1 NULL) | No |
| Count allowed | Many | Many | 1 |

---

### 6️⃣ How to optimize SQL query?  
- Proper indexes  
- Avoid `SELECT *`  
- Use **EXISTS** over **IN** (in large subqueries)  
- Optimize joins  
- Analyze execution plan

---

### 7️⃣ What is execution plan?  
- Shows how SQL engine **executes a query** (index scan, full scan etc.)

---

### 8️⃣ Difference between clustered and non-clustered index?  
- **Clustered**: rearranges actual data (1 per table)  
- **Non-clustered**: separate index structure (many per table)

---

## 🟢 **NoSQL / MongoDB**

### 9️⃣ SQL vs NoSQL?  
| SQL | NoSQL |
|-----|-------|
| Relational | Non-relational |
| Fixed schema | Flexible schema |
| Joins | No joins |
| ACID | Eventual Consistency (CAP Theorem) |

---

### 1️⃣0️⃣ CAP Theorem  
✅ **Consistency** — all nodes same data  
✅ **Availability** — system always responsive  
✅ **Partition Tolerance** — continues despite network splits  
👉 Can have **at most 2 out of 3** in distributed DB

---

### 1️⃣1️⃣ What is Document-Oriented DB?  
- Stores data as **JSON-like documents**  
Example: **MongoDB**

---

### 1️⃣2️⃣ Key features of MongoDB  
✅ No schema / dynamic schema  
✅ JSON-like documents (BSON)  
✅ High availability (replica sets)  
✅ Horizontal scaling (sharding)

---

### 1️⃣3️⃣ What is sharding?  
- **Horizontal partitioning** → split large collections across multiple servers

---

### 1️⃣4️⃣ What is replication in MongoDB?  
- Copies data across multiple servers (replica set) → High availability & failover

---

### 1️⃣5️⃣ MongoDB vs RDBMS  
| MongoDB | RDBMS |
|---------|-------|
| JSON docs | Tables + rows |
| No joins (embedding/refs) | Joins |
| Horizontal scaling | Vertical scaling |
| Schema-less | Schema-bound |

---

### 1️⃣6️⃣ Index types in MongoDB  
✅ Single Field Index  
✅ Compound Index  
✅ Multikey Index (arrays)  
✅ Text Index (for search)  
✅ Geospatial Index

---

### 1️⃣7️⃣ What is aggregation in MongoDB?  
- Pipeline-based processing (like SQL GROUP BY, JOIN)  
Operators: `$match`, `$group`, `$project`, `$sort`

---

### 1️⃣8️⃣ How does MongoDB ensure durability?  
- **Journaling** — writes operations to journal before data files

---

### 1️⃣9️⃣ Transactions in MongoDB?  
- Since v4.0 → **Multi-document ACID transactions** (Replica sets)  
- v4.2 → Transactions across shards

---

### 2️⃣0️⃣ How does MongoDB handle large datasets?  
- Sharding → splits collection across shards  
- Aggregation pipelines process large datasets efficiently

---

### 1️⃣ What is AWS?  
- Amazon Web Services — a **cloud computing platform** providing **IaaS**, **PaaS**, and **SaaS**  
- Services: **Compute, Storage, Database, Networking, Security, Analytics**

---

### 2️⃣ EC2 vs S3 vs RDS vs Lambda  
| Service | Purpose |
|---------|---------|
| **EC2** | Virtual machine (compute) |
| **S3** | Object storage |
| **RDS** | Relational database (managed) |
| **Lambda** | Serverless function execution |

---

### 3️⃣ What is IAM?  
- **Identity and Access Management** — manage users, roles, permissions  
✅ **Least privilege principle**  
✅ **IAM roles** (for apps / services)

---

### 4️⃣ What is an S3 bucket?  
- **Object storage service** for files  
✅ Versioning  
✅ Lifecycle policies (auto delete/archive)  
✅ Encryption (SSE-S3, SSE-KMS)

---

### 5️⃣ What is an Elastic Load Balancer (ELB)?  
- Distributes incoming traffic across multiple targets (EC2, containers)  
Types: **Application LB**, **Network LB**, **Gateway LB**

---

### 6️⃣ What is Auto Scaling?  
- Automatically **adds/removes instances** based on load

---

### 7️⃣ What is VPC?  
- **Virtual Private Cloud** — isolated cloud network  
✅ Subnets (public/private)  
✅ Route tables  
✅ Security groups  
✅ NAT Gateway (internet for private subnet)

---

### 8️⃣ What is AWS Lambda?  
- **Serverless compute** → run code without managing servers  
✅ Pay per execution  
✅ Event-driven (S3, API Gateway, SNS triggers)

---

### 9️⃣ Difference between SNS and SQS?  
| Feature | SNS | SQS |
|---------|-----|-----|
| Pattern | Pub/Sub | Queue |
| Subscribers | Multiple | 1 receiver per message |
| Push vs Pull | Push | Polling |

---

### 🔟 What is CloudFormation?  
- **Infrastructure as Code (IaC)** — provision AWS resources via templates (YAML/JSON)

---

### 1️⃣1️⃣ What is CloudWatch?  
- **Monitoring service** for metrics, logs, alarms

---

### 1️⃣2️⃣ What is Route 53?  
- AWS **DNS service** (domain registration, routing)

---

### 1️⃣3️⃣ What is Elastic Beanstalk?  
- **PaaS** — deploy Java, Node.js, Python apps easily → AWS manages infra

---

### 1️⃣4️⃣ What is EBS?  
- **Elastic Block Store** — persistent disk volumes for EC2

---

### 1️⃣5️⃣ Difference between RDS and DynamoDB?  
| Feature | RDS | DynamoDB |
|---------|-----|----------|
| Type | SQL (MySQL, Postgres…) | NoSQL |
| Scaling | Vertical | Horizontal (auto scaling) |
| Joins | Yes | No |
| Transactions | Yes | Limited (supported) |

---

### 1️⃣6️⃣ What is Amazon Aurora?  
- **High-performance RDS** (MySQL/Postgres compatible) — faster and more scalable

---

### 1️⃣7️⃣ What is AWS Secrets Manager?  
- Securely store/manage **API keys, passwords, tokens** (auto-rotation)

---

### 1️⃣8️⃣ AWS services for Microservices?  
✅ EC2 + ALB  
✅ ECS (Containers) / EKS (Kubernetes)  
✅ API Gateway + Lambda  
✅ DynamoDB / Aurora  
✅ S3 (Storage)  
✅ CloudWatch (Monitoring)

---

### 1️⃣9️⃣ What is ECR?  
- **Elastic Container Registry** — Docker image repository (like DockerHub)

---

### 2️⃣0️⃣ What is AWS Fargate?  
- **Serverless container service** (no EC2 management)

---

### 2️⃣1️⃣ What is SSM Parameter Store?  
- Securely store **configurations and secrets**

---

# 📂 ** Angular (Versions, Features, Concepts)**

---

### 1️⃣ What is Angular?  
- **Angular** is a **TypeScript-based front-end framework** (developed by Google) for building **single-page applications (SPA)**

---

### 2️⃣ AngularJS vs Angular (2+)  
| Feature | AngularJS (1.x) | Angular (2+) |
|---------|-----------------|--------------|
| Language | JavaScript | TypeScript |
| Architecture | MVC | Component-based |
| Data Binding | Two-way | Two-way (but improved) |
| Mobile Support | No | Yes |
| Performance | Slower | Faster (AOT + Tree Shaking) |

---

### 3️⃣ Key building blocks of Angular  
✅ **Modules** (NgModules) — group related components/services  
✅ **Components** — UI + logic  
✅ **Templates** — HTML + directives  
✅ **Services** — business logic  
✅ **Dependency Injection** — inject services  
✅ **Routing** — navigation

---

### 4️⃣ What is a Component?  
- Building block → **HTML template + class + metadata**  
```typescript
@Component({ selector: 'app-root', templateUrl: './app.component.html' })
export class AppComponent {}
```

---

### 5️⃣ Lifecycle hooks  
✅ `ngOnInit()` → component initialization  
✅ `ngOnDestroy()` → cleanup  
✅ `ngOnChanges()`, `ngDoCheck()`, etc.

---

### 6️⃣ What is Data Binding?  
| Type | Example |
|------|---------|
| Interpolation | `{{ name }}` |
| Property binding | `[disabled]="isDisabled"` |
| Event binding | `(click)="onClick()"` |
| Two-way binding | `[(ngModel)]="name"` |

---

### 7️⃣ What are Directives?  
✅ **Structural** → `*ngIf`, `*ngFor` (change DOM structure)  
✅ **Attribute** → `[ngClass]`, `[ngStyle]` (change appearance/behavior)

---

### 8️⃣ What is Angular CLI?  
- Command-line tool to scaffold, build, test, deploy apps  
`ng new`, `ng serve`, `ng build`

---

### 9️⃣ What is Dependency Injection?  
- **Inject services** into components for loose coupling  
```typescript
constructor(private userService: UserService) {}
```

---

### 🔟 What is a Service?  
- Reusable **business logic** class  
- Singleton (when provided in `root`)

---

### 1️⃣1️⃣ What is Routing?  
- Navigate between components  
✅ `RouterModule`  
✅ Routes array  
✅ `routerLink`

---

### 1️⃣2️⃣ Lazy Loading  
- Load feature modules **on demand** (improves performance)

---

### 1️⃣3️⃣ What is Ahead-of-Time (AOT) compilation?  
- Compiles app **during build time** → faster runtime

---

### 1️⃣4️⃣ What are Observables?  
- Part of **RxJS** — handle **async streams** (HTTP, events)  
✅ `subscribe()`  
✅ `map()`, `filter()`, `mergeMap()`

---

### 1️⃣5️⃣ Difference between Subject and BehaviorSubject  
| Subject | BehaviorSubject |
|---------|-----------------|
| No initial value | Initial value |
| Emits to subscribers | Emits last + new values |

---

### 1️⃣6️⃣ Features by Angular version

| Version | Features |
|---------|----------|
| Angular 2 | Initial release |
| Angular 4 | Smaller bundles |
| Angular 5 | HttpClient module |
| Angular 6 | Angular Elements, CLI Workspaces |
| Angular 7 | Virtual scrolling, Drag & Drop |
| Angular 8 | Differential loading |
| Angular 9 | Ivy renderer (default) |
| Angular 10 | Optional strict typing |
| Angular 11 | Faster builds |
| Angular 12 | Nullish coalescing |
| Angular 13 | ESBuild, no ViewEngine |
| Angular 14 | Standalone components |
| Angular 15 | Directive composition |
| Angular 16 | Signals (reactivity model - preview) |
| Angular 17 | Full Signals, Deferred loading |

---

### 1️⃣7️⃣ What are Angular Signals (Angular 16/17)?  
- **Fine-grained reactivity model** (similar to React hooks)  
- Reactive state management → **automatic change detection**

---

### 1️⃣8️⃣ What are Pipes?  
- **Transform data in template**  
✅ Built-in: `date`, `uppercase`, `currency`  
✅ Custom Pipes

```typescript
{{ birthday | date:'shortDate' }}
```

---

### 1️⃣9️⃣ What is a Guard?  
- Control route access → **AuthGuard**, **CanActivate**, **CanDeactivate**

---

### 2️⃣0️⃣ Unit testing in Angular?  
- **Jasmine** (framework)  
- **Karma** (test runner)  
- TestBed → create test modules

---

# 📂 **HTML (HyperText Markup Language)**

---

### 1️⃣ What is HTML?  
- **Markup language** to define **structure** of web pages  
- Uses **tags** to represent content (headings, paragraphs, links…)

---

### 2️⃣ What’s the difference between `<div>` and `<span>`?  
| Element | Purpose |
|---------|---------|
| `<div>` | Block-level container |
| `<span>` | Inline container |

---

### 3️⃣ What is semantic HTML?  
- Using **meaningful tags** to improve readability and accessibility  
✅ `<article>`, `<section>`, `<header>`, `<footer>`, `<nav>`

---

### 4️⃣ What is the difference between `<section>`, `<article>`, `<aside>`?  
| Tag | Use |
|-----|-----|
| `<section>` | Thematic grouping |
| `<article>` | Self-contained content |
| `<aside>` | Sidebar, related content |

---

### 5️⃣ What is the difference between `<em>` and `<i>`, `<strong>` and `<b>`?  
| Tag | Purpose |
|-----|---------|
| `<em>` | Emphasis (semantic) |
| `<i>` | Italic (styling) |
| `<strong>` | Strong importance (semantic) |
| `<b>` | Bold (styling) |

---

### 6️⃣ What are the different types of form input elements?  
✅ `<input type="text">`, `password`, `email`, `number`, `checkbox`, `radio`, `file`  
✅ `<textarea>`, `<select>`, `<button>`

---

### 7️⃣ Difference between GET and POST method in forms?  
| GET | POST |
|-----|------|
| Data in URL | Data in body |
| Limited size | Larger data |
| Bookmarkable | Not bookmarkable |
| Less secure | More secure |

---

### 8️⃣ What are HTML5 new features?  
✅ **Semantic tags** → `<section>`, `<article>`, `<nav>`  
✅ **Audio/Video** → `<audio>`, `<video>`  
✅ **Canvas**  
✅ **LocalStorage / SessionStorage**  
✅ **Form enhancements** (input types, validation)

---

### 9️⃣ What is the difference between `id` and `class`?  
| Attribute | Purpose |
|-----------|---------|
| `id` | Unique identifier |
| `class` | Can be reused |

---

### 🔟 What is the difference between block vs inline elements?  
| Block | Inline |
|-------|--------|
| Takes full width | Takes content width |
| Starts on new line | Same line |
| `<div>`, `<p>`, `<section>` | `<span>`, `<a>`, `<strong>` |

---

### 1️⃣1️⃣ What is DOCTYPE?  
- Declares **HTML version**  
```html
<!DOCTYPE html> <!-- HTML5 -->
```

---

### 1️⃣2️⃣ What is meta tag?  
✅ Metadata about document (charset, viewport, SEO)

```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

---

### 1️⃣3️⃣ How to make a link open in new tab?  
```html
<a href="url" target="_blank">Link</a>
```

---

### 1️⃣4️⃣ How to embed an image?  
```html
<img src="image.jpg" alt="Description">
```

---

### 1️⃣5️⃣ How to embed a video?  
```html
<video controls>
  <source src="video.mp4" type="video/mp4">
</video>
```

# 📂 **CSS (Cascading Style Sheets)**

---

### 1️⃣ What is CSS?  
- **Cascading Style Sheets** used to style and lay out web pages  
- Controls **layout**, **colors**, **fonts**, **spacing** of HTML elements

---

### 2️⃣ What are the different ways to apply CSS to a webpage?  
| Method | Description |
|--------|-------------|
| Inline | `<element style="property: value;">` |
| Internal | `<style>...</style>` inside `<head>` |
| External | Link to `.css` file using `<link>` |

---

### 3️⃣ What is the Box Model in CSS?  
- Defines how **content**, **padding**, **border**, and **margin** are displayed around elements

---

### 4️⃣ What is the difference between `padding` and `margin`?  
| Property | Description |
|----------|-------------|
| `padding` | Space between content and border (inside element) |
| `margin` | Space between element’s border and neighboring elements (outside element) |

---

### 5️⃣ What are CSS selectors?  
- **Selectors** define which HTML elements are targeted by CSS  
✅ **Element selector** → `div {}`  
✅ **Class selector** → `.class-name {}`  
✅ **ID selector** → `#id-name {}`  
✅ **Attribute selector** → `[type="text"] {}`

---

### 6️⃣ What is the difference between `class` and `id` in CSS?  
| Attribute | Purpose |
|-----------|---------|
| `class` | Reusable, can be applied to multiple elements |
| `id` | Unique, should be applied to only one element |

---

### 7️⃣ What are pseudo-classes and pseudo-elements?  
| Type | Description | Example |
|------|-------------|---------|
| Pseudo-class | Defines element’s state | `a:hover`, `:first-child` |
| Pseudo-element | Targets specific part of an element | `::before`, `::after` |

---

### 8️⃣ What are the different types of position in CSS?  
| Property | Description |
|----------|-------------|
| `static` | Default, normal flow |
| `relative` | Positioned relative to its normal position |
| `absolute` | Positioned relative to the nearest positioned ancestor |
| `fixed` | Positioned relative to the viewport |
| `sticky` | Sticks to the top of the viewport on scroll |

---

### 9️⃣ What is Flexbox?  
- **Layout model** for building one-dimensional layouts (horizontal or vertical)  
✅ **Flex container** → `display: flex`  
✅ **Flex items** → Items inside flex container

---

### 🔟 What is Grid in CSS?  
- **Layout system** for creating two-dimensional layouts (rows and columns)  
✅ `display: grid`  
✅ **Grid lines**, **grid-template-columns**, **grid-template-rows**

---

### 1️⃣1️⃣ What is the difference between `inline`, `block`, and `inline-block`?  
| Display Type | Description |
|--------------|-------------|
| `inline` | Elements do not break the flow, occupy content width |
| `block` | Elements take full width of parent, break the flow |
| `inline-block` | Like `inline` but allows setting `width` and `height` |

---

### 1️⃣2️⃣ What is `z-index` in CSS?  
- **Controls stack order** of positioned elements  
✅ Higher `z-index` → closer to the front  
✅ Must have `position` set (e.g., `relative`, `absolute`)

---

### 1️⃣3️⃣ What are media queries in CSS?  
- Used for **responsive design**, applying styles based on **device characteristics**  
```css
@media (max-width: 600px) {
  body { background-color: lightblue; }
}
```

---

### 1️⃣4️⃣ What is `display: none` vs `visibility: hidden`?  
| Property | Effect |
|----------|--------|
| `display: none` | Removes the element from the document flow (not visible) |
| `visibility: hidden` | Hides the element but still takes up space in the layout |

---

### 1️⃣5️⃣ What is the `transition` property in CSS?  
- Used to **smoothly animate** a change in property values  
```css
transition: all 0.5s ease;
```

---

### 1️⃣6️⃣ What is the `transform` property in CSS?  
- Apply transformations (e.g., rotate, scale, translate) to elements  
```css
transform: rotate(45deg);
```

---

### 1️⃣7️⃣ What is the `box-shadow` property in CSS?  
- Adds shadow effects to elements  
```css
box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.5);
```

---

### 1️⃣8️⃣ What is the difference between `em` and `rem` in CSS?  
| Unit | Description |
|------|-------------|
| `em` | Relative to the **parent element’s font size** |
| `rem` | Relative to the **root element’s font size** (`<html>`) |

---

### 1️⃣9️⃣ What are `::before` and `::after` pseudo-elements in CSS?  
- Insert **content before** or **after** an element  
```css
element::before {
  content: "Prefix";
}
```

---

### 2️⃣0️⃣ What is CSS specificity?  
- Determines which CSS rule is applied when multiple rules target the same element  
- **ID** has higher specificity than **class**, and **class** has higher specificity than **element** selectors

---


Let’s move on to **Section 10: JavaScript**  
We’ll cover **key JavaScript concepts** and **commonly asked interview questions**.

---

# 📂 **JavaScript**

---

### 1️⃣ What is JavaScript?  
- A **scripting language** used for creating dynamic and interactive web pages  
- Works in the **browser** or on the **server-side** (with Node.js)

---

### 2️⃣ What are the data types in JavaScript?  
- **Primitive**: `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint`  
- **Reference**: `object`, `array`, `function`

---

### 3️⃣ What is the difference between `var`, `let`, and `const`?  
| Keyword | Scope | Reassignment | Hoisting |
|---------|-------|--------------|----------|
| `var`   | Function | Yes | Yes (initialized as `undefined`) |
| `let`   | Block | Yes | Yes (does not initialize) |
| `const` | Block | No | Yes (does not initialize) |

---

### 4️⃣ What is Hoisting in JavaScript?  
- **Hoisting** is JavaScript's behavior of moving **declarations** to the top of their scope during compilation (variables, functions)

---

### 5️⃣ What is a closure in JavaScript?  
- A **function** that retains access to its lexical scope (even after it is executed outside of that scope)  
```javascript
function outer() {
  let counter = 0;
  return function inner() {
    counter++;
    return counter;
  }
}
const increment = outer();
increment(); // 1
```

---

### 6️⃣ What is a promise in JavaScript?  
- An **asynchronous operation** that represents a value that may not be available yet  
- **States**: `pending`, `fulfilled`, `rejected`  
```javascript
let promise = new Promise((resolve, reject) => { 
  resolve('Success');
});
```

---

### 7️⃣ What is the difference between `==` and `===`?  
- **`==`** → Loose equality (performs type coercion)  
- **`===`** → Strict equality (does not perform type coercion)

---

### 8️⃣ What are arrow functions in JavaScript?  
- A **shorter syntax** for writing functions  
- Does not bind its own `this`, it inherits it from the surrounding context  
```javascript
const add = (a, b) => a + b;
```

---

### 9️⃣ What is the `this` keyword in JavaScript?  
- Refers to the **current object** in methods, or the **global object** in functions  
- In arrow functions, `this` is inherited from the **enclosing context**

---

### 🔟 What is event delegation in JavaScript?  
- A technique where a **parent element** listens for events on **child elements** to improve performance and reduce memory usage

---

### 1️⃣1️⃣ What are higher-order functions in JavaScript?  
- Functions that either take other functions as arguments or return them  
```javascript
function filterArray(arr, callback) {
  return arr.filter(callback);
}
```

---

### 1️⃣2️⃣ What is the `bind()` method in JavaScript?  
- **`bind()`** creates a **new function** that, when invoked, has its `this` set to the provided value  
```javascript
const obj = { name: 'John' };
const greet = function() { console.log(this.name); };
const boundGreet = greet.bind(obj);
boundGreet(); // John
```

---

### 1️⃣3️⃣ What is the event loop in JavaScript?  
- The **event loop** continuously checks the **call stack** for tasks to execute and then pushes tasks from the **callback queue** into the call stack

---

### 1️⃣4️⃣ What are JavaScript modules?  
- Used to **split code into smaller files** and use `import`/`export` syntax to share and access functionalities  
```javascript
// module.js
export const greet = () => console.log('Hello');
// app.js
import { greet } from './module';
```

---

### 1️⃣5️⃣ What is destructuring in JavaScript?  
- Allows unpacking values from arrays or properties from objects into variables  
```javascript
const person = { name: 'Alice', age: 25 };
const { name, age } = person;
```

---

### 1️⃣6️⃣ What is spread/rest syntax?  
- **Spread**: Unpacks elements from an array or object  
```javascript
const arr = [1, 2, 3];
const newArr = [...arr, 4];
```
- **Rest**: Collects multiple elements into an array  
```javascript
const sum = (...args) => args.reduce((a, b) => a + b, 0);
```

---

### 1️⃣7️⃣ What is `setTimeout()` and `setInterval()`?  
- **`setTimeout()`**: Executes a function after a specified delay (one-time)  
- **`setInterval()`**: Executes a function at specified intervals (repeatedly)  
```javascript
setTimeout(() => { console.log('Hello'); }, 1000);
setInterval(() => { console.log('Hello'); }, 1000);
```

---

### 1️⃣8️⃣ What is `localStorage` and `sessionStorage`?  
- **`localStorage`**: Stores data **permanently** (until deleted)  
- **`sessionStorage`**: Stores data for the duration of the **session**

---

### 1️⃣9️⃣ What is a `Map` in JavaScript?  
- A collection of **key-value pairs**, where keys can be any type (not just strings)  
```javascript
let map = new Map();
map.set('name', 'John');
```

---

### 2️⃣0️⃣ What is `reduce()` in JavaScript?  
- A **higher-order function** that **accumulates** array values into a single result  
```javascript
const sum = [1, 2, 3].reduce((acc, val) => acc + val, 0); // 6
```

# 📂 **Docker**

---

### 1️⃣ What is Docker?  
- **Docker** is an open-source platform that enables **developers** to automate the deployment of applications inside lightweight, portable containers  
- Containers bundle an application’s code, libraries, dependencies, and runtime together

---

### 2️⃣ What is a container in Docker?  
- A **container** is a **lightweight, standalone executable package** of software that includes everything needed to run it  
- It is based on a Docker **image** and can run on any machine with Docker installed

---

### 3️⃣ What is the difference between a Docker image and a Docker container?  
| Concept       | Docker Image                              | Docker Container                          |
|---------------|-------------------------------------------|-------------------------------------------|
| **Definition** | Read-only template with the application code, libraries, and dependencies | Running instance of an image |
| **Lifecycle**  | Created from a Dockerfile and stored in the Docker registry | Runs as a live, active process |
| **Persistence** | Immutable and versioned | Mutable, stores data and changes during runtime |

---

### 4️⃣ How does Docker work?  
- **Docker Engine** runs on the host machine, creating containers from images using `docker run`  
- Containers run the application inside an isolated environment, sharing the host OS kernel

---

### 5️⃣ What is a Dockerfile?  
- A **Dockerfile** is a text file that contains a series of commands used to **build a Docker image**  
- Defines instructions like which base image to use, which dependencies to install, and how to run the application

---

### 6️⃣ What is Docker Compose?  
- **Docker Compose** is a tool for defining and running multi-container Docker applications  
- Uses a YAML file (`docker-compose.yml`) to configure application services, networks, and volumes

---

### 7️⃣ What are Docker volumes?  
- **Volumes** are used to persist data generated by and used by Docker containers  
- They allow data to **survive container restarts** and be shared between containers

---

### 8️⃣ What is the difference between `CMD` and `ENTRYPOINT` in a Dockerfile?  
| Instruction  | CMD | ENTRYPOINT |
|--------------|-----|------------|
| **Purpose**  | Provides default arguments for the container | Defines the command to run within the container |
| **Flexibility** | Can be overridden at runtime | Cannot be overridden at runtime |

---

### 9️⃣ How do you scale applications using Docker?  
- Docker containers can be scaled by running multiple instances of the same container across different hosts or on the same host  
- **Docker Swarm** or **Kubernetes** are commonly used to manage scaling, load balancing, and high availability

---

### 🔟 What is Docker Swarm?  
- **Docker Swarm** is Docker’s native clustering and orchestration tool  
- It turns a group of Docker hosts into a **single virtual Docker host** and manages the deployment, scaling, and networking of containers

---

### 1️⃣1️⃣ What is a Docker registry?  
- A **Docker registry** is a **repository** where Docker images are stored and shared  
- The most common registry is **Docker Hub**, but private registries can also be used

---

### 1️⃣2️⃣ How do you connect a Docker container to a network?  
- Use the `--network` flag when running the container to attach it to a specific Docker network  
```bash
docker run --network my-network my-container
```

---

### 1️⃣3️⃣ What is the purpose of `docker ps`?  
- The **`docker ps`** command lists all **running** containers  
- To list all containers, including stopped ones, use `docker ps -a`

---

### 1️⃣4️⃣ What is the purpose of `docker exec`?  
- **`docker exec`** allows you to **execute commands** inside a running container  
```bash
docker exec -it container_name bash
```

---

### 1️⃣5️⃣ How do you remove unused Docker images, containers, and volumes?  
- Use the following commands to remove unused resources:  
```bash
docker system prune -a  # Remove unused containers, images, and networks
docker volume prune     # Remove unused volumes
docker container prune  # Remove stopped containers
```

---

### 1️⃣6️⃣ How do you expose a port from a Docker container?  
- Use the `-p` flag to map a port from the container to the host  
```bash
docker run -p 8080:80 my-container
```

---

### 1️⃣7️⃣ What is the Docker daemon?  
- The **Docker daemon** is a background service that manages Docker containers, images, networks, and volumes  
- It runs on the host machine and communicates with Docker clients via REST APIs

---

### 1️⃣8️⃣ What is Docker networking?  
- Docker provides multiple networking options for containers:  
  - **Bridge** (default)  
  - **Host**  
  - **None**  
  - **Custom networks**

---

### 1️⃣9️⃣ How do you debug a Docker container?  
- Use commands like `docker logs`, `docker exec`, and `docker inspect` to check container logs, run commands inside the container, and inspect container configuration

---

### 2️⃣0️⃣ What is multi-stage build in Docker?  
- **Multi-stage builds** allow you to **use multiple FROM statements** in a Dockerfile to create intermediate images, reducing the final image size and improving efficiency

---

# 📂 **Kubernetes**

---

### 1️⃣ What is Kubernetes?  
- **Kubernetes** is an **open-source container orchestration platform** that automates the deployment, scaling, and management of containerized applications  
- Provides a framework for running distributed systems resiliently, scaling applications as needed

---

### 2️⃣ What are Pods in Kubernetes?  
- A **Pod** is the smallest and simplest unit in Kubernetes that represents a **single instance of a running process** in a cluster  
- A Pod can contain one or more containers that share the same network namespace and storage volumes

---

### 3️⃣ What is a Kubernetes Node?  
- A **Node** is a physical or virtual machine in a Kubernetes cluster  
- It runs **Kubernetes components** and is responsible for running Pods and providing network connectivity to the containers

---

### 4️⃣ What is a ReplicaSet in Kubernetes?  
- A **ReplicaSet** ensures that a specified number of identical Pods are running at any given time  
- It maintains the **desired state** of the application and automatically creates or deletes Pods to meet that state

---

### 5️⃣ What is a Deployment in Kubernetes?  
- A **Deployment** provides declarative updates to Pods and ReplicaSets  
- Manages the lifecycle of Pods, allowing for **rolling updates** and easy rollbacks

---

### 6️⃣ What is a Service in Kubernetes?  
- A **Service** is an abstraction that defines a logical set of Pods and a policy by which to access them  
- It enables communication between Pods and other external or internal services

---

### 7️⃣ What is a ConfigMap in Kubernetes?  
- A **ConfigMap** is an API object used to store non-confidential data in key-value pairs  
- It can be used to store configuration settings that are consumed by Pods

---

### 8️⃣ What is a Secret in Kubernetes?  
- A **Secret** is similar to a ConfigMap but is intended for **storing sensitive information** like passwords, OAuth tokens, or SSH keys  
- Secrets are base64 encoded, but they are not automatically encrypted

---

### 9️⃣ What is a Namespace in Kubernetes?  
- A **Namespace** is a way to divide cluster resources between multiple users or applications  
- Useful for organizing resources and providing a scope for names (e.g., `dev`, `prod`, `test` environments)

---

### 🔟 What is Helm in Kubernetes?  
- **Helm** is a package manager for Kubernetes that allows you to define, install, and upgrade applications using **charts**  
- A **chart** is a package of pre-configured Kubernetes resources

---

### 1️⃣1️⃣ What is a StatefulSet in Kubernetes?  
- A **StatefulSet** is used to manage **stateful applications** (e.g., databases) that require persistent storage and ordered deployment and scaling

---

### 1️⃣2️⃣ What is a DaemonSet in Kubernetes?  
- A **DaemonSet** ensures that a copy of a Pod is running on each Node in the cluster, or on a subset of Nodes  
- It is commonly used for **background processes** like logging or monitoring

---

### 1️⃣3️⃣ What is the difference between Deployment and StatefulSet?  
- **Deployment**: Used for stateless applications, where Pods are interchangeable  
- **StatefulSet**: Used for stateful applications, where Pods have stable identities and persistent storage

---

### 1️⃣4️⃣ What is the role of the Kubernetes Scheduler?  
- The **Kubernetes Scheduler** is responsible for assigning Pods to Nodes in the cluster based on resource availability and other constraints (e.g., node selectors)

---

### 1️⃣5️⃣ What is the role of the Kubernetes Controller Manager?  
- The **Controller Manager** is responsible for running controllers that monitor the state of the cluster and make changes to bring it closer to the desired state (e.g., scaling, ensuring Pods are running)

---

### 1️⃣6️⃣ What is Horizontal Pod Autoscaling in Kubernetes?  
- **Horizontal Pod Autoscaling** automatically scales the number of Pods in a Deployment or ReplicaSet based on observed CPU utilization or custom metrics

---

### 1️⃣7️⃣ What is a Kubernetes Ingress?  
- **Ingress** is an API object that manages external access to services, typically HTTP  
- Provides **load balancing**, SSL termination, and name-based virtual hosting

---

### 1️⃣8️⃣ How does Kubernetes handle networking between Pods?  
- Kubernetes provides a **flat networking model**, where each Pod gets its own IP address, and Pods can communicate with each other directly across Nodes

---

### 1️⃣9️⃣ What is a Kubernetes Volume?  
- A **Volume** is a directory that contains data, accessible to containers in a Pod  
- Volumes persist across container restarts and can be shared between containers

---

### 2️⃣0️⃣ What is the difference between `kubectl apply` and `kubectl create`?  
- **`kubectl apply`**: Used to create or update resources declaratively based on a file (idempotent)  
- **`kubectl create`**: Used to create resources without updating them if they already exist

---

# 📂 **Kafka**

---

### 1️⃣ What is Apache Kafka?  
- **Apache Kafka** is an open-source **distributed event streaming platform** used for building real-time data pipelines and streaming applications  
- Kafka is used for **high-throughput, low-latency messaging** and can handle massive amounts of data in real-time

---

### 2️⃣ What are Kafka producers and consumers?  
- **Producer**: A Kafka producer sends messages (records) to Kafka topics  
- **Consumer**: A Kafka consumer reads messages from Kafka topics

---

### 3️⃣ What is a Kafka topic?  
- A **topic** is a logical channel to which messages are published by producers and from which consumers can read  
- Topics are **partitioned** for scalability and parallel processing

---

### 4️⃣ What is a Kafka partition?  
- A **partition** is a unit of parallelism in Kafka that allows messages within a topic to be distributed across multiple Kafka brokers  
- Partitions ensure data is **distributed** and processed in parallel, improving scalability

---

### 5️⃣ What is a Kafka broker?  
- A **broker** is a Kafka server that stores data and serves clients  
- Kafka brokers handle the distribution and replication of data across the Kafka cluster

---

### 6️⃣ What is a Kafka consumer group?  
- A **consumer group** is a group of Kafka consumers that jointly consume messages from one or more Kafka topics  
- Kafka ensures that each message in a topic partition is consumed by **only one member** of the consumer group

---

### 7️⃣ What is Kafka's offset?  
- The **offset** is a unique identifier for each message within a Kafka partition  
- It allows consumers to track the position of the last read message and resume consumption from that point

---

### 8️⃣ What is Kafka replication?  
- **Replication** is the process of maintaining multiple copies of Kafka data across different brokers for **fault tolerance** and **high availability**  
- Each partition has one **leader** and multiple **replicas**

---

### 9️⃣ What is Kafka's Zookeeper?  
- **Zookeeper** is a centralized service used by Kafka for **managing and coordinating** Kafka brokers in the cluster  
- It handles tasks such as leader election and broker metadata management

---

### 🔟 What is Kafka Streams?  
- **Kafka Streams** is a client library for building real-time, **stream processing applications** that can process data in Kafka topics  
- Provides a simple API for **stateful** and **stateless** stream processing

---

### 1️⃣1️⃣ What is the difference between Kafka and RabbitMQ?  
- **Kafka**: Designed for **high-throughput**, **event-driven** architectures, and scalable data pipelines  
- **RabbitMQ**: Primarily used for **message queueing**, supports message acknowledgement, and is more suitable for smaller-scale systems with complex routing

---

### 1️⃣2️⃣ What is the difference between Kafka's producer and consumer?  
- **Producer**: Sends messages to a Kafka topic  
- **Consumer**: Reads messages from a Kafka topic

---

### 1️⃣3️⃣ What is message retention in Kafka?  
- **Message retention** refers to the duration for which Kafka stores messages in a topic  
- Kafka allows configuring the retention time based on the **time** or **size** of messages in a topic

---

### 1️⃣4️⃣ What is Kafka's "at least once" message delivery semantics?  
- **"At least once" delivery semantics** ensures that each message is delivered to the consumer at least once  
- This may result in **duplicate messages**, so the consumer should handle deduplication

---

### 1️⃣5️⃣ What is the Kafka Consumer Rebalance?  
- **Consumer rebalance** occurs when a Kafka consumer group changes the assignment of partitions to consumers  
- This can happen when a new consumer joins or leaves the group, or when the topic's partitions change

---

### 1️⃣6️⃣ What is Kafka Connect?  
- **Kafka Connect** is a framework for **integrating** Kafka with **external systems** (e.g., databases, file systems, etc.)  
- It allows for **easy import/export** of data to/from Kafka using pre-built or custom connectors

---

### 1️⃣7️⃣ How does Kafka ensure fault tolerance?  
- Kafka ensures fault tolerance through **replication** of data across multiple brokers  
- Each partition has one leader and multiple replicas, so if a broker fails, the replicas can take over

---

### 1️⃣8️⃣ How does Kafka achieve high throughput?  
- Kafka achieves high throughput by storing data in **append-only logs**, batching messages, and using a highly efficient **disk storage** mechanism  
- Kafka also uses **compression** to reduce network usage

---

### 1️⃣9️⃣ What are Kafka consumer acknowledgments?  
- Kafka consumers use **offsets** to acknowledge the messages they have read  
- Consumers can commit offsets manually or automatically after processing messages

---

### 2️⃣0️⃣ How do you scale a Kafka cluster?  
- Kafka can be scaled by adding more **brokers** and **partitions**  
- Scaling consumers is done by adding more consumers to a **consumer group**

---

# 📂 **REST API**

---

### 1️⃣ What is a REST API?  
- **REST** (Representational State Transfer) is an architectural style for designing networked applications  
- A **REST API** allows different software applications to communicate over HTTP using standard HTTP methods (GET, POST, PUT, DELETE, etc.)

---

### 2️⃣ What are the key principles of REST?  
1. **Statelessness**: Every request from a client must contain all the information needed to understand and process the request  
2. **Client-Server Architecture**: The client and server should be separate, with the client focusing on the user interface and the server managing data and logic  
3. **Cacheability**: Responses must be explicitly marked as cacheable or non-cacheable  
4. **Uniform Interface**: A uniform and consistent interface for interacting with resources  
5. **Layered System**: REST APIs should be designed to work across different layers, allowing for intermediate components like proxies, load balancers, etc.  
6. **Code on Demand (optional)**: Servers can extend functionality by providing executable code (e.g., JavaScript)

---

### 3️⃣ What are HTTP methods and how are they used in REST?  
- **GET**: Retrieve data from the server  
- **POST**: Submit data to be processed (often used to create resources)  
- **PUT**: Update a resource on the server  
- **DELETE**: Remove a resource from the server  
- **PATCH**: Partially update a resource on the server

---

### 4️⃣ What is the difference between PUT and PATCH?  
- **PUT**: Replaces an entire resource with a new version  
- **PATCH**: Applies partial updates to a resource

---

### 5️⃣ What is the status code 200 used for in REST API?  
- **200 OK**: The request was successful, and the server has returned the requested data or performed the requested operation

---

### 6️⃣ What is the difference between 4xx and 5xx status codes?  
- **4xx (Client Errors)**: These codes indicate issues with the client's request, such as **400 Bad Request**, **401 Unauthorized**, or **404 Not Found**  
- **5xx (Server Errors)**: These codes indicate issues with the server while processing the request, such as **500 Internal Server Error** or **503 Service Unavailable**

---

### 7️⃣ What is the difference between REST and SOAP?  
- **REST**: Lightweight, uses standard HTTP methods, supports multiple formats (JSON, XML), stateless, and widely used for web services  
- **SOAP**: A protocol that relies on XML for communication, has strict messaging standards, requires more overhead, and is more secure and reliable but less flexible than REST

---

### 8️⃣ What are some common HTTP status codes used in REST APIs?  
- **200 OK**: Successful request  
- **201 Created**: Resource created successfully  
- **400 Bad Request**: Malformed request or missing parameters  
- **401 Unauthorized**: Authentication required  
- **403 Forbidden**: The client does not have permission to access the resource  
- **404 Not Found**: The resource could not be found  
- **500 Internal Server Error**: A general server error

---

### 9️⃣ What is HATEOAS in REST?  
- **HATEOAS** (Hypermedia as the Engine of Application State) is a constraint of REST that allows a client to interact with an API entirely through hyperlinks provided dynamically by the server  
- The client does not need to know the exact structure of the API beforehand

---

### 🔟 What is RESTful design?  
- RESTful design refers to designing an API that adheres to the principles of **REST**  
- Key characteristics of RESTful APIs include using HTTP methods correctly, designing intuitive URIs (Uniform Resource Identifiers), and keeping interactions stateless

---

### 1️⃣1️⃣ What are the advantages of REST APIs?  
- **Scalability**: Stateless nature allows REST APIs to scale easily  
- **Flexibility**: REST APIs can use various data formats like XML, JSON, and more  
- **Performance**: By leveraging HTTP, REST APIs are lightweight and fast  
- **Cacheable**: Responses can be cached to improve performance

---

### 1️⃣2️⃣ What is API versioning in REST?  
- **API versioning** is the practice of managing changes to an API without breaking existing clients  
- Common strategies for versioning include:
  - **URL versioning** (e.g., `/api/v1/resource`)
  - **Header versioning** (e.g., `Accept: application/vnd.myapi.v1+json`)

---

### 1️⃣3️⃣ What is Cross-Origin Resource Sharing (CORS) in REST APIs?  
- **CORS** is a security feature implemented by browsers that restricts web pages from making requests to a domain other than the one that served the web page  
- REST APIs need to explicitly enable CORS to allow requests from different origins

---

### 1️⃣4️⃣ What are some common authentication methods in REST APIs?  
- **Basic Authentication**: Sends the username and password in the request header (not recommended for production)  
- **Bearer Token (JWT)**: Uses a token (e.g., JSON Web Token) for authentication  
- **OAuth**: A third-party authorization protocol for secure delegated access

---

### 1️⃣5️⃣ What is idempotency in REST?  
- An operation is **idempotent** if performing it multiple times has the same effect as performing it once  
- HTTP methods like **GET**, **PUT**, and **DELETE** are idempotent, meaning multiple identical requests will not have side effects

---

### 1️⃣6️⃣ What are the common REST API best practices?  
- **Use HTTP methods correctly**: GET, POST, PUT, DELETE, etc.  
- **Design clean and intuitive URLs**: Use plural nouns and avoid unnecessary verbs  
- **Provide appropriate status codes**: Return 404 for not found, 400 for bad request, etc.  
- **Use pagination** for large datasets  
- **Support filtering and sorting** through query parameters

---

# 📂 **Design Patterns**

---

### 1️⃣ What is a design pattern?  
- A **design pattern** is a general repeatable solution to a commonly occurring problem in software design  
- It provides a template for solving problems in software architecture and design

---

### 2️⃣ What are the types of design patterns?  
- **Creational Patterns**: Deal with object creation mechanisms, trying to create objects in a manner suitable to the situation. Example: Singleton, Factory Method, Abstract Factory, Builder, Prototype  
- **Structural Patterns**: Deal with object composition, creating relationships between objects to form larger structures. Example: Adapter, Decorator, Composite, Proxy, Flyweight, Facade  
- **Behavioral Patterns**: Focus on communication between objects, what happens between objects and how the responsibility is assigned. Example: Observer, Strategy, Command, State, Chain of Responsibility, Visitor, Iterator

---

### 3️⃣ What is the Singleton design pattern?  
- The **Singleton** pattern ensures that a class has only one instance and provides a global point of access to it  
- It is commonly used for database connections, logging, thread pool management, etc.  
- Implementation usually involves private constructor and a static method to retrieve the instance

---

### 4️⃣ What is the Factory Method design pattern?  
- The **Factory Method** pattern defines an interface for creating an object, but it allows subclasses to alter the type of objects that will be created  
- It helps when you don't know beforehand what class you need to create and need flexibility to change the object type

---

### 5️⃣ What is the Abstract Factory design pattern?  
- The **Abstract Factory** pattern provides an interface for creating families of related or dependent objects without specifying their concrete classes  
- It's useful when the system needs to be independent of how its objects are created and composed

---

### 6️⃣ What is the Builder design pattern?  
- The **Builder** pattern is used to construct a complex object step by step  
- It separates the construction of a complex object from its representation, allowing the same construction process to create different representations

---

### 7️⃣ What is the Prototype design pattern?  
- The **Prototype** pattern is used to create a duplicate object or clone from the original object  
- This pattern is particularly useful when the cost of creating a new object is expensive and cloning an existing object is more efficient

---

### 8️⃣ What is the Adapter design pattern?  
- The **Adapter** pattern allows incompatible interfaces to work together  
- It acts as a bridge between two incompatible interfaces by converting one interface to another that a client expects

---

### 9️⃣ What is the Decorator design pattern?  
- The **Decorator** pattern allows behavior to be added to an individual object dynamically without affecting the behavior of other objects from the same class  
- It's often used to extend the functionalities of classes in a flexible and reusable way

---

### 🔟 What is the Composite design pattern?  
- The **Composite** pattern allows you to compose objects into tree-like structures to represent part-whole hierarchies  
- It lets clients treat individual objects and compositions of objects uniformly

---

### 1️⃣1️⃣ What is the Proxy design pattern?  
- The **Proxy** pattern provides a surrogate or placeholder for another object  
- It is often used to control access to the original object by adding functionality such as lazy loading, access control, or logging

---

### 1️⃣2️⃣ What is the Flyweight design pattern?  
- The **Flyweight** pattern reduces the number of objects created by sharing objects that are similar in nature  
- It’s useful when many objects are needed, but they share common properties

---

### 1️⃣3️⃣ What is the Facade design pattern?  
- The **Facade** pattern provides a simplified interface to a complex subsystem  
- It is used to hide the complexities of a system and provide a higher-level interface to the client

---

### 1️⃣4️⃣ What is the Observer design pattern?  
- The **Observer** pattern defines a one-to-many dependency between objects, where a change in one object (subject) notifies all its dependents (observers)  
- It is commonly used in implementing event handling systems

---

### 1️⃣5️⃣ What is the Strategy design pattern?  
- The **Strategy** pattern defines a family of algorithms, encapsulates each one, and makes them interchangeable  
- It allows a client to choose the algorithm at runtime, making the algorithm independent of the client that uses it

---

### 1️⃣6️⃣ What is the Command design pattern?  
- The **Command** pattern encapsulates a request as an object, allowing the parameterization of clients with queues, requests, and operations  
- It decouples the sender and receiver of a request, enabling delayed execution or undo functionality

---

### 1️⃣7️⃣ What is the State design pattern?  
- The **State** pattern allows an object to alter its behavior when its internal state changes  
- The object will appear to change its class as it transitions between states

---

### 1️⃣8️⃣ What is the Chain of Responsibility design pattern?  
- The **Chain of Responsibility** pattern allows a request to be passed along a chain of handlers  
- Each handler in the chain processes the request or passes it on to the next handler, enabling dynamic change of processing behavior

---

### 1️⃣9️⃣ What is the Visitor design pattern?  
- The **Visitor** pattern lets you define new operations on elements of an object structure without changing the classes of the elements  
- It is useful when you need to perform operations across a set of objects that have different types

---

### 2️⃣0️⃣ What is the Iterator design pattern?  
- The **Iterator** pattern allows sequential access to elements of a collection without exposing the underlying structure of the collection  
- It provides a standard way to iterate over elements in a collection

---

# 📂 **Java Security**

---

### 1️⃣ What is Java Security?  
- **Java Security** is a set of mechanisms that ensure secure execution of Java programs, ensuring confidentiality, integrity, and availability of resources  
- It includes measures like code signing, encryption, authentication, and access control

---

### 2️⃣ What are the key components of Java Security?  
- **Authentication**: Verifying the identity of users, systems, or services  
- **Authorization**: Ensuring the authenticated user has permission to access a resource  
- **Confidentiality**: Protecting data from unauthorized access using encryption  
- **Integrity**: Ensuring the data remains unaltered during transmission or storage  
- **Non-repudiation**: Ensuring that a party cannot deny the authenticity of their actions or communications

---

### 3️⃣ What is the Java Security Manager?  
- The **Java Security Manager** is a security policy enforcement mechanism in the Java runtime environment  
- It controls access to system resources such as file I/O, network access, and shared memory, based on permissions granted to the code running in the JVM

---

### 4️⃣ What is the Java Cryptography Architecture (JCA)?  
- The **Java Cryptography Architecture (JCA)** is a set of APIs provided by Java for implementing cryptographic operations like encryption, decryption, key management, and message digests  
- JCA is provider-based, meaning it can use different providers to implement various cryptographic algorithms

---

### 5️⃣ What are some common cryptographic algorithms used in Java?  
- **Symmetric Encryption**: AES (Advanced Encryption Standard), DES (Data Encryption Standard), 3DES (Triple DES)  
- **Asymmetric Encryption**: RSA, ECC (Elliptic Curve Cryptography)  
- **Hash Functions**: MD5, SHA-1, SHA-256, SHA-512  
- **Digital Signatures**: RSA, DSA (Digital Signature Algorithm)

---

### 6️⃣ What is a digital signature, and how does it work?  
- A **digital signature** is a mathematical scheme for verifying the authenticity and integrity of a message, software, or digital document  
- It uses asymmetric encryption: the sender signs the data with their private key, and the receiver can verify the signature using the sender’s public key

---

### 7️⃣ What is Java KeyStore (JKS)?  
- The **Java KeyStore (JKS)** is a repository for storing cryptographic keys and certificates  
- It is used to store private keys, public keys, and certificates required for various security-related activities such as SSL/TLS and digital signatures

---

### 8️⃣ What is the difference between symmetric and asymmetric encryption?  
- **Symmetric encryption** uses the same key for both encryption and decryption (e.g., AES, DES)  
- **Asymmetric encryption** uses a pair of keys: a public key for encryption and a private key for decryption (e.g., RSA)

---

### 9️⃣ What is SSL/TLS, and how does it work in Java?  
- **SSL (Secure Sockets Layer)** and **TLS (Transport Layer Security)** are protocols used to secure data transmission over networks  
- Java uses the **JSSE (Java Secure Socket Extension)** API to implement SSL/TLS, providing secure communication channels via `SSLSocket` and `SSLServerSocket`

---

### 🔟 What is the purpose of the `java.security` package?  
- The **`java.security`** package provides a variety of security-related classes and interfaces for cryptographic operations, key management, and security policies  
- It allows developers to create secure applications by managing security providers, permissions, and authentication mechanisms

---

### 1️⃣1️⃣ What is a secure coding practice in Java?  
- **Secure coding practices** are techniques and practices that help developers write code that is resistant to security vulnerabilities  
- Examples: Input validation, output encoding, SQL injection prevention, using secure communication protocols (TLS/SSL), not hardcoding credentials, and using secure password hashing algorithms

---

### 1️⃣2️⃣ What is a Public Key Infrastructure (PKI)?  
- **PKI (Public Key Infrastructure)** is a framework for managing public-key encryption, digital signatures, and certificates  
- It includes **Certificate Authorities (CA)** for issuing digital certificates, **Public and Private Keys**, and **Certificate Revocation Lists (CRLs)**

---

### 1️⃣3️⃣ How does the Java Security model differ in terms of access control?  
- Java has a **granular access control model** using the **Security Manager** and **Permissions**. It uses the **AccessControlContext** class to grant or deny access to resources  
- It uses a **policy file** to set rules defining which classes can access which resources (files, network, etc.)

---

### 1️⃣4️⃣ What is the `java.security.PrivilegedAction` and why is it used?  
- **`PrivilegedAction`** is a class used for executing a block of code with elevated privileges  
- It is typically used in situations where code needs to perform sensitive operations like accessing system resources, but without exposing sensitive methods to the rest of the application

---

### 1️⃣5️⃣ What are the risks of hardcoding sensitive information in Java applications?  
- Hardcoding sensitive data such as passwords, API keys, or database credentials exposes the application to **data breaches**  
- Attackers can reverse-engineer the application or gain access to source code to extract sensitive information. It is recommended to use **environment variables** or **external configuration files** for storing sensitive data

---

### 1️⃣6️⃣ How do you prevent SQL Injection in Java applications?  
- Use **Prepared Statements** or **Parameterized Queries** to safely include user inputs in SQL queries  
- Avoid concatenating strings to form SQL queries, as this opens the door to SQL Injection attacks

---

### 1️⃣7️⃣ What is Cross-Site Scripting (XSS), and how do you mitigate it in Java applications?  
- **Cross-Site Scripting (XSS)** is a vulnerability where an attacker injects malicious scripts into web pages viewed by users  
- Mitigate it by **validating and sanitizing inputs**, **encoding output**, and using Java libraries like **OWASP Java HTML Sanitizer** or frameworks like **JSF**, **Spring Security** that automatically protect against XSS

---

# 📂 **JVM Internals and Performance Tuning**

---

### 1️⃣ What is the **Java Virtual Machine (JVM)**, and what are its components?  
- The **JVM** is a virtual machine that runs Java bytecode and provides the environment for Java programs to run.  
- **Key components**:
  - **Classloader**: Loads classes into the JVM.
  - **Runtime Data Areas**: Includes the heap, stack, method area, program counter, and native method stack.
  - **Execution Engine**: Responsible for executing the bytecode.
  - **Garbage Collector**: Automatically manages memory by reclaiming unused objects.

---

### 2️⃣ How does **Garbage Collection (GC)** work in Java?  
- **Garbage Collection (GC)** is the process of automatically finding and disposing of objects that are no longer reachable by any part of the program.  
- It helps in memory management by preventing memory leaks and freeing up space in the heap.  
- **GC Algorithms**:  
  - **Serial GC**  
  - **Parallel GC**  
  - **G1 Garbage Collector** (used for large heaps)
  - **ZGC** and **Shenandoah** (low-latency GCs)

---

### 3️⃣ What are the different memory areas in the JVM?  
- **Heap**: Stores objects created by the program. Divided into **young generation**, **old generation**, and **permanent generation** (or **metaspace** in Java 8+).
- **Stack**: Stores method frames, local variables, and partial results.
- **Method Area**: Stores class-level data such as metadata, class definitions, and static variables.
- **Program Counter Register**: Keeps track of the current instruction being executed.
- **Native Method Stack**: Contains native methods used by the JVM for interfacing with the operating system.

---

### 4️⃣ What is the **difference between stack memory and heap memory** in JVM?  
- **Stack Memory**:  
  - Stores **local variables** and method calls.
  - Memory is managed in a **Last-In-First-Out (LIFO)** manner.
  - Memory is **automatically reclaimed** when methods return.
- **Heap Memory**:  
  - Stores **objects** created by the program.
  - Memory must be manually reclaimed by the garbage collector.
  - Used for objects that need to be shared across methods or classes.

---

### 5️⃣ How do you perform **JVM performance tuning**?  
- **Tuning GC**: Adjust the heap size and garbage collector type to suit the application's needs. Use JVM flags like `-Xms` (initial heap size) and `-Xmx` (maximum heap size).
- **Thread Tuning**: Optimize the number of threads and the thread pool size.  
- **JVM flags**:  
  - `-XX:+UseG1GC`: To enable the G1 Garbage Collector.  
  - `-XX:+PrintGCDetails`: To view GC logs.
  - `-Xmn`: To set the size of the young generation.
  
---

### 6️⃣ What is **JVM tuning** using **JVM options**?  
- **JVM Options** are flags used to configure the behavior of the JVM.  
- Examples include:  
  - **Memory Settings**:  
    - `-Xms` to set the initial heap size.  
    - `-Xmx` to set the maximum heap size.  
  - **Garbage Collection**:  
    - `-XX:+UseG1GC` to enable the G1 Garbage Collector.  
    - `-XX:+PrintGCDetails` to enable detailed GC logging.

---

### 7️⃣ What is the **HotSpot JVM**?  
- The **HotSpot JVM** is the default JVM implementation in Java.  
- It uses **just-in-time (JIT) compilation** to improve performance by compiling bytecode into native machine code at runtime.

---

### 8️⃣ What are the **Java Memory Model (JMM)** concepts?  
- The **Java Memory Model (JMM)** defines how threads interact through memory and what behaviors are allowed when two threads access shared variables.  
- Key concepts include:  
  - **Visibility**: Changes made by one thread may not be visible to other threads unless synchronized properly.
  - **Atomicity**: Operations on a variable are atomic if they cannot be interrupted.
  - **Ordering**: The order in which instructions are executed in a multi-threaded environment.

---

### 9️⃣ What is **Heap Dump** in JVM, and how is it useful?  
- A **Heap Dump** is a snapshot of the memory in the heap at a specific point in time.  
- It is useful for debugging memory leaks or analyzing memory usage in an application.

---

### 🔟 What is the **difference between Minor GC and Full GC**?  
- **Minor GC**: Occurs when the **young generation** is full. It is a **quick** process and only affects the young generation.
- **Full GC**: Occurs when the entire heap (young + old generation) needs to be garbage collected. It is a **slower** process.

---

### 1️⃣1️⃣ What are **JVM tuning tools** used for monitoring and performance analysis?  
- **JConsole**: A monitoring tool that provides real-time data about JVM performance.
- **VisualVM**: A tool for profiling and monitoring JVM applications.
- **Java Flight Recorder**: A tool for collecting diagnostic data in a production environment.
- **GC Logs**: Used to analyze garbage collection behavior.

---

### 1️⃣2️⃣ How do you monitor **JVM heap usage**?  
- Tools like **JConsole**, **VisualVM**, and **JMX** can monitor heap usage in real time.  
- JVM options like `-XX:+PrintGCDetails` provide details of the garbage collection process, including heap usage statistics.

---

### 1️⃣3️⃣ What is **JIT Compilation** in Java?  
- **JIT (Just-In-Time)** compilation refers to the compilation of bytecode into native machine code at runtime to improve performance.  
- This process helps avoid interpretation overhead and speeds up execution.

---

### 1️⃣4️⃣ How would you deal with **Memory Leaks** in a Java application?  
- Use **profiling tools** like **VisualVM**, **JProfiler**, or **Eclipse MAT** to find memory leaks.
- Review code for objects that are no longer in use but are still being referenced.
- Ensure proper resource cleanup (e.g., closing database connections, streams, etc.).

---

### 1️⃣5️⃣ What is **Garbage Collection** tuning in the context of **JVM performance**?  
- **GC tuning** involves adjusting parameters like **heap size**, **young generation size**, and **garbage collector types** (e.g., G1, Parallel GC).
- Example tuning flags:  
  - `-Xms` (initial heap size), `-Xmx` (maximum heap size), `-XX:+UseG1GC` (to use G1 Garbage Collector).
 
---

# 📂 **Concurrency and Multithreading**

---

### 1️⃣ What is the difference between **concurrency** and **parallelism** in Java?  
- **Concurrency**: Refers to the ability of a program to handle multiple tasks at once, but not necessarily simultaneously. It is about managing multiple tasks over time, potentially executing them in an interleaved manner on a single or multiple threads.
- **Parallelism**: Refers to executing multiple tasks **simultaneously** in a program, typically on multiple processors or cores.

---

### 2️⃣ What is the **Thread** class in Java?  
- The **Thread** class represents a thread of execution in a Java program.  
- You can create a thread by either:  
  - Extending the `Thread` class and overriding its `run()` method.
  - Implementing the `Runnable` interface and passing it to a `Thread` object.

---

### 3️⃣ How do you create and start a thread in Java?  
```java
// Method 1: By extending Thread class
class MyThread extends Thread {
    @Override
    public void run() {
        System.out.println("Thread is running");
    }
}

MyThread thread = new MyThread();
thread.start();

// Method 2: By implementing Runnable interface
class MyRunnable implements Runnable {
    @Override
    public void run() {
        System.out.println("Runnable is running");
    }
}

Thread thread = new Thread(new MyRunnable());
thread.start();
```

---

### 4️⃣ What is the **Runnable** interface, and how is it different from **Thread**?  
- **Runnable** is a functional interface that represents a task that can be executed concurrently.  
- **Thread** is a concrete class that represents a thread, while **Runnable** is just a task to be executed by a thread.
- **Runnable** allows for better **resource sharing** as you can pass the same instance of `Runnable` to multiple threads.

---

### 5️⃣ What is **synchronization** in Java, and why is it important?  
- **Synchronization** ensures that only one thread can access a resource (e.g., method or block of code) at a time.
- It is important to prevent **race conditions**, where multiple threads trying to modify shared data simultaneously can lead to inconsistent results.
```java
public synchronized void myMethod() {
    // synchronized code
}
```

---

### 6️⃣ What is the **difference between synchronized method and synchronized block**?  
- **Synchronized Method**: The entire method is synchronized, meaning only one thread can execute it at a time.
  ```java
  public synchronized void method() {
      // code
  }
  ```
- **Synchronized Block**: Only a specific portion of the code inside a method is synchronized, allowing more control over which part of the method is synchronized.
  ```java
  public void method() {
      synchronized (lockObject) {
          // synchronized code
      }
  }
  ```

---

### 7️⃣ What is a **deadlock** in Java, and how can you prevent it?  
- **Deadlock** occurs when two or more threads are blocked indefinitely because each thread is waiting for a resource held by the other.
- **Prevention techniques**:
  - Always acquire locks in a consistent order.
  - Use **tryLock** with a timeout to avoid waiting indefinitely.
  - Use **lock ordering** to ensure that threads acquire locks in the same order.

---

### 8️⃣ What is the **Executor Framework** in Java?  
- The **Executor Framework** provides a higher-level replacement for the traditional way of managing threads. It separates task submission from the details of how each task will be executed.
- Key components:
  - **ExecutorService**: An interface that provides methods for managing and controlling thread pools.
  - **ThreadPoolExecutor**: A concrete implementation of `ExecutorService`.

---

### 9️⃣ What are **Callable** and **Future** interfaces in Java?  
- **Callable** is similar to **Runnable**, but it can return a result or throw an exception.
- **Future** represents the result of an asynchronous computation, allowing you to retrieve the result of a **Callable** or **Runnable** task.
```java
ExecutorService executor = Executors.newSingleThreadExecutor();
Callable<Integer> task = () -> 5 + 3;
Future<Integer> future = executor.submit(task);
Integer result = future.get();  // returns 8
```

---

### 🔟 What is the **ForkJoinPool** in Java?  
- **ForkJoinPool** is a specialized thread pool designed for parallelism. It efficiently manages tasks that can be broken down into smaller subtasks (i.e., divide and conquer).
- It uses a **work-stealing algorithm** to balance the load among threads.

---

### 1️⃣1️⃣ What is the **CountDownLatch** class, and how is it used?  
- The **CountDownLatch** is a synchronization aid that allows one or more threads to wait until a set of operations being performed by other threads completes.
- Example usage:
```java
CountDownLatch latch = new CountDownLatch(3);  // wait for 3 tasks to complete
// Worker threads
latch.countDown();  // Decrements the count
latch.await();  // Wait until the count is 0
```

---

### 1️⃣2️⃣ What is a **Semaphore** in Java?  
- A **Semaphore** is a synchronization tool that controls access to a shared resource through the use of a counter.
- It allows a specified number of threads to access a resource concurrently.
```java
Semaphore semaphore = new Semaphore(3);  // Allow 3 threads to access the resource
semaphore.acquire();  // Acquire a permit
semaphore.release();  // Release a permit
```

---

### 1️⃣3️⃣ What is **Thread Safety** in Java?  
- **Thread safety** refers to the ability of a class or method to function correctly when multiple threads access it simultaneously.
- **Achieved through**:  
  - Using **synchronized blocks/methods**.
  - Using thread-safe classes from the **java.util.concurrent** package (e.g., `ConcurrentHashMap`, `CopyOnWriteArrayList`).

---

### 1️⃣4️⃣ What is the **volatile** keyword in Java?  
- The **volatile** keyword ensures that a variable's value is always read from and written to the main memory, rather than being cached in a thread's local memory.
- It is used to **ensure visibility** between threads, preventing one thread from working with stale data.

---

### 1️⃣5️⃣ What is **ThreadLocal** in Java?  
- **ThreadLocal** provides thread-local variables, meaning each thread has its own independent copy of the variable.
- It is useful when you want each thread to have its own instance of a variable, without the need for synchronization.

Let's move on to the **Java Memory Model (JMM)** section.

---

# 📂 **Java Memory Model (JMM)**

---

### 1️⃣ What is the **Java Memory Model (JMM)**?  
- The **Java Memory Model (JMM)** defines how threads interact through memory and how variables are read and written in a multi-threaded environment.
- It ensures that Java programs exhibit predictable behavior when multiple threads access shared data concurrently.

---

### 2️⃣ What are the key principles of the **Java Memory Model**?  
- **Visibility**: Changes made by one thread to a shared variable are visible to other threads.
- **Atomicity**: A thread's actions on variables are atomic and indivisible.
- **Ordering**: The JMM guarantees that statements are executed in a specified order unless otherwise indicated by synchronization mechanisms.

---

### 3️⃣ What are the **happens-before** and **happens-after** relationships in the context of JMM?  
- **Happens-before**: A guarantee that one action (e.g., a write) happens before another action (e.g., a read) in a multithreaded environment.
  - Example: A `synchronized` block ensures that changes made inside the block happen-before any reads after the block.
- **Happens-after**: The opposite of happens-before, where an action (e.g., a read) happens after the corresponding write.

---

### 4️⃣ What is **volatile** in the context of JMM?  
- The **volatile** keyword in Java ensures that the most recent value of a variable is always fetched from the main memory, rather than being cached in the local thread cache.
- It guarantees **visibility** of changes made by one thread to other threads.
- **Note**: Volatile does not guarantee atomicity for compound operations (e.g., increment).

---

### 5️⃣ What is the significance of **synchronized** in JMM?  
- The **synchronized** keyword ensures that:
  - A method or block of code can be accessed by only one thread at a time.
  - The changes made by one thread are visible to other threads.
  - The synchronization mechanism **establishes a happens-before relationship** between threads, ensuring that writes to shared variables are visible to other threads after synchronization.

---

### 6️⃣ What is the **acquire-release** semantics in JMM?  
- The **acquire-release** semantics ensures that:
  - A thread's **acquire** action (e.g., entering a synchronized block) happens-before its corresponding **release** action (e.g., exiting the synchronized block).
  - This means that all actions done before the acquire action are visible to other threads after the release action.

---

### 7️⃣ What are **atomic variables** in Java?  
- **Atomic variables** are variables that are accessed and updated atomically, meaning their value is updated without interference from other threads.
- Java provides classes like `AtomicInteger`, `AtomicLong`, and `AtomicReference` in the `java.util.concurrent.atomic` package, which are designed to ensure atomicity for common operations like increment, compare-and-set, etc.

---

### 8️⃣ What is **reordering** in JMM, and how can it affect multi-threaded programs?  
- **Reordering** refers to the reordering of instructions by the JVM or CPU for performance optimization.
- While the JVM and hardware may reorder instructions for efficiency, the **happens-before** relationship in JMM ensures that reordering does not violate thread safety or produce inconsistent results.
- Synchronization and `volatile` can be used to prevent or control reordering in critical sections.

---

### 9️⃣ What is the concept of **race conditions** in the Java Memory Model?  
- A **race condition** occurs when two or more threads try to access and modify shared data concurrently without proper synchronization, leading to unpredictable results.
- To avoid race conditions, synchronization mechanisms like `synchronized` blocks, `volatile` variables, or `java.util.concurrent` classes should be used to ensure correct visibility and atomicity.

---

### 🔟 What is the **final** keyword in Java with respect to JMM?  
- The **final** keyword in Java ensures that:
  - A field's value is **immutable** once initialized.
  - If a field is declared as `final`, its value is guaranteed to be visible to all threads after the constructor of the object completes, ensuring proper **visibility** of the value across threads.

---

### 1️⃣1️⃣ What is the role of **happens-before relationship** in preventing thread interference in Java?  
- The **happens-before relationship** establishes a strict ordering of actions in a multi-threaded program.  
- It ensures that certain actions (like writing to a variable) are completed before others (like reading the variable), preventing **thread interference** where multiple threads modify shared data in conflicting ways.

---

### 1️⃣2️⃣ What is **Thread Interference** in Java, and how can it be avoided?  
- **Thread Interference** occurs when multiple threads attempt to read/write to the same variable concurrently without proper synchronization, leading to inconsistent or incorrect data.
- It can be avoided by:
  - Using synchronization (`synchronized` blocks/methods).
  - Using **atomic classes** (`AtomicInteger`, `AtomicReference`).
  - Using **Locks** (`ReentrantLock`).

---

### 1️⃣3️⃣ What is the **Java Memory Model's impact on multi-core systems**?  
- In a **multi-core system**, the JMM ensures that the behavior of Java programs is consistent across different cores.  
- The JMM handles **visibility** and **ordering** issues that can arise in multi-core systems, ensuring that changes made by one thread on one core are visible to other threads running on different cores.

---

### 1️⃣4️⃣ How do you ensure **safe publication** of an object in Java?  
- **Safe publication** refers to ensuring that an object is correctly shared between threads and is visible to them when they access it.
- Safe publication can be achieved by:
  - Using `volatile` variables.
  - Initializing the object within a **synchronized block** or constructor.
  - Using **final** fields.

---

### 1️⃣5️⃣ How does **double-checked locking** work, and how does JMM help in making it thread-safe?  
- **Double-checked locking** is a pattern used to implement lazy initialization of resources in a thread-safe manner.
- It involves checking if the resource is already initialized before acquiring a lock, and checking again after the lock is acquired.
- In JMM, the `volatile` keyword ensures that the variable is correctly published to other threads without reordering or caching issues.

---

# 📂 **Section 20: JDBC and Database Connectivity**

---

### 1️⃣ What is **JDBC (Java Database Connectivity)**?  
- **JDBC** is an API in Java that enables Java applications to interact with relational databases.
- It provides a standard interface for connecting to databases, executing SQL queries, and handling result sets.

---

### 2️⃣ What are the different **JDBC Drivers** available?  
- **Type 1**: JDBC-ODBC Bridge Driver – Uses ODBC to connect to the database.
- **Type 2**: Native-API Driver – Directly uses the database's native API to connect.
- **Type 3**: Network Protocol Driver – Uses a middle-tier server to communicate with the database.
- **Type 4**: Thin Driver – Directly communicates with the database using its native protocol (most common).

---

### 3️⃣ What are the basic steps involved in connecting to a database using JDBC?  
1. **Load the Driver**: Load the database driver class (e.g., `Class.forName("com.mysql.cj.jdbc.Driver");`).
2. **Establish the Connection**: Use `DriverManager.getConnection()` to establish a connection to the database.
3. **Create a Statement**: Use `Connection.createStatement()` to create a statement object.
4. **Execute the Query**: Use the `executeQuery()` or `executeUpdate()` methods to run SQL queries.
5. **Process the Result Set**: Retrieve results from a `ResultSet` object.
6. **Close the Connections**: Close the `Statement`, `ResultSet`, and `Connection` objects to avoid resource leaks.

---

### 4️⃣ What is the difference between **executeQuery()**, **executeUpdate()**, and **execute()** methods in JDBC?  
- **executeQuery()**: Used for executing SELECT queries and returns a `ResultSet`.
- **executeUpdate()**: Used for executing INSERT, UPDATE, DELETE, or any DDL (Data Definition Language) statements. It returns the number of affected rows.
- **execute()**: A general-purpose method that can execute any SQL query, returning a boolean indicating if the result is a `ResultSet`.

---

### 5️⃣ What is **Connection Pooling** in JDBC, and why is it important?  
- **Connection Pooling** is the practice of reusing existing database connections instead of opening and closing new ones frequently.
- It improves performance by reducing overhead and resource consumption.
- Connection pools are managed by frameworks like **HikariCP**, **Apache DBCP**, or **C3P0**.

---

### 6️⃣ What is the **PreparedStatement** in JDBC, and how is it different from a **Statement**?  
- **PreparedStatement** is used for executing parameterized SQL queries, where input parameters are bound to placeholders in the SQL statement.
- It is more efficient and secure compared to **Statement** as it precompiles the query, reducing the risk of SQL injection.
- Example:
  ```java
  String query = "SELECT * FROM users WHERE username = ?";
  PreparedStatement ps = conn.prepareStatement(query);
  ps.setString(1, "user1");
  ResultSet rs = ps.executeQuery();
  ```

---

### 7️⃣ What is **Transaction Management** in JDBC?  
- **Transaction Management** in JDBC is used to ensure that a set of SQL operations either all succeed or fail (i.e., **Atomicity**).
- **Steps for transaction management**:
  1. **Disable Auto-commit**: `conn.setAutoCommit(false);`
  2. **Execute SQL Queries**: Perform multiple SQL operations.
  3. **Commit**: `conn.commit();` to save changes if everything is successful.
  4. **Rollback**: `conn.rollback();` to undo changes if there is an error.

---

### 8️⃣ What are **Batch Processing** and its advantages in JDBC?  
- **Batch Processing** allows multiple SQL statements to be executed as a batch, reducing database round trips.
- It is beneficial for inserting or updating large amounts of data efficiently.
- Example:
  ```java
  Statement stmt = conn.createStatement();
  stmt.addBatch("INSERT INTO users (name) VALUES ('John')");
  stmt.addBatch("INSERT INTO users (name) VALUES ('Jane')");
  int[] result = stmt.executeBatch();
  ```

---

### 9️⃣ What are **CallableStatement** and how do you use it in JDBC?  
- **CallableStatement** is used to execute stored procedures in the database.
- It can execute SQL queries that are stored in the database itself as a procedure.
- Example:
  ```java
  String storedProc = "{call getUserInfo(?, ?)}";
  CallableStatement cs = conn.prepareCall(storedProc);
  cs.setInt(1, 1001);
  cs.registerOutParameter(2, java.sql.Types.VARCHAR);
  cs.execute();
  String userInfo = cs.getString(2);
  ```

---

### 🔟 How does **Exception Handling** work in JDBC?  
- JDBC provides **SQLExceptions** to handle database errors.
- You can handle exceptions using a `try-catch` block and use `getMessage()`, `getErrorCode()`, and `getSQLState()` methods of `SQLException` to get detailed information about the error.

---

### 1️⃣1️⃣ What is the **ResultSet** in JDBC, and how do you process it?  
- The **ResultSet** is an object that holds the data retrieved from a SQL query execution.
- You can process the result set by iterating through it using methods like `next()`, `getString()`, `getInt()`, etc.
  ```java
  while (rs.next()) {
      String name = rs.getString("username");
      int age = rs.getInt("age");
  }
  ```

---

### 1️⃣2️⃣ What is the role of **Auto-commit** in JDBC?  
- **Auto-commit** is a mode in which each SQL statement is executed as a separate transaction.
- By default, JDBC operates in auto-commit mode. To manually control transactions, you can disable auto-commit using `conn.setAutoCommit(false)`.

---

### 1️⃣3️⃣ What is **SQL Injection**, and how can it be prevented in JDBC?  
- **SQL Injection** is a security vulnerability where malicious input is inserted into SQL statements, potentially allowing attackers to execute unauthorized queries.
- It can be prevented by:
  - Using **PreparedStatement** with parameterized queries instead of concatenating user input into SQL strings.
  - Validating user input before processing it.

---

### 1️⃣4️⃣ What is **getGeneratedKeys()** in JDBC?  
- The `getGeneratedKeys()` method is used to retrieve auto-generated keys (e.g., primary keys) after executing an `INSERT` statement.
- Example:
  ```java
  PreparedStatement ps = conn.prepareStatement("INSERT INTO users (name) VALUES (?)", Statement.RETURN_GENERATED_KEYS);
  ps.setString(1, "John");
  ps.executeUpdate();
  ResultSet rs = ps.getGeneratedKeys();
  if (rs.next()) {
      int id = rs.getInt(1);  // Get the generated key
  }
  ```

---

### 1️⃣5️⃣ What is the **difference between Statement, PreparedStatement, and CallableStatement** in JDBC?  
- **Statement**: Used for executing static SQL queries, not efficient for repeated queries.
- **PreparedStatement**: Used for executing parameterized SQL queries, more efficient and secure than `Statement`.
- **CallableStatement**: Used for executing stored procedures.

---

# 📂 **ORM (Hibernate and JPA)**

---

### 1️⃣ What is **ORM (Object-Relational Mapping)**?  
- **ORM** is a programming technique used to convert data between incompatible type systems (object-oriented programming and relational databases).  
- It allows developers to work with databases using object-oriented paradigms, eliminating the need for manual SQL queries and mapping objects to database tables.

---

### 2️⃣ What is the difference between **Hibernate** and **JPA**?  
- **Hibernate** is a framework that implements the **JPA** (Java Persistence API) specification. 
  - Hibernate provides additional features such as caching and session management that are not part of JPA.
  - It is a full-fledged ORM framework.
- **JPA** is a Java specification for ORM frameworks. It provides a set of interfaces and annotations, but it does not define a concrete implementation.
  - Hibernate, EclipseLink, and OpenJPA are popular implementations of JPA.

---

### 3️⃣ What are the main **annotations** used in **JPA**?  
- `@Entity`: Defines a class as a persistent entity.
- `@Id`: Marks the primary key field of an entity.
- `@GeneratedValue`: Specifies how the primary key should be generated (e.g., auto, sequence).
- `@Column`: Maps a field to a database column.
- `@OneToOne`, `@OneToMany`, `@ManyToOne`, `@ManyToMany`: Defines relationships between entities.
- `@JoinColumn`: Specifies the column used to join two tables in a relationship.

---

### 4️⃣ What is **HQL (Hibernate Query Language)**, and how does it differ from SQL?  
- **HQL** is an object-oriented query language used in Hibernate to query the database. Unlike SQL, HQL queries are written in terms of Java objects and their properties, not the database tables.
- Example of HQL:
  ```java
  String hql = "FROM User WHERE username = :username";
  Query query = session.createQuery(hql);
  query.setParameter("username", "john_doe");
  List<User> users = query.list();
  ```
- **Difference from SQL**: 
  - HQL queries are based on entities and their properties, not database tables and columns.
  - HQL supports polymorphic queries, allowing you to query by entity class.

---

### 5️⃣ What is **lazy loading** in Hibernate, and how does it work?  
- **Lazy Loading** is a strategy used in Hibernate to load related entities only when they are accessed for the first time (on demand), rather than loading them immediately.
- It is useful for improving performance when you have large object graphs.
- Example:
  ```java
  @OneToMany(fetch = FetchType.LAZY)
  private List<Order> orders;
  ```

---

### 6️⃣ What is **Eager Loading** in Hibernate?  
- **Eager Loading** means that related entities are loaded immediately when the parent entity is loaded.
- It is useful when you know that you will need the related entities.
- Example:
  ```java
  @OneToMany(fetch = FetchType.EAGER)
  private List<Order> orders;
  ```

---

### 7️⃣ What is the **Session** in Hibernate?  
- The **Session** is an interface in Hibernate that is used to interact with the database. It provides methods for saving, updating, deleting, and retrieving objects.
- A **Session** is a single-threaded object, meaning it should not be shared between different threads.
- It is used to perform CRUD operations and is analogous to a connection in JDBC.

---

### 8️⃣ What is **First-Level Cache** in Hibernate?  
- **First-Level Cache** (also known as **Session Cache**) is a cache that is associated with the **Session** object.
- It stores the entities that are loaded or saved during the lifecycle of the session.
- The session cache is **enabled by default** and is cleared once the session is closed.

---

### 9️⃣ What is **Second-Level Cache** in Hibernate?  
- **Second-Level Cache** is a cache that is shared across sessions and is used to store data that is accessed frequently.
- It is optional and requires configuration. It can significantly improve performance by reducing database calls.
- Popular second-level cache providers include **EHCache**, **Infinispan**, and **Redis**.

---

### 🔟 What is **Cascading** in Hibernate, and how is it used?  
- **Cascading** refers to automatically applying certain operations (e.g., persist, merge, delete) to related entities when performing these operations on the parent entity.
- Common cascade options:
  - `CascadeType.PERSIST`: Propagates the persist operation.
  - `CascadeType.MERGE`: Propagates the merge operation.
  - `CascadeType.ALL`: Applies all operations (persist, merge, remove).
  - Example:
    ```java
    @OneToMany(cascade = CascadeType.ALL)
    private List<Order> orders;
    ```

---

### 1️⃣1️⃣ What is **@OneToMany** and **@ManyToOne** in JPA?  
- **@OneToMany**: Defines a one-to-many relationship, where one entity can be associated with multiple entities.
  - Example:
    ```java
    @OneToMany(mappedBy = "user")
    private List<Order> orders;
    ```
- **@ManyToOne**: Defines a many-to-one relationship, where multiple entities can be associated with one entity.
  - Example:
    ```java
    @ManyToOne
    @JoinColumn(name = "user_id")
    private User user;
    ```

---

### 1️⃣2️⃣ What is the role of **Transaction** in Hibernate and JPA?  
- **Transaction** is used to ensure that a group of operations is executed in a consistent, atomic way.
- In Hibernate and JPA, it is used to manage the persistence context, committing or rolling back changes to the database.
  ```java
  Session session = sessionFactory.openSession();
  Transaction transaction = session.beginTransaction();
  session.save(user);
  transaction.commit();
  ```

---

### 1️⃣3️⃣ What is the purpose of **@Transient** annotation in JPA?  
- The **@Transient** annotation is used to mark a field in an entity that should not be persisted to the database.
- It is useful for marking fields that are used for business logic or calculations but do not require storage in the database.

---

### 1️⃣4️⃣ How do you configure **Hibernate** in a Spring Boot application?  
- **Configuration** in Spring Boot is done via `application.properties` or `application.yml`.
  Example:
  ```properties
  spring.datasource.url=jdbc:mysql://localhost:3306/mydb
  spring.datasource.username=root
  spring.datasource.password=root
  spring.jpa.hibernate.ddl-auto=update
  spring.jpa.database-platform=org.hibernate.dialect.MySQL5Dialect
  ```

---

### 1️⃣5️⃣ What is **@Query** annotation in Spring Data JPA?  
- The **@Query** annotation is used to define custom queries in Spring Data JPA repositories.
- It can be used for both JPQL and native SQL queries.
  Example:
  ```java
  @Query("SELECT u FROM User u WHERE u.username = :username")
  User findByUsername(@Param("username") String username);
  ```

---

# 📂 **Microservices**

---

### 1️⃣ What are **Microservices**?  
- **Microservices** is an architectural style where a system is designed as a collection of small, loosely coupled services, each responsible for a specific business function.
- Each microservice can be developed, deployed, and scaled independently. They communicate with each other via lightweight protocols (usually HTTP/REST or messaging queues).

---

### 2️⃣ What are the **advantages** of using **Microservices**?  
- **Scalability**: Individual services can be scaled independently based on demand.
- **Flexibility**: You can use different technologies for different services (polyglot persistence).
- **Fault isolation**: A failure in one service does not affect the others.
- **Continuous Deployment**: Microservices support agile development and can be deployed independently.
- **Improved maintainability**: Smaller services are easier to understand, develop, and maintain.

---

### 3️⃣ What are the **disadvantages** of using **Microservices**?  
- **Complexity**: Microservices introduce complexity due to distributed systems, communication between services, and service discovery.
- **Data Management**: Each service may have its own database, making data consistency harder to achieve.
- **Latency**: Network calls between services can introduce latency.
- **Deployment Overhead**: Managing multiple services can lead to higher operational overhead.

---

### 4️⃣ What are **RESTful APIs** in Microservices?  
- **RESTful APIs** are HTTP-based APIs that follow the principles of Representational State Transfer (REST). These APIs are commonly used in microservices for communication between services.
- RESTful APIs:
  - Use HTTP methods (GET, POST, PUT, DELETE) for CRUD operations.
  - Are stateless (no session information is stored between requests).
  - Operate with resource URIs to represent entities.

---

### 5️⃣ What is **Service Discovery** in Microservices?  
- **Service Discovery** is the mechanism by which services in a microservices architecture locate and communicate with each other.
- Popular tools for service discovery:
  - **Eureka** (Netflix OSS)
  - **Consul**
  - **Zookeeper**
- The service registry keeps track of available services and their instances, while clients query the registry to discover services dynamically.

---

### 6️⃣ What is **API Gateway** in Microservices?  
- An **API Gateway** is a server that acts as an entry point for client requests to a microservices system.
- It routes requests to the appropriate microservices, handles load balancing, and performs tasks such as authentication, logging, and rate limiting.
- Example: **Spring Cloud Gateway**, **Zuul**.

---

### 7️⃣ What is the role of **Spring Cloud** in Microservices?  
- **Spring Cloud** provides tools for building and managing microservices, including service discovery, configuration management, messaging, and more.
- Common features:
  - **Spring Cloud Netflix**: Provides tools like Eureka (service discovery), Ribbon (client-side load balancing), and Hystrix (fault tolerance).
  - **Spring Cloud Config**: Centralized configuration management.
  - **Spring Cloud Stream**: Messaging and event-driven architectures.
  - **Spring Cloud Gateway**: API Gateway functionality.

---

### 8️⃣ What is **Spring Boot**'s role in Microservices?  
- **Spring Boot** simplifies the process of setting up and configuring microservices. It provides:
  - Embedded web servers (Tomcat, Jetty, etc.).
  - Auto-configuration to minimize boilerplate code.
  - Embedded support for microservices-related features (e.g., Spring Cloud integration).
  - Easy integration with databases, messaging systems, and other services.

---

### 9️⃣ What is **Circuit Breaker** in Microservices?  
- A **Circuit Breaker** is a design pattern used to prevent cascading failures when a service fails or becomes unavailable.
- It monitors the communication between microservices and triggers fallback mechanisms when a service is down or has issues.
- Common tools for circuit breaking:
  - **Hystrix** (from Netflix)
  - **Resilience4j**
  - **Spring Cloud Circuit Breaker**

---

### 🔟 What is **Event-Driven Architecture** in Microservices?  
- **Event-Driven Architecture (EDA)** involves services communicating asynchronously by producing and consuming events (messages).
- This pattern is commonly used in microservices to decouple services, ensuring that a service does not directly call another service but rather reacts to events/messages.
- Popular tools for event-driven architectures:
  - **Kafka**
  - **RabbitMQ**
  - **ActiveMQ**

---

### 1️⃣1️⃣ What is **Database per Service** in Microservices?  
- **Database per Service** is a pattern where each microservice manages its own database schema. This ensures that each service is loosely coupled and independently deployable.
- Benefits:
  - Service autonomy in terms of data management.
  - No shared database, which reduces potential bottlenecks.
  - Different databases (e.g., SQL, NoSQL) can be used for different services.
- Challenges:
  - Ensuring consistency and transactions across services.
  - Complex data management and integration.

---

### 1️⃣2️⃣ What is **SAGA Pattern** in Microservices?  
- The **SAGA** pattern is used to manage distributed transactions in a microservices architecture.
- It breaks a distributed transaction into a series of smaller, isolated transactions that can be completed independently.
- There are two approaches:
  - **Choreography-based**: Each service knows what to do next.
  - **Orchestration-based**: A central service manages the sequence of operations.

---

### 1️⃣3️⃣ How does **Centralized Logging** work in Microservices?  
- **Centralized Logging** aggregates logs from all microservices into a central system.
- Tools:
  - **ELK Stack** (Elasticsearch, Logstash, Kibana)
  - **Fluentd**
  - **Splunk**
- Centralized logging is crucial for debugging and monitoring microservices, as it allows you to view logs from all services in one place.

---

### 1️⃣4️⃣ What is **Monitoring and Health Checks** in Microservices?  
- **Monitoring** ensures that each microservice is functioning properly by tracking metrics such as latency, request rates, and error rates.
- **Health Checks** provide a way to check whether a microservice is healthy and able to handle traffic.
- Common tools:
  - **Prometheus** and **Grafana** for metrics and visualization.
  - **Spring Boot Actuator** for built-in health checks.
  - **Micrometer** for metrics collection.

---

### 1️⃣5️⃣ What is **Fault Tolerance** in Microservices?  
- **Fault Tolerance** is the ability of a system to continue functioning even when some components fail.
- Techniques to improve fault tolerance in microservices:
  - **Retries**: Automatically retry failed requests.
  - **Circuit Breaker**: Prevent cascading failures by stopping calls to failing services.
  - **Timeouts**: Set timeouts for service calls to prevent blocking.
  - **Bulkheads**: Isolate services to prevent failures from spreading.

---

# 📂 **Oracle NoSQL & MongoDB**

---

### 1️⃣ What is **NoSQL**?  
- **NoSQL** stands for "Not Only SQL," and it refers to a broad class of database management systems designed to handle unstructured or semi-structured data.
- NoSQL databases are more flexible and scalable than traditional relational databases (RDBMS), making them ideal for handling big data and real-time web applications.
- Types of NoSQL databases:
  - **Document-based** (e.g., MongoDB, CouchDB)
  - **Key-Value stores** (e.g., Redis, DynamoDB)
  - **Column-family stores** (e.g., Cassandra, HBase)
  - **Graph databases** (e.g., Neo4j, Amazon Neptune)

---

### 2️⃣ What is **MongoDB**?  
- **MongoDB** is a document-based NoSQL database. It stores data in flexible, JSON-like documents (BSON format) rather than in rows and columns.
- MongoDB is designed for scalability and high availability, offering horizontal scaling (sharding) and built-in replication.

---

### 3️⃣ What are the advantages of using **MongoDB**?  
- **Scalability**: MongoDB supports horizontal scaling (sharding), which allows you to distribute data across multiple servers.
- **Flexible schema**: MongoDB uses a schema-less design, so each document can have different fields.
- **High Availability**: MongoDB provides built-in replication to ensure data availability and fault tolerance.
- **Rich Query Language**: MongoDB supports a powerful query language, including indexing, aggregation, and full-text search.

---

### 4️⃣ What is **BSON** in MongoDB?  
- **BSON (Binary JSON)** is the format in which MongoDB stores data. It is a binary representation of JSON-like documents.
- BSON extends the capabilities of JSON by adding support for additional data types like `ObjectId`, `Date`, and `Binary`.

---

### 5️⃣ What are the basic CRUD operations in **MongoDB**?  
- **Create**: Insert a document into a collection.
  ```javascript
  db.users.insertOne({ name: "John", age: 30 });
  ```
- **Read**: Retrieve documents from a collection.
  ```javascript
  db.users.find({ name: "John" });
  ```
- **Update**: Modify existing documents.
  ```javascript
  db.users.updateOne({ name: "John" }, { $set: { age: 31 } });
  ```
- **Delete**: Remove documents from a collection.
  ```javascript
  db.users.deleteOne({ name: "John" });
  ```

---

### 6️⃣ What is **Sharding** in MongoDB?  
- **Sharding** is the process of distributing data across multiple servers to ensure horizontal scalability. Each shard is a subset of the data, and together they form a sharded cluster.
- MongoDB automatically distributes documents across shards based on a shard key.

---

### 7️⃣ What is **Replication** in MongoDB?  
- **Replication** ensures that data is copied to multiple MongoDB instances for redundancy and high availability.
- In a replica set, one node is the primary (handles writes) and others are secondary (replica copies of the primary).
- If the primary node fails, a secondary node can be promoted to primary.

---

### 8️⃣ What is the difference between **MongoDB** and **Relational Databases**?  
- **Schema**: MongoDB is schema-less, while relational databases require predefined schemas.
- **Data Model**: MongoDB uses collections of documents, while relational databases use tables with rows and columns.
- **Scalability**: MongoDB supports horizontal scaling through sharding, while relational databases are typically scaled vertically (adding more resources to a single server).

---

### 9️⃣ What is **Oracle NoSQL Database**?  
- **Oracle NoSQL Database** is a distributed key-value store designed for high availability, scalability, and flexibility.
- It supports both key-value and document data models and is optimized for large-scale applications.
- It provides features like automatic sharding, replication, and strong consistency.

---

### 🔟 What are the key differences between **Oracle NoSQL Database** and **MongoDB**?  
- **Data Model**: 
  - MongoDB is a document-oriented database, while Oracle NoSQL can support key-value, document, and other models.
- **Consistency**: 
  - Oracle NoSQL provides strong consistency by default, while MongoDB provides eventual consistency in a distributed setup.
- **Sharding and Scalability**: 
  - Both support sharding, but Oracle NoSQL is often considered more suitable for large-scale, distributed enterprise applications.

---

### 1️⃣1️⃣ How do you define **Indexes** in MongoDB?  
- **Indexes** are used in MongoDB to improve the performance of query operations. Without indexes, MongoDB must scan every document in the collection.
- MongoDB supports several types of indexes:
  - **Single-field indexes**: Indexes on a single field.
  - **Compound indexes**: Indexes on multiple fields.
  - **Text indexes**: For full-text search.
  - **Geospatial indexes**: For location-based queries.
- Example of creating an index:
  ```javascript
  db.users.createIndex({ name: 1 });
  ```

---

### 1️⃣2️⃣ What are **Aggregation** and **Aggregation Pipeline** in MongoDB?  
- **Aggregation** in MongoDB is used to process data records and return computed results.
- The **Aggregation Pipeline** is a framework that processes data in stages (similar to SQL's `GROUP BY` and `HAVING` clauses).
- Example:
  ```javascript
  db.orders.aggregate([
    { $match: { status: "completed" } },
    { $group: { _id: "$customer_id", totalAmount: { $sum: "$amount" } } }
  ]);
  ```

---

### 1️⃣3️⃣ How does **MongoDB** ensure **Data Consistency**?  
- MongoDB provides **strong consistency** in a single-node setup, meaning reads always return the most recent write.
- In a replica set, MongoDB uses **Read Preferences** to allow you to specify whether to read from primary or secondary nodes, impacting consistency and performance.
- **Write Concern** is a setting that ensures data is written to a specific number of nodes for consistency.

---

### 1️⃣4️⃣ What are **Transactions** in MongoDB, and how do they work?  
- MongoDB supports **multi-document transactions**, allowing you to perform multiple operations in a single, atomic transaction.
- This feature provides ACID guarantees (Atomicity, Consistency, Isolation, Durability) for multiple documents or collections.
- Example:
  ```javascript
  const session = db.getMongo().startSession();
  session.startTransaction();
  db.collection1.insertOne({ name: "John" }, { session });
  db.collection2.updateOne({ name: "John" }, { $set: { age: 30 } }, { session });
  session.commitTransaction();
  ```

---

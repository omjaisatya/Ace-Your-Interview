### Java Interview Questions and Answers 


## 1. What is Java?
**Answer:** Java is a high-level, class-based, object-oriented programming language that is designed to have as few implementation dependencies as possible. It is a general-purpose programming language intended to let application developers write once, run anywhere (WORA), meaning that compiled Java code can run on all platforms that support Java without the need for recompilation.

## 2. What are the main features of Java?
**Answer:** 
- Simple
- Object-Oriented
- Platform Independent
- Secured
- Robust
- Architecture Neutral
- Portable
- Dynamic
- Interpreted
- High Performance
- Multithreaded
- Distributed

## 3. What is JVM, JRE, and JDK?
**Answer:**
- **JVM (Java Virtual Machine):** It is an abstract machine that provides the runtime environment in which Java bytecode can be executed. It is platform-dependent.
- **JRE (Java Runtime Environment):** It includes the JVM and provides libraries, Java Virtual Machine (JVM), and other components to run applications written in Java.
- **JDK (Java Development Kit):** It is a full-featured software development kit for Java, including JRE, an interpreter/loader (Java), a compiler (javac), an archiver (jar), a documentation generator (Javadoc), and other tools needed for Java development.

## 4. What is the difference between a JDK and a JRE?
**Answer:** 
- **JDK (Java Development Kit):** It is used for developing Java applications and includes tools like a compiler (javac), a debugger, and other development tools. It also includes the JRE.
- **JRE (Java Runtime Environment):** It provides the libraries, Java Virtual Machine (JVM), and other components to run Java applications. It does not include development tools like a compiler or debugger.

## 5. What is a class in Java?
**Answer:** A class is a blueprint from which individual objects are created. A class can contain fields and methods to define the behaviors and properties of an object. For example:
```java
public class Dog {
    String breed;
    int age;
    String color;

    void barking() {
    }

    void hungry() {
    }

    void sleeping() {
    }
}
```

## 6. What is an object in Java?
**Answer:** An object is an instance of a class. It has state and behavior. For example, a dog is an object with properties like breed, age, and color, and behaviors like barking, hungry, and sleeping.

## 7. What are the OOP principles in Java?
**Answer:** The four main principles of Object-Oriented Programming are:
- **Inheritance:** The mechanism in Java by which one class is allowed to inherit the features (fields and methods) of another class.
- **Encapsulation:** The wrapping up of data and methods into a single unit (class). It also involves data hiding and access control.
- **Polymorphism:** The ability of a variable, function, or object to take on multiple forms. It includes method overloading and method overriding.
- **Abstraction:** The concept of hiding the complex implementation details and showing only the necessary features of the object.

## 8. What is the difference between method overloading and method overriding?
**Answer:**
- **Method Overloading:** It occurs when two or more methods in the same class have the same name but different parameters. It is a compile-time polymorphism.
- **Method Overriding:** It occurs when a subclass has a method with the same name and parameters as a method in its superclass. It is a runtime polymorphism.

## 9. What is an interface in Java?
**Answer:** An interface in Java is a reference type, similar to a class, that can contain only constants, method signatures, default methods, static methods, and nested types. Interfaces cannot contain instance fields or constructors. They are used to achieve abstraction and multiple inheritance in Java.

## 10. What is a constructor in Java?
**Answer:** A constructor is a special method that is called when an object is instantiated. It is used to initialize the state of an object. Constructors have the same name as the class and do not have a return type.

## 11. What is the difference between `==` and `equals()` in Java?
**Answer:**
- `==` is an operator that compares the references of two objects to see if they point to the same memory location.
- `equals()` is a method that compares the contents of two objects to see if they are logically equal. The `equals()` method can be overridden to provide custom equality logic.

## 12. What is exception handling in Java?
**Answer:** Exception handling is a mechanism to handle runtime errors, allowing the normal flow of the application to be maintained. It uses five keywords: `try`, `catch`, `finally`, `throw`, and `throws`.

## 13. What is the difference between checked and unchecked exceptions?
**Answer:**
- **Checked Exceptions:** These are exceptions that are checked at compile-time. They must be either handled using a try-catch block or declared using the throws keyword. Example: `IOException`, `SQLException`.
- **Unchecked Exceptions:** These are exceptions that are not checked at compile-time. They are usually caused by programming bugs, such as logic errors or improper use of an API. Example: `NullPointerException`, `ArrayIndexOutOfBoundsException`.

## 14. What is the `finally` block in Java?
**Answer:** The `finally` block is a block of code that always executes, regardless of whether an exception is thrown or not. It is used to execute important code, such as closing resources, that must be executed even if an error occurs.

## 15. What is the purpose of the `static` keyword in Java?
**Answer:** The `static` keyword in Java is used for memory management. It can be applied to variables, methods, blocks, and nested classes. The static keyword means that the member belongs to the class itself rather than to any specific instance of the class. Static members can be accessed without creating an instance of the class.

## 16. What is the `final` keyword in Java?
**Answer:** The `final` keyword in Java is used to restrict the user. It can be applied to variables, methods, and classes.
- When applied to a variable, it makes the variable a constant.
- When applied to a method, it prevents the method from being overridden.
- When applied to a class, it prevents the class from being subclassed.

## 17. What is a `thread` in Java?
**Answer:** A thread in Java is a lightweight subprocess, the smallest unit of processing. It is a separate path of execution and can be used to perform multitasking in Java. Java provides built-in support for multithreading through the `java.lang.Thread` class and the `java.util.concurrent` package.

## 18. What is synchronization in Java?
**Answer:** Synchronization in Java is the capability to control the access of multiple threads to shared resources. It is used to prevent thread interference and consistency problems. The synchronized keyword can be applied to methods and blocks to ensure that only one thread can execute a block of code at a time.

## 19. What is garbage collection in Java?
**Answer:** Garbage collection in Java is the process of automatically freeing up memory by deleting objects that are no longer reachable in the program. The garbage collector runs in the background, identifying and disposing of objects that are no longer in use, thus helping to manage memory and avoid memory leaks.

## 20. What is the difference between `ArrayList` and `LinkedList` in Java?
**Answer:**
- **ArrayList:** It is a resizable array implementation of the `List` interface. It provides fast random access to elements but slow insertion and deletion operations as it requires shifting elements.
- **LinkedList:** It is a doubly linked list implementation of the `List` interface. It provides fast insertion and deletion operations but slower random access to elements as it requires traversal of the list.

## 21. What is the difference between `String`, `StringBuilder`, and `StringBuffer` in Java?
**Answer:**
- **String:** It is immutable, meaning once created, its value cannot be changed. Any modification creates a new `String` object.
- **StringBuilder:** It is mutable and not synchronized, making it faster than `StringBuffer`. It is used in a single-threaded environment.
- **StringBuffer:** It is mutable and synchronized, making it thread-safe but slower than `StringBuilder`.

## 22. What is the use of the `super` keyword in Java?
**Answer:** The `super` keyword in Java is used to refer to the immediate parent class object. It can be used to access parent class methods, constructors, and variables. It is commonly used in the following scenarios:
- To call the parent class constructor.
- To access the parent class variables.
- To access the parent class methods.

## 23. What is the difference between `abstract class` and `interface` in Java?
**Answer:**
- **Abstract Class:** It can have both abstract and concrete methods. It can have state (fields) and constructors. A class can extend only one abstract class.
- **Interface:** It can only have abstract methods (until Java 8, which introduced default and static methods). It cannot have state (fields). A class can implement multiple interfaces.

## 24. What is the difference between `HashMap` and `Hashtable` in Java?
**Answer:**
- **HashMap:** It is not synchronized, meaning it is not thread-safe. It allows one null key and multiple null values. It is faster than `Hashtable`.
- **Hashtable:** It is synchronized, meaning it is thread-safe. It does not allow any null keys or values.

## 25. What is the Java Collections Framework?
**Answer:** The Java Collections Framework is a set of classes and interfaces that implement commonly reusable collection data structures. It includes interfaces such as `List`, `Set`, and `Map`, and classes like `ArrayList`, `HashSet`, `HashMap`, and `LinkedList`.

## 26. What is the `Iterator` in Java?
**Answer:** An `Iterator` is an interface in the Java Collections Framework that provides methods to traverse a collection. It provides methods such as `hasNext()`, `next()`, and `remove()`. The `Iterator` allows the caller to remove elements from the underlying collection during the iteration.

## 27. What is the purpose of the `transient` keyword in Java?
**Answer:** The `transient` keyword in Java is used to indicate that a field should not be serialized. When an object is serialized, transient fields are ignored and not included in the serialized representation.

## 28. What is the `volatile` keyword in Java?
**Answer:** The `volatile` keyword in Java is used to indicate that a variable's value will be modified by different threads. It ensures that the value of the volatile variable is always read from the main memory, and not from the thread's local cache, ensuring visibility of changes across threads.

## 29. What is reflection in Java?
**Answer:** Reflection in Java is a feature that allows the inspection and manipulation of classes, methods, and fields at runtime. It is provided through the `java.lang.reflect` package. Reflection is used for various purposes, such as inspecting class properties, invoking methods, and accessing fields dynamically.

## 30. What is the difference between `public`, `protected`, `private`, and default access modifiers in Java?
**Answer:**
- **public:** The member is accessible from any other class.
- **protected:** The member is accessible within the same package and by subclasses in other packages.
- **private:** The member is accessible only within the same class.
- **default (no modifier):** The member is accessible only within the same package.

## 31. What is the Singleton design pattern?
**Answer:** The Singleton design pattern ensures that a class has only one instance and provides a global point of access to it. It is commonly implemented using a private constructor and a static method that returns the single instance.

## 32. What is dependency injection?
**Answer:** Dependency injection is a design pattern used to implement inversion of control, allowing an object's dependencies to be injected rather than hard-coded. It promotes loose coupling and enhances testability and maintainability of code.

## 33. What is the difference between `==` and `equals()` in Java?
**Answer:**
- `==` compares the references of two objects to check if they point to the same memory location.
- `equals()` compares the contents of two objects for logical equality. The `equals()` method can be overridden to provide custom equality logic.

## 34. What is the use of the `this` keyword in Java?
**Answer:** The `this` keyword in Java is a reference to the current object. It can be used to refer to the current instance's variables, methods, and constructors. It is often used to resolve naming conflicts and to pass the current object as a parameter.

## 35. What are lambda expressions in Java?
**Answer:** Lambda expressions, introduced in Java 8, provide a clear and concise way to represent one method interface using an expression. They are used primarily to define inline implementations of functional interfaces, enabling functional programming features in Java.

## 36. What is the Stream API in Java?
**Answer:** The Stream API, introduced in Java 8, provides a functional programming approach to processing sequences of elements. It supports operations such as map, filter, and reduce, enabling efficient and expressive data manipulation.

## 37. What is the Optional class in Java?
**Answer:** The `Optional` class, introduced in Java 8, is a container object used to represent the presence or absence of a value. It provides methods to deal with values that may or may not be present, reducing the need for explicit null checks.

## 38. What are functional interfaces in Java?
**Answer:** Functional interfaces are interfaces with a single abstract method, used as the basis for lambda expressions and method references. Examples include `Runnable`, `Callable`, `Comparator`, and the interfaces in the `java.util.function` package.

## 39. What is method reference in Java?
**Answer:** Method reference is a shorthand notation of a lambda expression to call a method. It uses the `::` operator and can refer to static methods, instance methods, or constructors.

## 40. What is the CompletableFuture class in Java?
**Answer:** `CompletableFuture` is a class in the `java.util.concurrent` package that represents a future result of an asynchronous computation. It provides a comprehensive API for asynchronous programming, allowing the composition of multiple tasks and handling their results.


## 41. What is a lambda expression in Java?
**Answer:** Lambda expressions are a feature introduced in Java 8 that allows you to write concise code for functional interfaces (interfaces with a single abstract method). They provide a clear and concise way to represent one method interface using an expression. Lambda expressions are used primarily to define the inline implementation of a functional interface.

## 42. What is the difference between `Runnable` and `Callable` in Java?
**Answer:**
- **Runnable:** It is an interface representing a task that can be executed by a thread. It has a single `run()` method that does not return any result and cannot throw checked exceptions.
- **Callable:** It is an interface introduced in Java 5 that represents a task that can be executed by a thread. It has a single `call()` method that returns a result and can throw checked exceptions.

## 43. What is the difference between `wait()` and `sleep()` in Java?
**Answer:**
- **wait():** It is a method of the `Object` class that causes the current thread to wait until another thread invokes the `notify()` or `notifyAll()` method on the same object. It releases the lock on the object.
- **sleep():** It is a method of the `Thread` class that causes the current thread to sleep for a specified number of milliseconds. It does not release the lock on the object.

## 44. What is a thread pool in Java?
**Answer:** A thread pool is a group of pre-instantiated reusable threads that are available for performing tasks. Using a thread pool helps in reducing the overhead of creating and destroying threads for each task. The `java.util.concurrent` package provides the `Executor` framework for managing thread pools.

## 45. What is the `synchronized` keyword in Java?
**Answer:** The `synchronized` keyword is used to control the access of multiple threads to a shared resource. It can be applied to methods or blocks of code to ensure that only one thread can execute the synchronized code at a time. It helps in preventing thread interference and maintaining data consistency.

## 46. What are generics in Java?
**Answer:** Generics enable types (classes and interfaces) to be parameters when defining classes, interfaces, and methods. They provide type safety by allowing you to define a class or a method with a placeholder for a data type. Generics eliminate the need for type casting and prevent runtime errors by catching type-related issues at compile-time.

## 47. What is the `enum` keyword in Java?
**Answer:** The `enum` keyword is used to define a set of named constants. An enum is a special class that represents a group of constants (unchangeable variables, like final variables). Enums are useful for representing a fixed set of constants, such as days of the week, directions, etc.

## 48. What is a nested class in Java?
**Answer:** A nested class is a class defined within another class. There are four types of nested classes in Java:
- **Static nested class:** A static nested class is a static member of the outer class. It can access static members of the outer class.
- **Inner class (non-static nested class):** It is a non-static member of the outer class and can access all members of the outer class.
- **Local class:** It is a class defined within a method or a block of code.
- **Anonymous class:** It is a class without a name, used for instantiating objects with certain modifications, usually defined within a method.

## 49. What is the diamond operator in Java?
**Answer:** The diamond operator (`<>`) is a feature introduced in Java 7 that allows you to avoid specifying the type parameters on the right side of the variable declaration. It simplifies the code by inferring the type from the context, reducing redundancy. Example:
```java
List<String> list = new ArrayList<>();
```

## 50. What is the purpose of the `default` keyword in interfaces?
**Answer:** The `default` keyword, introduced in Java 8, allows you to define default methods in interfaces. Default methods are methods with a body that can be overridden by implementing classes. They provide a way to add new methods to interfaces without breaking existing implementations.

## 51. What is the `Optional` class in Java?
**Answer:** The `Optional` class, introduced in Java 8, is a container object used to represent the presence or absence of a value. It helps in avoiding null checks and NullPointerExceptions by providing methods to deal with optional values in a functional style.

## 52. What is the `Stream` API in Java?
**Answer:** The `Stream` API, introduced in Java 8, provides a functional programming approach to process sequences of elements. It allows operations such as filtering, mapping, and reducing collections of data in a declarative manner. Streams enable efficient and expressive data processing.

## 53. What is method overloading in Java?
**Answer:** Method overloading is a feature in Java that allows you to define multiple methods with the same name but different parameters (different type, number, or both). It is a form of compile-time polymorphism that allows methods to be differentiated based on their signature.

## 54. What is method overriding in Java?
**Answer:** Method overriding is a feature in Java that allows a subclass to provide a specific implementation of a method that is already defined in its superclass. The overridden method must have the same name, return type, and parameters as the method in the superclass. It is a form of runtime polymorphism.

## 55. What is the purpose of the `transient` keyword in Java?
**Answer:** The `transient` keyword in Java is used to indicate that a field should not be serialized. When an object is serialized, transient fields are ignored and not included in the serialized representation. It is useful for fields that should not be persisted, such as temporary data or sensitive information.

## 56. What is the `volatile` keyword in Java?
**Answer:** The `volatile` keyword in Java is used to indicate that a variable's value will be modified by different threads. It ensures that the value of the volatile variable is always read from the main memory, and not from the thread's local cache, ensuring visibility of changes across threads.

## 57. What is the `finalize()` method in Java?
**Answer:** The `finalize()` method is a method of the `Object` class that is called by the garbage collector before an object is removed from memory. It provides an opportunity to clean up resources or perform other cleanup operations. However, it is not recommended to rely on `finalize()` for resource management, as it is unpredictable and can lead to performance issues.

## 58. What is the difference between `ArrayList` and `LinkedList` in Java?
**Answer:**
- **ArrayList:** It is a resizable array implementation of the `List` interface. It provides fast random access to elements but slow insertion and deletion operations as it requires shifting elements.
- **LinkedList:** It is a doubly linked list implementation of the `List` interface. It provides fast insertion and deletion operations but slower random access to elements as it requires traversal of the list.

## 59. What is the `Comparator` interface in Java?
**Answer:** The `Comparator` interface is used to define a custom comparison logic for sorting objects. It has a single method `compare()` that compares two objects and returns an integer indicating their relative order. It can be used to sort collections of objects with custom criteria.

## 60. What is the difference between `abstract class` and `interface` in Java?
**Answer:**
- **Abstract Class:** It can have both abstract and concrete methods. It can have state (fields) and constructors. A class can extend only one abstract class.
- **Interface:** It can only have abstract methods (until Java 8, which introduced default and static methods). It cannot have state (fields). A class can implement multiple interfaces.

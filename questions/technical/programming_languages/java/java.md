
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

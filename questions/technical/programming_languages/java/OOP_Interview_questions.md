# OOP Interview Questions and Answers

## 1. What is Object-Oriented Programming (OOP)?

**Answer:**  
Object-Oriented Programming (OOP) is a programming paradigm based on the concept of objects. Objects contain data in the form of fields (often referred to as attributes or properties) and code in the form of procedures (often referred to as methods). OOP is centered around four main principles: Encapsulation, Abstraction, Inheritance, and Polymorphism.

---

## 2. What is a Class in OOP?

**Answer:**  
A class is a blueprint or prototype from which objects are created. It defines a set of attributes and methods that the created objects (instances) will have. A class encapsulates data for the object and methods to manipulate that data.

---

## 3. What is an Object in OOP?

**Answer:**  
An object is an instance of a class. It is a self-contained entity that consists of both data and methods to manipulate the data. Objects interact with one another by sending messages or invoking methods.

---

## 4. What is Encapsulation?

**Answer:**  
Encapsulation is the concept of wrapping data (variables) and methods (functions) that work on the data into a single unit or class. It restricts direct access to some of the object's components, which is a means of preventing unintended interference and misuse of the data.

---

## 5. What is Abstraction?

**Answer:**  
Abstraction is the process of hiding the implementation details and showing only the functionality to the user. It allows focusing on what the object does instead of how it does it. Abstraction is achieved using abstract classes and interfaces.

---

## 6. What is Inheritance?

**Answer:**  
Inheritance is a mechanism where one class acquires the properties (fields and methods) of another class. The class that is inherited is called the superclass (or base class), and the class that inherits is called the subclass (or derived class). Inheritance promotes code reusability.

---

## 7. What is Polymorphism?

**Answer:**  
Polymorphism means "many forms," and it allows objects of different classes to be treated as objects of a common superclass. It occurs when a subclass can define its unique behavior while still sharing the same interface or method signature as the superclass.

---

## 8. What is Method Overloading?

**Answer:**  
Method overloading is a feature that allows a class to have more than one method with the same name, but with different parameters (different type, number, or both). It is a way to implement compile-time polymorphism.

---

## 9. What is Method Overriding?

**Answer:**  
Method overriding occurs when a subclass provides a specific implementation of a method that is already defined in its superclass. The method in the subclass must have the same name, return type, and parameters as the method in the superclass. This is an example of runtime polymorphism.

---

## 10. What is the difference between an Abstract Class and an Interface?

**Answer:**  
- **Abstract Class:** Can have both abstract methods (without implementation) and concrete methods (with implementation). A class can inherit only one abstract class.
- **Interface:** Can only have abstract methods (before Java 8) and default methods (from Java 8 onwards). A class can implement multiple interfaces. Interfaces are used to achieve complete abstraction and multiple inheritance.

---

## 11. What is a Constructor in OOP?

**Answer:**  
A constructor is a special method that is called when an object is instantiated. It is used to initialize the object. A constructor has the same name as the class and does not have a return type.

---

## 12. What is the difference between a Constructor and a Method?

**Answer:**  
- **Constructor:** Initializes an object when it is created. It has the same name as the class and no return type.
- **Method:** A function defined within a class that performs a specific task. Methods can have a return type and can be called multiple times.

---

## 13. What is Multiple Inheritance? Does Java support it?

**Answer:**  
Multiple inheritance is a feature where a class can inherit from more than one superclass. Java does not support multiple inheritance with classes to avoid ambiguity and complexity. However, it supports multiple inheritance using interfaces.

---

## 14. What is the `super` keyword in Java?

**Answer:**  
The `super` keyword in Java is used to refer to the immediate parent class object. It can be used to call superclass methods, access superclass variables, and invoke the superclass constructor.

---

## 15. What is the difference between `==` and `equals()` in Java?

**Answer:**  
- `==`: Compares the reference or memory address of objects. It checks whether both objects point to the same memory location.
- `equals()`: Compares the actual content of objects. It is used to compare the values of two objects for equality.

---

## 16. What is Dynamic Binding in OOP?

**Answer:**  
Dynamic binding, also known as late binding, occurs when the method to be called is determined at runtime instead of at compile-time. This is typically used in method overriding where the method called depends on the object’s runtime type.

---

## 17. What is the Open/Closed Principle in OOP?

**Answer:**  
The Open/Closed Principle states that software entities (classes, modules, functions, etc.) should be open for extension but closed for modification. This means that the behavior of a module can be extended without modifying its source code, typically by using interfaces or abstract classes.

---

## 18. What is the Liskov Substitution Principle?

**Answer:**  
The Liskov Substitution Principle (LSP) states that objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program. This ensures that a subclass can stand in for its superclass.

---

## 19. What is Composition in OOP?

**Answer:**  
Composition is a design principle where a class is composed of one or more objects from other classes, implying a "has-a" relationship. It is a way to build complex classes by combining simpler, reusable classes. Unlike inheritance, composition provides greater flexibility by allowing dynamic changes to the components of the class.

---

## 20. What is a Singleton Pattern?

**Answer:**  
The Singleton Pattern is a design pattern that restricts the instantiation of a class to a single instance. This is useful when exactly one object is needed to coordinate actions across the system. The Singleton class typically provides a static method to get the instance of the class.

# Object-Oriented Programming (OOP) Concepts

## 1. Introduction to OOP

Object-Oriented Programming (OOP) is a programming paradigm that uses objects and classes to design software applications.

### Key Features of OOP:

- Encapsulation
- Inheritance
- Polymorphism
- Abstraction

---

## 2. Core OOP Concepts

### 2.1 Class and Object

- **Class**: A blueprint for creating objects.
- **Object**: An instance of a class.

Example:

```python
class Car:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

    def display(self):
        print(f"Car: {self.brand} {self.model}")

car1 = Car("Toyota", "Corolla")
car1.display()
```

---

### 2.2 Encapsulation

Encapsulation is the concept of restricting direct access to some data and methods.

Example:

```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance  # Private variable

    def get_balance(self):
        return self.__balance

account = BankAccount(1000)
print(account.get_balance())  # Allowed
# print(account.__balance)  # Not Allowed (Throws Error)
```

---

### 2.3 Inheritance

Inheritance allows one class to inherit properties and methods from another class.

Example:

```python
class Animal:
    def make_sound(self):
        print("Some generic sound")

class Dog(Animal):
    def make_sound(self):
        print("Bark")

dog = Dog()
dog.make_sound()
```

---

### 2.4 Polymorphism

Polymorphism allows different classes to be treated as instances of the same class through a common interface.

Example:

```python
class Bird:
    def fly(self):
        print("Some birds can fly")

class Sparrow(Bird):
    def fly(self):
        print("Sparrow can fly fast")

class Penguin(Bird):
    def fly(self):
        print("Penguins cannot fly")

for bird in [Sparrow(), Penguin()]:
    bird.fly()
```

---

### 2.5 Abstraction

Abstraction hides implementation details and only shows relevant functionality.

Example:

```python
from abc import ABC, abstractmethod

class Vehicle(ABC):
    @abstractmethod
    def start_engine(self):
        pass

class Car(Vehicle):
    def start_engine(self):
        print("Car engine started")

car = Car()
car.start_engine()
```

---

## 3. Advantages of OOP

- Code reusability
- Scalability
- Data security
- Improved maintainability

## 4. Common OOP Interview Questions

### 1. **What are the four pillars of OOP?**

**Answer:** The four pillars of OOP are:

- Encapsulation
- Inheritance
- Polymorphism
- Abstraction

### 2. **Explain the difference between abstraction and encapsulation.**

**Answer:**

- **Abstraction** hides implementation details and only shows relevant functionality.
- **Encapsulation** restricts direct access to data by wrapping it inside a class with access control mechanisms.

### 3. **How does method overriding work in Python?**

**Answer:** Method overriding occurs when a subclass provides a specific implementation of a method already defined in its parent class.

```python
class Parent:
    def show(self):
        print("Parent class")

class Child(Parent):
    def show(self):
        print("Child class")

obj = Child()
obj.show()  # Output: Child class
```

### 4. **What is the difference between class and object?**

**Answer:**

- A **class** is a blueprint for creating objects.
- An **object** is an instance of a class with actual values.

### 5. **What is multiple inheritance? Provide an example.**

**Answer:** Multiple inheritance allows a class to inherit from more than one parent class.

```python
class A:
    def method_a(self):
        print("A method")

class B:
    def method_b(self):
        print("B method")

class C(A, B):
    pass

obj = C()
obj.method_a()
obj.method_b()
```

### 6. **What is the difference between method overloading and method overriding?**

**Answer:**

- **Method overloading** allows multiple methods in the same class with different parameters (not directly supported in Python).
- **Method overriding** is redefining a parent class method in a subclass.

### 7. **Can you instantiate an abstract class?**

**Answer:** No, abstract classes cannot be instantiated. They are meant to be inherited by subclasses.

### 8. **What is a constructor in OOP?**

**Answer:** A constructor is a special method that initializes an object when it is created. In Python, it is `__init__()`.

### 9. **Explain the significance of the `super()` function in Python.**

**Answer:** The `super()` function allows a subclass to access methods of its parent class.

### 10. **What are access specifiers? Explain their types.**

**Answer:** Access specifiers define the visibility of class attributes and methods:

- `public`: Accessible everywhere
- `_protected`: Accessible within the class and its subclasses
- `__private`: Accessible only within the class

### 11. **What is the difference between composition and inheritance?**

**Answer:**

- **Inheritance** represents an "is-a" relationship.
- **Composition** represents a "has-a" relationship (one class contains an object of another class).

### 12. **How does dynamic polymorphism work?**

**Answer:** Dynamic polymorphism allows method overriding where the method to be called is determined at runtime.

### 13. **What is an interface in OOP, and how is it implemented?**

**Answer:** An interface defines a contract that implementing classes must follow. In Python, abstract classes with `ABC` module serve as interfaces.

### 14. **Explain duck typing in Python.**

**Answer:** Duck typing is a concept where the type of an object is determined by its behavior rather than its class.

### 15. **What is the difference between shallow copy and deep copy in Python?**

**Answer:**

- **Shallow copy** creates a new object but references the same nested objects.
- **Deep copy** creates a completely independent copy of the object.

```python
import copy
list1 = [[1, 2], [3, 4]]
shallow = copy.copy(list1)
deep = copy.deepcopy(list1)
```

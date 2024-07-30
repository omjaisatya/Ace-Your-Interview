# TypeScript Interview Questions

## 1. What is TypeScript?

**Answer:**
TypeScript is a superset of JavaScript developed by Microsoft. It adds static types to JavaScript, allowing developers to catch errors at compile time rather than runtime. TypeScript is compiled down to JavaScript, making it compatible with any environment that supports JavaScript.

## 2. What are the main benefits of using TypeScript over JavaScript?

**Answer:**
The main benefits of using TypeScript include:

- **Static Type Checking:** TypeScript's type system helps catch errors early in the development process.
- **Improved IDE Support:** TypeScript offers better autocompletion, navigation, and refactoring tools in modern IDEs.
- **Enhanced Readability and Maintainability:** Explicit types can make code more understandable and easier to maintain.
- **Advanced Language Features:** TypeScript includes features like interfaces, enums, and decorators that are not present in standard JavaScript.

## 3. How do you define a variable with a specific type in TypeScript?

**Answer:**
In TypeScript, you can define a variable with a specific type using a type annotation. For example:

```typescript
let age: number = 30;
let name: string = "John Doe";
let isActive: boolean = true;
```

## 4. What is an interface in TypeScript, and how is it used?

**Answer:**
An interface in TypeScript is a way to define the shape of an object, including its properties and methods. Interfaces help ensure that objects adhere to a specific structure. Here is an example:

```typescript
interface Person {
  name: string;
  age: number;
  greet(): void;
}

const person: Person = {
  name: "Alice",
  age: 25,
  greet: () => console.log("Hello!"),
};
```

## 5. What is the difference between `interface` and `type` in TypeScript?

**Answer:**
Both `interface` and `type` can be used to define object shapes and types in TypeScript, but there are some differences:

- **`interface`:** Used to define the structure of objects and can be extended or merged with other interfaces.
- **`type`:** Can define more complex types, including unions, intersections, and tuples, and cannot be extended in the same way as interfaces.
  _Example of `type`_:

```typescript
type Coordinates = { x: number; y: number };
```

## 6. How do you define optional properties in an interface?

**Answer:**
You can define optional properties in an interface using the `?` modifier. For example:

```typescript
interface Person {
  name: string;
  age?: number; // age is optional
}

const person1: Person = { name: "John" };
const person2: Person = { name: "Jane", age: 30 };
```

## 7. What is a `union type` in TypeScript?

**Answer**:
A union type allows a variable to be one of several types. It is defined using the `|` operator. For example:

```typescript
let value: number | string;
value = 42; // valid
value = "hello"; // valid
value = true; // error: Type 'boolean' is not assignable to type 'number | string'
```

## 8. How do you use generics in TypeScript?

**Answer**:
Generics allow you to create components or functions that work with a variety of types while still maintaining type safety. For example:

```typescript
function identity<T>(arg: T): T {
  return arg;
}

let output = identity<string>("Hello World");
```

## 9. What is the purpose of the `never` type in TypeScript?

**Answer**:
The `never` type represents values that never occur. It is used to indicate that a function never returns or that a variable should never hold a value. Common examples include functions that throw errors or enter infinite loops:

```typescript
function throwError(message: string): never {
  throw new Error(message);
}
```

## 10. How do you handle `null` and `undefined types` in TypeScript?

**Answer:**
In TypeScript, `null` and `undefined` are treated as separate types. To handle them, you can enable the `strictNullChecks` option in the TypeScript configuration file. This ensures that `null` and `undefined` are not automatically assignable to other types:

```typescript
let value: string | null = null;
value = "Hello"; // valid
value = undefined; // error if strictNullChecks is enabled
```

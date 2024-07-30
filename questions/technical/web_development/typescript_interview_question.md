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

## 11. What is type assertion in TypeScript?

**Answer:**
Type assertion is a way to inform the TypeScript compiler about the type of a variable when the developer is certain of its type. It does not perform any special checking or restructuring of data; it simply tells the compiler to treat a value as a specific type.

```typescript
let someValue: any = "Hello World";
let strLength: number = (someValue as string).length;
```

12. How can you use `type guards` in TypeScript?
    **Answer:**
    Type guards are used to narrow down the type of a variable within a conditional block. They can be implemented using `typeof`, `instanceof`, or custom type predicates:

```typescript
function isString(value: any): value is string {
  return typeof value === "string";
}

function printLength(value: string | number) {
  if (isString(value)) {
    console.log(value.length);
  } else {
    console.log("Not a string");
  }
}
```

## 13. What is `type inference` in TypeScript?

**Answer:**
Type inference is the process by which TypeScript automatically infers the type of a variable or expression when it is not explicitly specified. For example:

```typescript
let message = "Hello World"; // TypeScript infers `message` as `string`
```

## 14. What are `enums` in TypeScript, and how are they used?

**Answer:**
Enums are a way to define a set of named constants. They can be numeric or string-based. Enums help in giving meaningful names to sets of values:

```typescript
enum Color {
  Red = 1,
  Green,
  Blue,
}

let color: Color = Color.Green;
```

## 15. How does TypeScript handle `modules` and `namespaces`?

**Answer:**
TypeScript supports both `modules` and `namespaces` for organizing code. `Modules` use ES6 `import/export` syntax, while `namespaces` use TypeScript's own syntax.

- Modules:

```typescript
// math.ts
export function add(a: number, b: number): number {
  return a + b;
}

// app.ts
import { add } from "./math";
console.log(add(2, 3));
```

- Namespaces:

```typescript
namespace Geometry {
  export function areaOfCircle(radius: number): number {
    return Math.PI * radius * radius;
  }
}

console.log(Geometry.areaOfCircle(5));
```

## 16. How do you handle asynchronous operations in TypeScript?

**Answer:**
Asynchronous operations in TypeScript are handled using `Promise` and `async/await` syntax, similar to JavaScript:

```typescript
async function fetchData(): Promise<string> {
  return "Data fetched";
}

fetchData().then((data) => console.log(data));

async function fetchDataAsync() {
  let data = await fetchData();
  console.log(data);
}
```

## 17. What is `decorator` in TypeScript, and how is it used?

**Answer:**
Decorators are a special kind of declaration that can be attached to a class, method, accessor, property, or parameter. They are used to modify or annotate classes and their members.

To use decorators, you must enable the `experimentalDecorators` option in the `tsconfig.json` file.

Example of a class decorator:

```typescript
function Component(target: Function) {
  console.log(`Component decorator applied to: ${target.name}`);
}

@Component
class MyComponent {
  // class definition
}
```

## 18. How can you create a type alias for a function type in TypeScript?

**Answer:**
You can create a type alias for a function `type` using the type keyword:

```typescript
type GreetFunction = (name: string) => void;

const greet: GreetFunction = (name) => {
  console.log(`Hello, ${name}`);
};
```

## 19. What is `type narrowing`, and how does it work?

**Answer:**
Type narrowing is the process of refining the type of a variable based on certain conditions. TypeScript uses control flow analysis to narrow down types within conditional blocks:

```typescript
function processValue(value: string | number) {
  if (typeof value === "string") {
    console.log(value.toUpperCase());
  } else {
    console.log(value.toFixed(2));
  }
}
```

## 20. Explain the use of `partial` and `readonly` utility types in TypeScript.

**Answer:**

- **`Partial<T>`:** Constructs a type with all properties of `T` set to optional.
- **`Readonly<T>`:** Constructs a type with all properties of `T` set to read-only.
  Examples:

```typescript
interface User {
  name: string;
  age: number;
}

const user1: Partial<User> = { name: "Alice" }; // age is optional

const user2: Readonly<User> = { name: "Bob", age: 30 };
// user2.age = 31; // Error: Cannot assign to 'age' because it is a read-only property.
```

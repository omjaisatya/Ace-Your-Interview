### 1. What’s the difference between `var`, `let`, and `const`?

- **`var`**: It’s either function-scoped or globally scoped. You can redeclare and update it, but it can behave unexpectedly because of how it's scoped.
- **`let`**: Block-scoped (meaning it only exists within `{ }` braces). You can update it, but you can’t redeclare it in the same scope.
- **`const`**: Also block-scoped, but you **can’t** change or redeclare it after assigning a value. It must be initialized when declared.

---

### 2. What is hoisting in JavaScript?

Hoisting is JavaScript’s way of “moving” variable and function declarations to the top of their scope behind the scenes. So, you can reference a function or variable _before_ it appears in your code—but only the declaration is hoisted, not the value.

```javascript
console.log(x); // undefined
var x = 5;
```

In this case, `x` is hoisted, but its value isn't.

---

### 3. What’s a closure?

A closure is when a function remembers and continues to access variables from its outer (lexical) scope—even after the outer function has finished running.

```javascript
function outerFunction() {
  let outerVariable = "I am from outer function";

  function innerFunction() {
    console.log(outerVariable);
  }

  return innerFunction;
}

const inner = outerFunction();
inner(); // Outputs: 'I am from outer function'
```

Closures are powerful for things like data privacy and function factories.

---

### 4. What's the difference between `==` and `===`?

- **`==`** (loose equality): Compares values after _type conversion_. So, `5 == "5"` is `true`.
- **`===`** (strict equality): Compares values _and_ types, so no type conversion. `5 === "5"` is `false`.

```javascript
console.log(5 == "5"); // true
console.log(5 === "5"); // false
```

---

### 5. What does `this` mean in JavaScript?

`this` refers to the context in which a function is executed—it changes depending on how the function is called:

- In a method: `this` is the object that owns the method.
- In a constructor: `this` is the new object being created.
- In a regular function: `this` is the global object (or `undefined` in strict mode).
- In an arrow function: `this` is inherited from the surrounding scope.

---

### 6. What are Promises?

Promises are a cleaner way to deal with asynchronous operations (like fetching data). They represent a value that may be available now, later, or never.

```javascript
let promise = new Promise((resolve, reject) => {
  let success = true;
  if (success) {
    resolve("Operation was successful");
  } else {
    reject("Operation failed");
  }
});

promise
  .then((result) => console.log(result))
  .catch((error) => console.log(error));
```

---

### 7. What’s event delegation?

Instead of attaching event listeners to lots of child elements, you attach one to a common parent and catch events as they bubble up. It’s great for performance, especially with dynamic content.

```javascript
document.getElementById("parent").addEventListener("click", function (event) {
  if (event.target && event.target.matches("button.child")) {
    console.log("Button clicked!");
  }
});
```

---

### 8. What is prototypal inheritance?

In JavaScript, objects can inherit from other objects. If a property or method isn’t found on the object itself, JavaScript will look for it in its prototype.

```javascript
let animal = {
  speak() {
    console.log("Animal sound");
  },
};

let dog = Object.create(animal);
dog.speak(); // Output: 'Animal sound'
```

It’s the core of how JavaScript inheritance works.

---

### 9. What do `async` and `await` do?

They make working with Promises easier and your async code look more like regular, synchronous code.

```javascript
async function fetchData() {
  let response = await fetch("https://api.example.com/data");
  let data = await response.json();
  console.log(data);
}
```

Just add `async` before a function and use `await` to pause until the Promise resolves.

---

### 10. What's the difference between `null` and `undefined`?

- **`null`**: You _assign_ this to a variable when you want to say, “this has no value.”
- **`undefined`**: This is what JavaScript gives a variable if you declared it but didn’t assign a value.

```javascript
let a = null;
let b;
console.log(a); // null
console.log(b); // undefined
```

---

### 11. What's the difference between a function declaration and a function expression?

- **Function declarations** are hoisted, which means you can call them _before_ they're defined in the code.

  ```javascript
  function greet() {
    console.log("Hello");
  }
  ```

- **Function expressions** are not hoisted. You assign the function to a variable, and you can’t use it until that line runs.
  ```javascript
  const greet = function () {
    console.log("Hello");
  };
  ```

---

### 12. What does the `bind` method do?

`bind` creates a **new function** with `this` set to whatever object you pass in. You can also pre-fill arguments.

```javascript
function greet(name) {
  console.log(`Hello, ${name}`);
}

const greetJohn = greet.bind(null, "John");
greetJohn(); // Output: 'Hello, John'
```

---

### 13. What are arrow functions, and how are they different?

Arrow functions are a shorter way to write functions and behave a bit differently:

- They don’t have their own `this`, `arguments`, or `super`.
- Can’t be used as constructors (no `new`).
- No `prototype` property.

```javascript
// Regular function
function add(a, b) {
  return a + b;
}

// Arrow function
const add = (a, b) => a + b;
```

---

### 14. What’s the `apply` method?

`apply` lets you call a function with a specific `this` value and arguments passed as an array.

```javascript
function sum(a, b) {
  return a + b;
}

console.log(sum.apply(null, [1, 2])); // Output: 3
```

Very similar to `call`, but it takes an array instead of individual arguments.

---

### 15. What is event bubbling?

Event bubbling is how events move up the DOM tree. When you click a child element, the event “bubbles up” to its parent and continues upward.

```javascript
document.getElementById("parent").addEventListener("click", () => {
  console.log("Parent clicked");
});

document.getElementById("child").addEventListener("click", () => {
  console.log("Child clicked");
});
```

Clicking on the child will trigger both messages.

---

### 16. What’s the difference between `setTimeout` and `setInterval`?

- **`setTimeout`** runs code **once** after a delay.
- **`setInterval`** runs code **repeatedly** at regular intervals.

```javascript
setTimeout(() => console.log("Runs once after 1 second"), 1000);
setInterval(() => console.log("Runs every second"), 1000);
```

---

### 17. What is a `debounce` function?

Debounce is a way to control how often a function runs. It makes sure the function only runs **after** a certain amount of time has passed _since the last call_. Great for things like typing or window resizing.

```javascript
function debounce(fn, delay) {
  let timeout;
  return function (...args) {
    clearTimeout(timeout);
    timeout = setTimeout(() => fn.apply(this, args), delay);
  };
}

const debouncedFn = debounce(() => console.log("Debounced!"), 300);
window.addEventListener("resize", debouncedFn);
```

---

### 18. What are template literals?

Template literals let you use backticks (`` ` ``) to make strings that support:

- Multi-line formatting
- Easy variable interpolation using `${}`

```javascript
let name = "Alice";
let greeting = `Hello, ${name}!`;
console.log(greeting); // Output: 'Hello, Alice!'
```

---

### 19. What’s the difference between `call` and `apply`?

Both are used to call a function with a specific `this` value. The only difference is how you pass arguments:

- **`call`**: Pass arguments one by one.
- **`apply`**: Pass arguments as an array.

```javascript
function show(a, b) {
  console.log(a, b);
}

show.call(null, 1, 2); // Output: 1 2
show.apply(null, [1, 2]); // Output: 1 2
```

---

### 20. What does `Object.assign()` do?

It copies properties from one or more objects into a target object. This is useful for merging or cloning objects.

```javascript
const target = { a: 1 };
const source = { b: 2 };

Object.assign(target, source);
console.log(target); // Output: { a: 1, b: 2 }
```

---

### 21. What’s the difference between synchronous and asynchronous code?

- **Synchronous code** runs one line at a time, in order. Each line waits for the one before it to finish.
- **Asynchronous code** lets certain tasks (like network requests or timers) run in the background, so your code doesn’t have to wait for them.

Example:

```javascript
console.log("Start");

setTimeout(() => {
  console.log("Timeout");
}, 1000);

console.log("End");
```

**Output:**

```
Start
End
Timeout
```

Even though the timeout is written second, it runs _after_ the rest of the code finishes. That’s async in action!

---

### 22. What does `Promise.all` do?

`Promise.all` takes multiple promises and runs them at the same time. It waits for **all** of them to finish, then gives you the results. If even one fails, it throws an error.

```javascript
let p1 = Promise.resolve(3);
let p2 = 42; // treated like a resolved promise
let p3 = new Promise((resolve) => setTimeout(resolve, 100, "foo"));

Promise.all([p1, p2, p3]).then((values) => {
  console.log(values); // [3, 42, 'foo']
});
```

---

### 23. What is `this` in JavaScript?

`this` refers to the object that's currently running the function. Its meaning depends on **how** the function is called:

- In the **global scope**: `this` refers to the global object (`window` in browsers).
- In a **method**: it refers to the object the method belongs to.
- In a **constructor**: it refers to the new object being created.
- In an **event handler**: it refers to the element that triggered the event.
- In **arrow functions**: it doesn't have its own `this`; it inherits it from the parent scope.

Example:

```javascript
function show() {
  console.log(this);
}

const obj = {
  show: show,
};

obj.show(); // Logs 'obj'
```

---

### 24. What’s a generator function?

Generators are functions that you can pause and resume. They use the `function*` syntax and `yield` keyword.

```javascript
function* myGenerator() {
  yield 1;
  yield 2;
  yield 3;
}

const gen = myGenerator();

console.log(gen.next().value); // 1
console.log(gen.next().value); // 2
console.log(gen.next().value); // 3
```

Perfect for tasks like iterating over a sequence of values.

---

### 25. What does `Object.freeze` do?

It makes an object **immutable**. Once frozen, you can't add, remove, or change its properties.

```javascript
const obj = { name: "Alice" };

Object.freeze(obj);

obj.name = "Bob"; // Has no effect
console.log(obj.name); // Still 'Alice'
```

---

### 26. What’s the event loop?

The event loop is how JavaScript handles async stuff without blocking your code.

- **Call stack**: Holds the functions that are being run.
- **Task queue**: Holds things like callbacks and `setTimeout` functions.
- **Microtask queue**: For promises and other high-priority tasks.

When the call stack is empty, the event loop checks these queues and pushes tasks into the stack one at a time.

---

### 27. What’s the difference between `slice()` and `splice()`?

- **`slice(start, end)`**: Returns part of the array without changing the original.

  ```javascript
  const arr = [1, 2, 3, 4];
  const result = arr.slice(1, 3); // [2, 3]
  ```

- **`splice(start, deleteCount, ...items)`**: Changes the array by removing/replacing/adding elements.
  ```javascript
  const arr = [1, 2, 3, 4];
  arr.splice(1, 2, "a", "b"); // arr is now [1, 'a', 'b', 4]
  ```

---

### 28. How do `Object.keys()`, `Object.values()`, and `Object.entries()` work?

They help you work with objects:

- **`Object.keys(obj)`** → array of property names
- **`Object.values(obj)`** → array of values
- **`Object.entries(obj)`** → array of key-value pairs

```javascript
const obj = { a: 1, b: 2 };

console.log(Object.keys(obj)); // ['a', 'b']
console.log(Object.values(obj)); // [1, 2]
console.log(Object.entries(obj)); // [['a', 1], ['b', 2]]
```

---

### 29. How does JavaScript handle type coercion?

JavaScript automatically converts types when needed (called _type coercion_), which can lead to surprises.

```javascript
console.log("5" + 1); // '51' → string + number becomes a string
console.log("5" - 1); // 4   → string is converted to number
console.log(true + 1); // 2   → true becomes 1
```

---

### 30. What’s the difference between `==` and `===`?

- **`==`** (loose equality): compares values _after_ converting types.
- **`===`** (strict equality): compares value _and_ type.

```javascript
console.log(5 == "5"); // true  → values match after coercion
console.log(5 === "5"); // false → different types
```

Use `===` most of the time to avoid unexpected behavior.

---

### 31. How can you create objects in JavaScript?

There are a few different ways to create objects:

1. **Object Literals** – The simplest and most common way:

   ```javascript
   const obj = {
     name: "Alice",
     age: 25,
   };
   ```

2. **Constructor Functions** – Create a function and use `new` to make new instances:

   ```javascript
   function Person(name, age) {
     this.name = name;
     this.age = age;
   }

   const alice = new Person("Alice", 25);
   ```

3. **`Object.create()`** – Creates a new object using an existing object as its prototype:

   ```javascript
   const proto = {
     greet() {
       console.log("Hello");
     },
   };

   const obj = Object.create(proto);
   obj.greet(); // Hello
   ```

4. **ES6 Classes** – A cleaner, more modern way:

   ```javascript
   class Person {
     constructor(name, age) {
       this.name = name;
       this.age = age;
     }
   }

   const alice = new Person("Alice", 25);
   ```

---

### 32. How does `reduce()` work in JavaScript?

The `reduce()` method runs a function on every item in an array, building up a single result.

```javascript
const numbers = [1, 2, 3, 4];

const sum = numbers.reduce((acc, curr) => acc + curr, 0);

console.log(sum); // 10
```

Here, it adds each number to an accumulator, ending up with the total sum.

---

### 33. What's the difference between `undefined` and `not defined`?

- **`undefined`** means the variable exists but hasn't been given a value yet.

  ```javascript
  let a;
  console.log(a); // undefined
  ```

- **`not defined`** means the variable was never declared at all.
  ```javascript
  console.log(b); // ReferenceError: b is not defined
  ```

---

### 34. What are the ways to loop through arrays?

Here are some common ones:

1. **Traditional `for` loop**:

   ```javascript
   for (let i = 0; i < arr.length; i++) {
     console.log(arr[i]);
   }
   ```

2. **`forEach()`** – Runs a function on each item:

   ```javascript
   arr.forEach((item) => console.log(item));
   ```

3. **`map()`** – Transforms each item and returns a new array:

   ```javascript
   const doubled = arr.map((x) => x * 2);
   ```

4. **`filter()`** – Filters items that match a condition:

   ```javascript
   const evens = arr.filter((x) => x % 2 === 0);
   ```

5. **`for...of`** – A modern loop for iterables:
   ```javascript
   for (const item of arr) {
     console.log(item);
   }
   ```

---

### 35. What's the `Symbol` type used for?

A `Symbol` is a unique and immutable value, often used to create hidden or non-colliding object property keys.

```javascript
const sym = Symbol("id");
const obj = {
  [sym]: "secret",
};

console.log(obj[sym]); // 'secret'
```

Each symbol is completely unique, even if they have the same description.

---

### 36. What are template literals?

Template literals use backticks (`` ` ``) instead of quotes and let you:

- **Insert variables directly** using `${}`:

  ```javascript
  const name = "Alice";
  const greeting = `Hello, ${name}!`;
  ```

- **Write multi-line strings** easily:
  ```javascript
  const message = `This is
  a multi-line
  string.`;
  ```

---

### 37. What’s the difference between `call()` and `apply()`?

Both are used to call functions with a specific `this` value, but the way you pass arguments differs:

- **`call()`** – Pass arguments one by one:

  ```javascript
  greet.call(null, "Hi", "Alice");
  ```

- **`apply()`** – Pass arguments as an array:
  ```javascript
  greet.apply(null, ["Hi", "Alice"]);
  ```

---

### 38. What does the `new` keyword do?

`new` creates a new object using a constructor function or class:

1. It creates an empty object.
2. Sets the prototype.
3. Binds `this` inside the constructor.
4. Returns the object.

```javascript
function Person(name) {
  this.name = name;
}

const alice = new Person("Alice");
console.log(alice.name); // Alice
```

---

### 39. What’s the difference between `let` and `const`?

- **`let`** allows reassignment:

  ```javascript
  let x = 5;
  x = 10; // ok
  ```

- **`const`** means no reassignment. But the contents of objects/arrays can still change:

  ```javascript
  const obj = { a: 1 };
  obj.a = 2; // this is allowed

  obj = {}; // ❌ not allowed
  ```

---

### 40. How does `Object.assign()` work?

It copies properties from one or more source objects into a target object.

```javascript
const target = { a: 1 };
const source = { b: 2 };

Object.assign(target, source);
console.log(target); // { a: 1, b: 2 }
```

This is great for merging objects or making shallow copies.

---

## 41. What are the different data types in JavaScript?

JavaScript has two main types of data: **primitive** and **non-primitive**.

### 🔹 Primitive types:

These are the basic building blocks:

- **String** – text like `"hello"`.
- **Number** – both integers and decimals (e.g. `42`, `3.14`).
- **BigInt** – for really big numbers beyond the safe limit for regular numbers.
- **Boolean** – just `true` or `false`.
- **Undefined** – a variable that’s been declared but hasn’t been given a value.
- **Null** – represents “no value” intentionally.
- **Symbol** – unique values, often used as keys in objects.

### 🔸 Non-primitive:

- **Object** – includes arrays, functions, or any key-value pairs.

```javascript
let name = "Alice"; // String
let age = 30; // Number
let bigNum = 123n; // BigInt
let isCool = true; // Boolean
let notSet; // Undefined
let nothing = null; // Null
let sym = Symbol("id"); // Symbol
let person = { name: "Bob" }; // Object
```

---

## 42. What is a Promise in JavaScript?

A **Promise** is a way to handle something that will finish later — like getting data from an API.

### It has three states:

- **Pending** – still waiting for a result.
- **Fulfilled** – completed successfully.
- **Rejected** – something went wrong.

Example:

```javascript
const promise = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Success!"), 1000);
});

promise
  .then((result) => console.log(result)) // Outputs: Success!
  .catch((error) => console.error(error));
```

---

## 43. What is event delegation?

**Event delegation** is a technique where you add a single event listener to a parent element instead of multiple listeners to each child. This works because events "bubble" up through the DOM.

### Why use it?

- You use fewer event listeners (better performance).
- It works even for elements added to the page later.

```javascript
document.getElementById("list").addEventListener("click", (event) => {
  if (event.target.tagName === "LI") {
    console.log("Item clicked:", event.target.textContent);
  }
});
```

---

## 44. How does JavaScript deal with asynchronous code?

JavaScript runs one thing at a time, but it can _handle_ async actions using:

### Callbacks:

```javascript
setTimeout(() => {
  console.log("Done!");
}, 1000);
```

### Promises:

```javascript
new Promise((resolve) => {
  setTimeout(() => resolve("All done"), 1000);
}).then(console.log);
```

### Async/Await:

Makes async code look cleaner and easier to read.

```javascript
async function loadData() {
  let result = await new Promise((resolve) =>
    setTimeout(() => resolve("Data loaded"), 1000)
  );
  console.log(result);
}
loadData();
```

---

## 45. What are higher-order functions?

A **higher-order function** is just a fancy name for a function that:

- Takes another function as an argument
- Or returns another function

### Example 1 – takes a function:

```javascript
function doSomething(arr, action) {
  return arr.map(action);
}
console.log(doSomething([1, 2], (x) => x * 2)); // [2, 4]
```

### Example 2 – returns a function:

```javascript
function greeter(prefix) {
  return function (name) {
    return `${prefix} ${name}`;
  };
}

const sayHi = greeter("Hi");
console.log(sayHi("Alice")); // Hi Alice
```

---

## 46. What does `this` mean in JavaScript?

The `this` keyword refers to **who's calling the function** — the execution context.

- **In the global scope**: `this` is the global object (`window` in browsers).
- **Inside an object method**: `this` refers to the object.
- **In a constructor**: `this` is the new object created.
- **In event handlers**: `this` is the element that fired the event.
- **Arrow functions**: `this` is inherited from the parent scope (it doesn't bind its own).

### Examples:

```javascript
console.log(this); // window (in browsers)

const obj = {
  name: "Alice",
  sayHi() {
    console.log(this.name); // "Alice"
  },
};

obj.sayHi();

document.getElementById("btn").addEventListener("click", function () {
  console.log(this); // refers to the button
});
```

---

## 47. What are `async` and `await`?

- `**async**` marks a function as asynchronous. It always returns a Promise.
- `**await**` pauses the function until a Promise is resolved (only works inside async functions).

### Example:

```javascript
async function getData() {
  let data = await new Promise((resolve) =>
    setTimeout(() => resolve("Fetched!"), 1000)
  );
  console.log(data); // Fetched!
}
getData();
```

---

## 48. How does prototypal inheritance work?

In JavaScript, objects can inherit from other objects using a **prototype**. This lets them share methods and properties.

```javascript
const animal = {
  speak() {
    console.log("I make a noise");
  },
};

const dog = Object.create(animal);
dog.bark = function () {
  console.log("Woof!");
};

dog.speak(); // I make a noise
dog.bark(); // Woof!
```

---

## 49. What does `Object.freeze()` do?

`Object.freeze()` locks an object so that no changes can be made:

- No new properties
- No deletion
- No editing of values

```javascript
const person = { name: "Alice" };
Object.freeze(person);

person.name = "Bob"; // Won't work
console.log(person.name); // Alice
```

---

## 50. What's the difference between `==` and `===`?

- `==` checks for **loose equality** (does type conversion).

  ```javascript
  5 == "5"; // true
  ```

- `===` checks for **strict equality** (no type conversion).
  ```javascript
  5 === "5"; // false
  ```

---

## 51. **What’s a closure in JavaScript?**

A **closure** happens when a function remembers and accesses variables from its outer scope—even after that outer function has finished running.

**Example:**

```javascript
function outerFunction(outerVariable) {
  return function innerFunction(innerVariable) {
    console.log(`Outer: ${outerVariable}, Inner: ${innerVariable}`);
  };
}

const closureFunction = outerFunction("outer");
closureFunction("inner"); // Output: Outer: outer, Inner: inner
```

Here, `innerFunction` still has access to `outerVariable` even though `outerFunction` has already run. That’s closure in action!

---

## 52. **What are event bubbling and capturing?**

When you click an element, the event doesn't just stay there—it travels through the DOM in two phases:

- **Event Bubbling** (default): The event starts at the target element and "bubbles" up to its ancestors.
- **Event Capturing**: The event starts at the top (document root) and moves _down_ to the target.

**Bubbling Example:**

```javascript
document.getElementById("child").addEventListener("click", () => {
  console.log("Child clicked");
});

document.getElementById("parent").addEventListener("click", () => {
  console.log("Parent clicked");
});
```

Clicking the child logs:  
`Child clicked`  
`Parent clicked`

**Capturing Example:**

```javascript
document.getElementById("parent").addEventListener(
  "click",
  () => {
    console.log("Parent clicked");
  },
  true // Enables capturing
);

document.getElementById("child").addEventListener("click", () => {
  console.log("Child clicked");
});
```

Clicking the child logs:  
`Parent clicked`  
`Child clicked`

---

## 53. **What does `bind()` do in JavaScript?**

`bind()` lets you set the value of `this` inside a function and optionally preset some arguments.

**Example:**

```javascript
function greet(greeting, name) {
  console.log(`${greeting}, ${name}`);
}

const greetHello = greet.bind(null, "Hello");
greetHello("Alice"); // Hello, Alice
```

---

## 54. **What is `Array.prototype.flat()`?**

`flat()` is a handy method that flattens nested arrays into a single-level array—up to a certain depth.

**Example:**

```javascript
const arr = [1, [2, [3, [4]]]];
const flattened = arr.flat(2);
console.log(flattened); // [1, 2, 3, [4]]
```

---

## 55. **What’s the difference between `null` and `undefined`?**

- `**null**`: You _intentionally_ set a variable to “nothing.”
- `**undefined**`: The variable exists but hasn’t been given a value.

```javascript
let a = null; // You set this to "nothing"
let b; // No value assigned

console.log(a); // null
console.log(b); // undefined
```

---

## 56. **How does JavaScript handle type conversion?**

JS is flexible—it’ll often convert types automatically, or you can do it yourself.

- **Implicit conversion** (JS does it for you):

```javascript
console.log("5" + 1); // "51"
console.log("5" - 1); // 4
```

- **Explicit conversion** (you do it manually):

```javascript
console.log(Number("5")); // 5
console.log(String(5)); // "5"
```

---

## 57. **What’s the difference between `setTimeout` and `setInterval`?**

- `**setTimeout**`: Runs a function _once_ after a delay.

```javascript
setTimeout(() => {
  console.log("Runs after 1 second");
}, 1000);
```

- `**setInterval**`: Keeps running the function every X milliseconds.

```javascript
const id = setInterval(() => {
  console.log("Runs every second");
}, 1000);

// To stop it:
clearInterval(id);
```

---

## 58. **What is the spread operator (`...`) and how is it used?**

The spread operator expands arrays or objects into individual elements or properties.

**Examples:**

- **Function calls:**

```javascript
const numbers = [1, 2, 3];
console.log(Math.max(...numbers)); // 3
```

- **Arrays:**

```javascript
const arr1 = [1, 2];
const arr2 = [3, 4];
const combined = [...arr1, ...arr2]; // [1, 2, 3, 4]
```

- **Objects:**

```javascript
const obj1 = { a: 1 };
const obj2 = { b: 2 };
const merged = { ...obj1, ...obj2 }; // { a: 1, b: 2 }
```

---

## 59. **What does the `typeof` operator do?**

`typeof` tells you the data type of a value.

**Examples:**

```javascript
typeof "Hello"; // "string"
typeof 42; // "number"
typeof true; // "boolean"
typeof undefined; // "undefined"
typeof Symbol(); // "symbol"
typeof {}; // "object"
typeof function () {}; // "function"
```

---

## 60. **How do you create a new instance of a class in JavaScript?**

Use the `new` keyword with the class name and pass any required arguments.

**Example:**

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hi, I'm ${this.name}`);
  }
}

const alice = new Person("Alice", 25);
alice.greet(); // Hi, I'm Alice
```

---

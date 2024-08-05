# JavaScript Interview Questions and Answers

## 1. What is the difference between `var`, `let`, and `const`?

**Answer:**

- `var`: Function-scoped or globally-scoped. Can be redeclared and updated.
- `let`: Block-scoped. Can be updated but not redeclared within the same scope.
- `const`: Block-scoped. Cannot be updated or redeclared. Must be initialized during declaration.

## 2. Explain the concept of hoisting in JavaScript.

**Answer:**
Hoisting is JavaScript's behavior of moving variable and function declarations to the top of their containing scope during the compile phase. This means you can use variables and functions before they are declared in the code. However, only declarations are hoisted, not initializations.

```javascript
console.log(x); // undefined
var x = 5;
```

## 3. What is a closure in JavaScript?

**Answer:**
A closure is a function that retains access to its lexical scope, even when the function is executed outside that scope. This means that a function defined within another function can access the outer function’s variables.

```javascript
function outerFunction() {
  let outerVariable = "I am from outer function";

  function innerFunction() {
    console.log(outerVariable);
  }

  return innerFunction;
}

const inner = outerFunction();
inner(); // Output: 'I am from outer function'
```

## 4. Explain the difference between `==` and `===` in JavaScript.

**Answer:**

- `==` (Equality Operator): Compares two values for equality after converting both values to a common type (type coercion).
- `===` (Strict Equality Operator): Compares both value and type for equality without type coercion.

```javascript
console.log(5 == "5"); // true
console.log(5 === "5"); // false
```

## 5. What is the purpose of the `this` keyword in JavaScript?

**Answer:**
The `this` keyword refers to the context in which a function is called. It can point to different objects depending on how the function is invoked:

- In a method of an object, `this` refers to the object itself.
- In a constructor function, `this` refers to the newly created instance.
- In a regular function, `this` refers to the global object (or undefined in strict mode).
- In an arrow function, `this` is lexically inherited from the outer function.

## 6. What are Promises in JavaScript?

**Answer:**
Promises are objects that represent the eventual completion (or failure) of an asynchronous operation and its resulting value. They provide a way to handle asynchronous operations more gracefully compared to traditional callback methods.

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
  .then((result) => {
    console.log(result);
  })
  .catch((error) => {
    console.log(error);
  });
```

## 7. What is event delegation?

**Answer:**
Event delegation is a technique where a single event listener is added to a parent element instead of adding listeners to multiple child elements. This leverages event bubbling to handle events at a higher level in the DOM tree.

```javascript
document.getElementById("parent").addEventListener("click", function (event) {
  if (event.target && event.target.matches("button.child")) {
    console.log("Button clicked!");
  }
});
```

## 8. Explain the concept of prototypal inheritance in JavaScript.

**Answer:**
Prototypal inheritance is a feature in JavaScript where objects can inherit properties and methods from other objects. This is achieved via the prototype chain. Every JavaScript object has an internal prototype reference, and if a property or method is not found on the object itself, the JavaScript engine looks up the prototype chain.

```javascript
let animal = {
  speak() {
    console.log("Animal sound");
  },
};

let dog = Object.create(animal);
dog.speak(); // Output: 'Animal sound'
```

## 9. What is the purpose of `async` and `await` in JavaScript?

**Answer:**
`async` and `await` are used to work with Promises in a more synchronous fashion, making asynchronous code easier to read and write. The `async` keyword is used to define a function that returns a Promise, and `await` is used to pause the execution of the `async` function until the Promise is resolved.

```javascript
async function fetchData() {
  let response = await fetch("https://api.example.com/data");
  let data = await response.json();
  console.log(data);
}
```

## 10. What is the difference between `null` and `undefined`?

**Answer:**

- `null`: A value explicitly assigned to a variable to indicate the absence of any object value. It is a type itself.
- `undefined`: A value automatically assigned to a variable that has been declared but not yet initialized. It is a type itself.

```javascript
let a = null;
let b;
console.log(a); // null
console.log(b); // undefined
```

## 11. What is the difference between `function` declarations and `function` expressions?

**Answer:**

- **Function Declarations**: Hoisted to the top of their scope, so they can be called before their definition. They are also called function statements.
  ```javascript
  function greet() {
    console.log("Hello");
  }
  ```
- **Function Expressions**: Not hoisted. They are defined and assigned to a variable. They can be named or anonymous.

```javascript
const greet = function () {
  console.log("Hello");
};
```

## 12. What is the bind method in JavaScript?

Answer:
The `bind` method creates a new function that, when called, has its `this` keyword set to the provided value, with a given sequence of arguments preceding any provided when the new function is called.

```javascript
function greet(name) {
  console.log(`Hello, ${name}`);
}

const greetJohn = greet.bind(null, "John");
greetJohn(); // Output: 'Hello, John'
```

## 13. What are arrow functions and how do they differ from regular functions?

**Answer:**
Arrow functions provide a concise syntax for writing functions. They differ from regular functions in several ways:

- They do not have their own `this`, `arguments`, or `super` keyword.
- They cannot be used as constructors.
- They do not have a `prototype` property.

```javascript
// Regular function
function add(a, b) {
  return a + b;
}

// Arrow function
const add = (a, b) => a + b;
```

## 14. What is the `apply` method in JavaScript?

**Answer:**
The `apply` method calls a function with a given `this` value and arguments provided as an array (or an array-like object). It is similar to `call`, but `apply` takes arguments as an array.

```javascript
function sum(a, b) {
  return a + b;
}

console.log(sum.apply(null, [1, 2])); // Output: 3
```

## 15. Explain the concept of event bubbling in JavaScript.

**Answer:**
Event bubbling is a type of event propagation in the DOM where the event starts from the target element and bubbles up to the root of the DOM tree. This means that events on child elements will propagate up to parent elements.

```javascript
document.getElementById("parent").addEventListener("click", () => {
  console.log("Parent clicked");
});

document.getElementById("child").addEventListener("click", () => {
  console.log("Child clicked");
});
```

## 16. What are `setTimeout` and `setInterval`? How do they differ?

**Answer:**

- **`setTimeout`(callback, delay)**: Executes the `callback` function once after a specified delay (in milliseconds).
- **`setInterval`(callback, interval)**: Executes the callback function repeatedly at specified intervals (in milliseconds) until `clearInterval` is called.

```javascript
setTimeout(() => console.log("Executed once"), 1000);
setInterval(() => console.log("Executed repeatedly"), 1000);
```

## 17. What is the `debounce` function and why is it used?

**Answer:**
The `debounce` function is used to limit the rate at which a function is executed. It ensures that a function is not called continuously but rather only after a specified period of inactivity. It is useful for performance optimization in scenarios like handling user input or resizing events.

```javascript
function debounce(fn, delay) {
  let timeout;
  return function (...args) {
    clearTimeout(timeout);
    timeout = setTimeout(() => fn.apply(this, args), delay);
  };
}

const debouncedFunction = debounce(() => console.log("Debounced!"), 300);
window.addEventListener("resize", debouncedFunction);
```

## 18. What are JavaScript templates literals?

Answer:
Template literals are a way to include expressions within strings using backticks (``). They allow for multi-line strings and interpolation of variables and expressions using ${}.

```javascript
let name = "Alice";
let greeting = `Hello, ${name}!`;
console.log(greeting); // Output: 'Hello, Alice!'
```

## 19. What is the difference between `call` and `apply` methods in JavaScript?

**Answer:**
Both `call` and `apply` methods are used to invoke a function with a specific `this` value. The main difference is how arguments are passed:

- **`call(thisArg, arg1, arg2, ...)`**: Arguments are passed individually.
- **`apply(thisArg, [arg1, arg2, ...])`**: Arguments are passed as an array.

```javascript
function show(a, b) {
  console.log(a, b);
}

show.call(null, 1, 2); // Output: 1 2
show.apply(null, [1, 2]); // Output: 1 2
```

## 20. What is the purpose of the `Object.assign()` method?

**Answer:**
The `Object.assign()` method copies the values of all enumerable own properties from one or more source objects to a target object. It returns the target object. It is often used for object cloning or merging objects.

```javascript
const target = { a: 1 };
const source = { b: 2 };

Object.assign(target, source);
console.log(target); // Output: { a: 1, b: 2 }
```

## 21. What is the difference between synchronous and asynchronous code in JavaScript?

**Answer:**

- **Synchronous Code**: Executes line-by-line in the order it's written. Each operation must complete before the next one starts.
- **Asynchronous Code**: Executes operations independently of the main program flow. It allows tasks like network requests or timers to run in the background, with the program continuing to execute other code in the meantime. It is often handled using callbacks, Promises, or async/await.

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

## 22. What is the `Promise.all` method and how does it work?

**Answer:**
`Promise.all` is a method that takes an iterable of Promises and, when all of the Promises have resolved, returns a single Promise that resolves with an array of the resolved values. If any of the Promises reject, `Promise.all` immediately rejects with the reason of the first rejected Promise.

```javascript
let p1 = Promise.resolve(3);
let p2 = 42;
let p3 = new Promise((resolve, reject) => setTimeout(resolve, 100, "foo"));

Promise.all([p1, p2, p3]).then((values) => {
  console.log(values); // [3, 42, 'foo']
});
```

## 23. What is the `this` keyword in JavaScript, and how does it behave in different contexts?

**Answer:**
The `this` keyword refers to the object that is executing the current function. Its value depends on how the function is called:

- **Global Context**: Refers to the global object (`window` in browsers, `global` in Node.js).
- **Object Method**: Refers to the object that owns the method.
- **Constructor Function**: Refers to the newly created object.
- **Event Handler**: Refers to the element that triggered the event.
- **Arrow Functions**: Do not have their own `this`; they inherit `this` from their lexical scope.

```javascript
function show() {
  console.log(this);
}

const obj = {
  show: show,
};

obj.show(); // 'this' refers to 'obj'
```

## 24. What is a JavaScript generator function?

**Answer:**
A generator function is a special type of function that can be paused and resumed. It uses the `function*` syntax and returns an iterator object that can be used to control the execution of the function.

```javascript
function* myGenerator() {
  yield 1;
  yield 2;
  yield 3;
}

const generator = myGenerator();

console.log(generator.next().value); // 1
console.log(generator.next().value); // 2
console.log(generator.next().value); // 3
```

## 25. What is the `Object.freeze` method and how is it used?

**Answer:**
`Object.freeze` is a method that prevents modifications to an object. It makes the object immutable by disallowing changes to its properties and their values, as well as preventing the addition or deletion of properties.

```javascript
const obj = {
  name: "Alice",
};

Object.freeze(obj);

obj.name = "Bob"; // This will not work
console.log(obj.name); // 'Alice'
```

## 26. Explain the concept of the event loop in JavaScript.

**Answer:**
The event loop is a mechanism that allows JavaScript to perform non-blocking operations. It continuously checks the call stack and the task queue. If the call stack is empty, it takes the first event from the task queue and pushes it to the call stack for execution.

- **Call Stack**: Keeps track of function execution.
- **Task Queue**: Holds tasks like callback functions or event handlers.
- **Microtask Queue**: A special queue for promises and other microtasks.

## 27. What is the difference between `slice()` and `splice()` methods in arrays?

**Answer:**

- **`slice(start, end)`**: Returns a shallow copy of a portion of an array into a new array object. It does not modify the original array.

  ```javascript
  const arr = [1, 2, 3, 4];
  const slicedArr = arr.slice(1, 3); // [2, 3]
  ```

- **`splice(start, deleteCount, item1, item2, ...)`**: Changes the contents of an array by removing or replacing existing elements and/or adding new elements. It modifies the original array.

  ```javascript
  const arr = [1, 2, 3, 4];
  arr.splice(1, 2, "a", "b"); // [1, 'a', 'b', 4]
  ```

## 28. What is the difference between `Object.keys()`, `Object.values()`, and `Object.entries()`?

**Answer:**

- **`Object.keys(obj)`**: Returns an array of the object's own enumerable property names.

  ```javascript
  const obj = { a: 1, b: 2 };
  console.log(Object.keys(obj)); // ['a', 'b']
  ```

- **`Object.values(obj)`**: Returns an array of the object's own enumerable property values.

  ```javascript
  console.log(Object.values(obj)); // [1, 2]
  ```

- **`Object.entries(obj)`**: Returns an array of the object's own enumerable property `[key, value]` pairs.

  ```javascript
  console.log(Object.entries(obj)); // [['a', 1], ['b', 2]]
  ```

## 29. How does JavaScript handle type coercion?

**Answer:**
JavaScript performs type coercion automatically when performing operations between different types. It tries to convert one type to another to complete the operation, which can sometimes lead to unexpected results.

```javascript
console.log("5" + 1); // '51' (string concatenation)
console.log("5" - 1); // 4 (string to number conversion)
console.log(true + 1); // 2 (boolean to number conversion)
```

## 30. What is the difference between `==` and `===` in JavaScript?

**Answer:**

- **`==` (Equality Operator)**: Performs type coercion and compares values for equality after converting both to the same type.

  ```javascript
  console.log(5 == "5"); // true
  ```

- **`===` (Strict Equality Operator)**: Compares values for equality without type coercion. Both value and type must be the same.

  ```javascript
  console.log(5 === "5"); // false
  ```

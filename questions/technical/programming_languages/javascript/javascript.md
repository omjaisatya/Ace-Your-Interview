# Ace Your Interview

**Ace Your Interview - JAVASCRIPT**

---

© 2024 Satya Prakash

---

**Author:**

[Satya Prakash](https://github.com/omjaisatya)

---

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

## 31. What are the different ways to create objects in JavaScript?

**Answer:**

1. **Object Literals**: Create an object using curly braces.

   ```javascript
   const obj = {
     name: "Alice",
     age: 25,
   };
   ```

2. **Constructor Functions**: Define a function and use the `new` keyword to create instances.

   ```javascript
   function Person(name, age) {
     this.name = name;
     this.age = age;
   }

   const alice = new Person("Alice", 25);
   ```

3. **Object.create()**: Create an object with a specified prototype object.

   ```javascript
   const proto = {
     greet: function () {
       console.log("Hello");
     },
   };
   const obj = Object.create(proto);
   obj.greet(); // 'Hello'
   ```

4. **Class Syntax**: ES6 syntax for creating objects and constructors.

   ```javascript
   class Person {
     constructor(name, age) {
       this.name = name;
       this.age = age;
     }
   }

   const alice = new Person("Alice", 25);
   ```

## 32. How does the `Array.prototype.reduce()` method work?

**Answer:**
`Array.prototype.reduce()` executes a reducer function (that you provide) on each element of the array, resulting in a single output value. The reducer function takes four arguments: accumulator, currentValue, currentIndex, and array.

```javascript
const numbers = [1, 2, 3, 4];

const sum = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue;
}, 0);

console.log(sum); // 10
```

## 33. What is the difference between `undefined` and `not defined`?

**Answer:**

- **`undefined`**: A variable that has been declared but not assigned a value is `undefined`. It is a built-in global property.

  ```javascript
  let a;
  console.log(a); // undefined
  ```

- **`not defined`**: Refers to a variable that has not been declared at all. Accessing it will throw a `ReferenceError`.

  ```javascript
  console.log(b); // ReferenceError: b is not defined
  ```

## 34. What are the different methods to iterate over arrays in JavaScript?

**Answer:**

1. **`for` Loop**: Traditional way to loop through array elements.

   ```javascript
   const arr = [1, 2, 3];
   for (let i = 0; i < arr.length; i++) {
     console.log(arr[i]);
   }
   ```

2. **`forEach()`**: Executes a provided function once for each array element.

   ```javascript
   arr.forEach((item) => console.log(item));
   ```

3. **`map()`**: Creates a new array populated with the results of calling a provided function on every element.

   ```javascript
   const doubled = arr.map((x) => x * 2);
   console.log(doubled); // [2, 4, 6]
   ```

4. **`filter()`**: Creates a new array with all elements that pass the test implemented by the provided function.

   ```javascript
   const evens = arr.filter((x) => x % 2 === 0);
   console.log(evens); // [2]
   ```

5. **`for...of`**: ES6 loop that iterates over iterable objects.

   ```javascript
   for (const item of arr) {
     console.log(item);
   }
   ```

## 35. What is the purpose of the `Symbol` type in JavaScript?

**Answer:**
`Symbol` is a primitive data type that is used to create unique identifiers for object properties. Symbols are often used to avoid name clashes between properties, as each symbol is guaranteed to be unique.

```javascript
const sym = Symbol("description");
const obj = {
  [sym]: "value",
};

console.log(obj[sym]); // 'value'
```

## 36. What are template literals and how are they used in JavaScript?

**Answer:**
Template literals are a way to work with strings in JavaScript using backticks (`` ` ``). They allow for multi-line strings and string interpolation.

- **Interpolation**: Embed expressions within strings using `${}`.

  ```javascript
  const name = "Alice";
  const greeting = `Hello, ${name}!`;
  console.log(greeting); // 'Hello, Alice!'
  ```

- **Multi-line Strings**: Write strings across multiple lines.

  ```javascript
  const multiLine = `This is a
  multi-line string.`;
  console.log(multiLine);
  ```

## 37. What is the difference between `call` and `apply` methods in JavaScript?

**Answer:**

- **`call()`**: Calls a function with a given `this` value and arguments provided individually.

  ```javascript
  function greet(greeting, name) {
    console.log(`${greeting}, ${name}`);
  }

  greet.call(null, "Hello", "Alice"); // 'Hello, Alice'
  ```

- **`apply()`**: Calls a function with a given `this` value and arguments provided as an array.

  ```javascript
  greet.apply(null, ["Hello", "Alice"]); // 'Hello, Alice'
  ```

## 38. What is the purpose of the `new` keyword in JavaScript?

**Answer:**
The `new` keyword is used to create instances of constructor functions or classes. It initializes a new object, sets the prototype of the new object to the prototype of the constructor, and returns the new object.

```javascript
function Person(name) {
  this.name = name;
}

const alice = new Person("Alice");
console.log(alice.name); // 'Alice'
```

## 39. What is the difference between `let` and `const`?

**Answer:**

- **`let`**: Allows you to declare a variable that can be reassigned. It is block-scoped.

  ```javascript
  let x = 10;
  x = 20; // Valid
  ```

- **`const`**: Declares a variable that cannot be reassigned. It is also block-scoped. However, objects and arrays declared with `const` can still be modified.

  ```javascript
  const y = 10;
  y = 20; // Error: Assignment to constant variable

  const obj = { a: 1 };
  obj.a = 2; // Valid
  ```

## 40. How does JavaScript's `Object.assign()` method work?

**Answer:**
`Object.assign()` copies the values of all enumerable own properties from one or more source objects to a target object. It returns the target object. It is often used to merge objects or create a shallow copy of an object.

```javascript
const target = { a: 1 };
const source = { b: 2 };

Object.assign(target, source);
console.log(target); // { a: 1, b: 2 }
```

## 41. What are JavaScript Data Types?

**Answer:**
JavaScript has the following data types:

- **Primitive Types**:

  - **String**: Represents a sequence of characters.
  - **Number**: Represents both integer and floating-point numbers.
  - **BigInt**: Represents large integers.
  - **Boolean**: Represents `true` or `false`.
  - **Undefined**: Represents a variable that has been declared but not assigned a value.
  - **Symbol**: Represents a unique and immutable value, often used as object property keys.
  - **Null**: Represents the intentional absence of any object value.

- **Non-Primitive Type**:
  - **Object**: Represents a collection of properties, including arrays, functions, and other objects.

```javascript
let str = "Hello"; // String
let num = 42; // Number
let bigInt = 9007199254740991n; // BigInt
let isTrue = true; // Boolean
let notDefined; // Undefined
let uniqueSymbol = Symbol("unique"); // Symbol
let nothing = null; // Null
```

## 42. What is a JavaScript Promise and how is it used?

**Answer:**
A JavaScript Promise is an object representing the eventual completion (or failure) of an asynchronous operation and its resulting value. It allows you to handle asynchronous operations more easily compared to using callbacks.

- **States of a Promise**:
  - **Pending**: Initial state, neither fulfilled nor rejected.
  - **Fulfilled**: The operation completed successfully.
  - **Rejected**: The operation failed.

```javascript
const promise = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Success"), 1000);
});

promise
  .then((result) => console.log(result)) // Output: 'Success'
  .catch((error) => console.error(error));
```

## 43. What is event delegation and why is it used?

**Answer:**
Event delegation is a technique where you use a single event listener on a parent element to manage events for its child elements. It works by taking advantage of event bubbling, which allows you to handle events at a higher level in the DOM tree.

**Advantages**:

- Reduces the number of event listeners in the application.
- Efficiently handles events for dynamically added elements.

```javascript
document.getElementById("parent").addEventListener("click", function (event) {
  if (event.target && event.target.matches("button")) {
    console.log("Button clicked:", event.target.textContent);
  }
});
```

## 44. How does JavaScript handle asynchronous code?

**Answer:**
JavaScript handles asynchronous code using several mechanisms:

- **Callbacks**: Functions passed as arguments to be executed later.

  ```javascript
  function fetchData(callback) {
    setTimeout(() => callback("Data fetched"), 1000);
  }

  fetchData((data) => console.log(data));
  ```

- **Promises**: Objects representing the eventual completion or failure of an asynchronous operation.

  ```javascript
  let promise = new Promise((resolve, reject) => {
    setTimeout(() => resolve("Data fetched"), 1000);
  });

  promise.then((data) => console.log(data));
  ```

- **Async/Await**: Syntactic sugar for handling Promises, making asynchronous code look synchronous.

  ```javascript
  async function fetchData() {
    let response = await new Promise((resolve) =>
      setTimeout(() => resolve("Data fetched"), 1000)
    );
    console.log(response);
  }

  fetchData();
  ```

## 45. What are higher-order functions in JavaScript?

**Answer:**
Higher-order functions are functions that either take other functions as arguments or return a function as a result. They enable more abstract and reusable code.

**Examples**:

- **Function that takes another function as an argument**:

  ```javascript
  function applyOperation(arr, operation) {
    return arr.map(operation);
  }

  const result = applyOperation([1, 2, 3], (x) => x * 2);
  console.log(result); // [2, 4, 6]
  ```

- **Function that returns another function**:

  ```javascript
  function multiplier(factor) {
    return function (x) {
      return x * factor;
    };
  }

  const double = multiplier(2);
  console.log(double(5)); // 10
  ```

## 46. Explain the concept of 'this' in JavaScript with examples.

**Answer:**
The `this` keyword refers to the context in which a function is executed. Its value varies depending on how the function is called:

- **Global Context**: Refers to the global object (`window` in browsers).

  ```javascript
  console.log(this); // Window object
  ```

- **Object Method**: Refers to the object the method is called on.

  ```javascript
  const obj = {
    name: "Alice",
    greet() {
      console.log(this.name);
    },
  };

  obj.greet(); // 'Alice'
  ```

- **Constructor Function**: Refers to the new instance being created.

  ```javascript
  function Person(name) {
    this.name = name;
  }

  const alice = new Person("Alice");
  console.log(alice.name); // 'Alice'
  ```

- **Event Handler**: Refers to the element that triggered the event.

  ```javascript
  document.getElementById("button").addEventListener("click", function () {
    console.log(this); // Button element
  });
  ```

- **Arrow Functions**: Do not have their own `this`; they inherit `this` from their lexical scope.

  ```javascript
  const obj = {
    name: "Alice",
    greet: () => {
      console.log(this.name); // 'this' refers to the enclosing scope, not `obj`
    },
  };

  obj.greet(); // undefined
  ```

## 47. What are `async` and `await` keywords in JavaScript?

**Answer:**

- **`async`**: Declares a function as asynchronous, which implicitly returns a Promise.

  ```javascript
  async function fetchData() {
    return "Data fetched";
  }

  fetchData().then(console.log); // 'Data fetched'
  ```

- **`await`**: Pauses the execution of an `async` function until a Promise is resolved. It can only be used inside `async` functions.

  ```javascript
  async function fetchData() {
    let result = await new Promise((resolve) =>
      setTimeout(() => resolve("Data fetched"), 1000)
    );
    console.log(result);
  }

  fetchData(); // 'Data fetched'
  ```

## 48. How does JavaScript's prototypal inheritance work?

**Answer:**
JavaScript uses prototypal inheritance to allow objects to inherit properties and methods from other objects. Each object has a prototype object that it inherits from, and it can also inherit from the prototype of its prototype, forming a prototype chain.

- **Example**:

  ```javascript
  const animal = {
    eat() {
      console.log("Eating");
    },
  };

  const dog = Object.create(animal);
  dog.bark = function () {
    console.log("Barking");
  };

  dog.eat(); // 'Eating'
  dog.bark(); // 'Barking'
  ```

## 49. What is the purpose of `Object.freeze()` in JavaScript?

**Answer:**
`Object.freeze()` prevents modifications to an object. Once an object is frozen, new properties cannot be added, existing properties cannot be removed or modified, and the object’s prototype cannot be changed.

- **Example**:

  ```javascript
  const obj = { name: "Alice" };
  Object.freeze(obj);

  obj.name = "Bob"; // No effect
  console.log(obj.name); // 'Alice'
  ```

## 50. What is the difference between `==` and `===` in JavaScript?

**Answer:**

- **`==` (Equality Operator)**: Compares values for equality after type conversion (type coercion).

  ```javascript
  console.log(0 == "0"); // true
  ```

- **`===` (Strict Equality Operator)**: Compares values for equality without type conversion. Both value and type must be the same.

  ```javascript
  console.log(0 === "0"); // false
  ```

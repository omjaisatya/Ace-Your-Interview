# JavaScript Interview Questions and Answers

### 1. What is the difference between `var`, `let`, and `const`?

**Answer:**

- `var`: Function-scoped or globally-scoped. Can be redeclared and updated.
- `let`: Block-scoped. Can be updated but not redeclared within the same scope.
- `const`: Block-scoped. Cannot be updated or redeclared. Must be initialized during declaration.

### 2. Explain the concept of hoisting in JavaScript.

**Answer:**
Hoisting is JavaScript's behavior of moving variable and function declarations to the top of their containing scope during the compile phase. This means you can use variables and functions before they are declared in the code. However, only declarations are hoisted, not initializations.

```javascript
console.log(x); // undefined
var x = 5;
```

### 3. What is a closure in JavaScript?

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

### 4. Explain the difference between `==` and `===` in JavaScript.

**Answer:**

- `==` (Equality Operator): Compares two values for equality after converting both values to a common type (type coercion).
- `===` (Strict Equality Operator): Compares both value and type for equality without type coercion.

```javascript
console.log(5 == "5"); // true
console.log(5 === "5"); // false
```

### 5. What is the purpose of the `this` keyword in JavaScript?

**Answer:**
The `this` keyword refers to the context in which a function is called. It can point to different objects depending on how the function is invoked:

- In a method of an object, `this` refers to the object itself.
- In a constructor function, `this` refers to the newly created instance.
- In a regular function, `this` refers to the global object (or undefined in strict mode).
- In an arrow function, `this` is lexically inherited from the outer function.

### 6. What are Promises in JavaScript?

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

### 7. What is event delegation?

**Answer:**
Event delegation is a technique where a single event listener is added to a parent element instead of adding listeners to multiple child elements. This leverages event bubbling to handle events at a higher level in the DOM tree.

```javascript
document.getElementById("parent").addEventListener("click", function (event) {
  if (event.target && event.target.matches("button.child")) {
    console.log("Button clicked!");
  }
});
```

### 8. Explain the concept of prototypal inheritance in JavaScript.

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

### 9. What is the purpose of `async` and `await` in JavaScript?

**Answer:**
`async` and `await` are used to work with Promises in a more synchronous fashion, making asynchronous code easier to read and write. The `async` keyword is used to define a function that returns a Promise, and `await` is used to pause the execution of the `async` function until the Promise is resolved.

```javascript
async function fetchData() {
  let response = await fetch("https://api.example.com/data");
  let data = await response.json();
  console.log(data);
}
```

### 10. What is the difference between `null` and `undefined`?

**Answer:**

- `null`: A value explicitly assigned to a variable to indicate the absence of any object value. It is a type itself.
- `undefined`: A value automatically assigned to a variable that has been declared but not yet initialized. It is a type itself.

```javascript
let a = null;
let b;
console.log(a); // null
console.log(b); // undefined
```

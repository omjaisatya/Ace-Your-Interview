# JavaScript Tricky Interview Question

## Question 1

What will be the output of the following JavaScript code?

```javascript
function foo() {
  console.log(a);
  console.log(bar());

  var a = 1;
  function bar() {
    return 2;
  }
}

foo();
```

The output of the code will be:

```javascript
undefined;
2;
```

## Question 2

What will be the output of the following JavaScript code?

```javascript
const a = [1, 2, 3];
const b = [1, 2, 3];

console.log(a == b);
console.log(a === b);
console.log(a.join() === b.join());
```

The output of the code will be:

```javascript
false;
false;
true;
```

## Question 3

What will be the output of the following JavaScript code?

```javascript
const obj = {
  value: 10,
  getValue: function () {
    return this.value;
  },
};

const getValue = obj.getValue;
console.log(getValue());
```

```javascript
undefined;
```

## Question 4

What will be the output of the following JavaScript code?

```javascript
let count = 0;

function increment() {
  count++;
  if (count < 3) {
    increment();
  }
}

increment();
console.log(count);
```

```javascript
3;
```

## Question 5

What will be the output of the following JavaScript code?

```javascript
const obj = {
  a: 1,
  b: 2,
  c: 3,
};

Object.keys(obj).forEach(function (key) {
  console.log(this[key]);
}, obj);
```

```javascript
1;
2;
3;
```

## Question 6

What will be the output of the following JavaScript code?

```javascript
function createCounter() {
  let count = 0;
  return function () {
    count++;
    return count;
  };
}

const counter1 = createCounter();
const counter2 = createCounter();

console.log(counter1()); // What will this print?
console.log(counter1()); // What will this print?
console.log(counter2()); // What will this print?
console.log(counter2()); // What will this print?
```

```javascript
1;
2;
1;
2;
```

# JavaScript Tricky Interview Question

## Question 7

What will be the output of the following JavaScript code?

```javascript
const obj = {
  name: "Alice",
  getName: function () {
    return this.name;
  },
};

const { getName } = obj;
console.log(getName());
```

```javascript
TypeError: Cannot read property 'name' of undefined
```

## Question 8

What will be the output of the following JavaScript code?

```javascript
const arr = [1, 2, 3];

arr[10] = 10;

console.log(arr.length);
console.log(arr[9]);
```

```javascript
11;
undefined;
```

## Question 9

What will be the output of the following JavaScript code?

```javascript
let x = 10;
let y = 20;

function example() {
  console.log(x); // What will this print?
  console.log(y); // What will this print?

  let x = 30;
  var y = 40;
}

example();
```

```javascript
ReferenceError: Cannot access 'x' before initialization
undefined
```

## Question 10

What will be the output of the following JavaScript code?

```javascript
const foo = (function () {
  return {
    bar: function () {
      return "bar";
    },
    baz: function () {
      return "baz";
    },
  };
})();

console.log(foo.bar());
console.log(foo.baz);
console.log(foo.baz());
```

```javascript
bar
[Function: baz]
baz
```

## Question 11

What will be the output of the following JavaScript code?

```javascript
let obj = {
  prop: "value",
};

Object.defineProperty(obj, "prop", {
  writable: false,
  configurable: false,
});

obj.prop = "new value";

console.log(obj.prop);
```

```javascript
value;
```

## Question 12

What will be the output of the following JavaScript code?

```javascript
const obj = {
  a: 1,
  b: 2,
  c: 3,
};

Object.freeze(obj);

obj.a = 10;
obj.d = 4;

console.log(obj.a); // What will this print?
console.log(obj.d); // What will this print?
console.log(Object.keys(obj)); // What will this print?
```

```javascript
1;
undefined;
[("a", "b", "c")];
```

## Question 13

What will be the output of the following JavaScript code?

```javascript
for (var i = 0; i < 3; i++) {
  setTimeout(function() {
    console.log(i);
  }, 1000);
}
```

## Answer

The output of the code will be:

```
3
3
3
```

### Explanation

1. **`var` and Function Scope**: The `var` keyword is function-scoped, not block-scoped. This means that the variable `i` is shared across all iterations of the loop. When the loop completes, the value of `i` is `3`.

2. **`setTimeout` and Closures**: The `setTimeout` function is asynchronous and runs after the loop has finished executing. By the time each `setTimeout` callback runs, the loop has already completed, and `i` is `3`.

3. **Output**: Since all three `setTimeout` callbacks share the same `i`, and by the time they execute `i` is `3`, the output is `3` printed three times.

### How to Fix It

If the intention is to print `0`, `1`, and `2`, you can use `let` instead of `var`:

```javascript
for (let i = 0; i < 3; i++) {
  setTimeout(function() {
    console.log(i);
  }, 1000);
}
```

With `let`, `i` is block-scoped, so each iteration of the loop gets its own copy of `i`. The output will be:

```
0
1
2
```

## Question 14

What will be the output of the following JavaScript code?

```javascript
console.log(typeof null);
console.log(null instanceof Object);
```

### Answer
The output of the code will be:

```bash
object
false
```


## Question 15

What will be the output of the following JavaScript code?

```javascript
let a = 1;
let b = { a: 2 };
let c = b;

c.a = 3;

console.log(a);  // What will this print?
console.log(b.a); // What will this print?
console.log(c.a); // What will this print?
```

## Answer

The output of the code will be:

```
1
3
3
```

### Explanation

1. **Primitive vs. Object Reference**:
   - `let a = 1;` creates a primitive variable `a` holding the value `1`.
   - `let b = { a: 2 };` creates an object `b` with a property `a` holding the value `2`.
   - `let c = b;` assigns the reference of object `b` to `c`. Now both `b` and `c` refer to the same object.

2. **Modification via Reference**:
   - `c.a = 3;` modifies the `a` property of the object referenced by `c`. Since `c` and `b` point to the same object, `b.a` is also affected.

3. **Output**:
   - `console.log(a);` prints `1` because the original primitive `a` is unchanged.
   - `console.log(b.a);` prints `3` because `b.a` was modified via `c`.
   - `console.log(c.a);` prints `3` because `c` refers to the same object as `b`.


## Question 16

What will be the output of the following JavaScript code?

```javascript
function sayHello() {
  return 
  {
    message: "Hello, world!"
  };
}

console.log(sayHello());
```

## Answer

The output of the code will be:

```
undefined
```

### Correcting the Code:
   - If you remove the line break between `return` and the object, or wrap the object in parentheses, the code will work as expected:
   ```javascript
   function sayHello() {
     return {
       message: "Hello, world!"
     };
   }
   ```

## Question 17

What will be the output of the following JavaScript code?

```javascript
function test() {
  console.log(a);
  console.log(foo());

  var a = 1;
  function foo() {
    return 2;
  }
}

test();
```

### Answer
The output of the code will be:

```javascript
undefined
2
```


## Question 18

What will be the output of the following JavaScript code?

```javascript
let x = 10;

function outer() {
  let x = 20;
  function inner() {
    x++;
    let x = 30;
    console.log(x);
  }
  inner();
}

outer();
```

### Answer
The output of the code will be:

```javascript
Uncaught ReferenceError: Cannot access 'x' before initialization
```

## Question 19

What will be the output of the following JavaScript code?

```javascript
let arr = [10, 20, 30];
arr[2] = arr;
console.log(arr);
```

### Answer
The output of the code will be:

```javascript
[10, 20, [10, 20, [Circular]]]
```

## Question 20

What will be the output of the following JavaScript code?

```javascript
console.log(1 + "2" + "2");
console.log(1 + +"2" + "2");
console.log(1 + -"1" + "2");
console.log(+"1" + "1" + "2");
console.log("A" - "B" + "2");
console.log("A" - "B" + 2);
```

### Answer
The output of the code will be:

```javascript
"122"
"32"
"02"
"112"
"NaN2"
NaN
```

## Question 21

What will be the output of the following JavaScript code?

```javascript
function foo() {
  return {
    bar: "hello"
  };
}

function baz() {
  return
  {
    bar: "hello"
  };
}

console.log(foo());
console.log(baz());
```

### Answer
The output of the code will be:

```javascript
{ bar: "hello" }
undefined
```

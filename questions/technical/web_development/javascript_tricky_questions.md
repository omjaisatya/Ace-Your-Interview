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
undefined[("a", "b", "c")];
```

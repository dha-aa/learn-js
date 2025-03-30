# Data Types in JavaScript

JavaScript provides different types of values, categorized into **primitive** and **reference (non-primitive)** data types.

## 1 - Primitive Data Types
Primitive types are immutable and stored directly in memory.

### a) String
Used for text.
```js
let name = "Alice";
let message = 'Hello, world!';
```

### b) Number
Represents both integers and floating-point numbers.
```js
let age = 25;
let price = 99.99;
```

### c) Boolean
Represents `true` or `false` values.
```js
let isLoggedIn = true;
let hasPermission = false;
```

### d) Undefined
A variable that has been declared but not assigned a value.
```js
let data;
console.log(data); // Output: undefined
```

### e) Null
Represents an intentional absence of value.
```js
let response = null;
```

### f) Symbol (ES6+)
Used to create unique values.
```js
const id = Symbol("unique");
```

### g) BigInt (ES11+)
Used for numbers beyond the safe integer limit.
```js
let bigNumber = 9007199254740991n;
```

## 2 - Reference (Non-Primitive) Data Types
Reference types store values as references in memory.

### a) Object
Used to store collections of data.
```js
let person = {
  name: "Alice",
  age: 30
};
```

### b) Array
A special type of object for ordered lists.
```js
let numbers = [1, 2, 3, 4, 5];
```

### c) Function
A reusable block of code.
```js
function greet() {
  console.log("Hello!");
}
```

## 3 - Checking Data Types
Use `typeof` to check a variable’s type.
```js
console.log(typeof 42); // "number"
console.log(typeof "Hello"); // "string"
console.log(typeof true); // "boolean"
console.log(typeof {}); // "object"
console.log(typeof []); // "object" (Arrays are a type of object)
console.log(typeof function() {}); // "function"
```

## Summary
- **Primitive types**: `string`, `number`, `boolean`, `undefined`, `null`, `symbol`, `bigint`.
- **Reference types**: `object`, `array`, `function`.
- Use `typeof` to check a value’s type.

Understanding data types helps in writing better, more efficient JavaScript code.


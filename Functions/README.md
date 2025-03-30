# Functions in JavaScript

Functions in JavaScript allow us to define reusable blocks of code that can be executed whenever needed. They help in organizing code, improving readability, and reducing redundancy.

## 1 - Defining a Function
### a) Function Declaration
A function declaration defines a named function.

#### Syntax:
```js
function functionName(parameters) {
  // Function body
  return value; // Optional
}
```

#### Example:
```js
function greet(name) {
  return "Hello, " + name + "!";
}
console.log(greet("Alice")); // "Hello, Alice!"
```

### b) Function Expression
A function expression assigns a function to a variable.

#### Example:
```js
const add = function(x, y) {
  return x + y;
};
console.log(add(3, 4)); // 7
```

### c) Arrow Function (ES6)
A shorter syntax for writing functions.

#### Example:
```js
const multiply = (a, b) => a * b;
console.log(multiply(4, 5)); // 20
```

## 2 - Function Parameters and Arguments
### a) Default Parameters
Assign default values to function parameters.

#### Example:
```js
function greet(name = "Guest") {
  return "Hello, " + name;
}
console.log(greet()); // "Hello, Guest"
```

### b) Rest Parameters (`...args`)
Allows passing multiple arguments as an array.

#### Example:
```js
function sum(...numbers) {
  return numbers.reduce((acc, num) => acc + num, 0);
}
console.log(sum(1, 2, 3, 4)); // 10
```

## 3 - Arguments Object
The `arguments` object is an array-like object available inside function bodies that contains all passed arguments.

#### Example:
```js
function showArguments() {
  console.log(arguments);
}
showArguments(1, 2, 3); // [1, 2, 3]
```

## 4 - Function Scope & Stack
- **Global Scope**: Variables declared outside functions.
- **Local Scope**: Variables declared inside a function.
- **Function Stack**: JavaScript maintains a function execution stack, handling function calls and returns.

#### Example:
```js
function first() {
  console.log("First function");
  second();
}
function second() {
  console.log("Second function");
}
first();
```

## 5 - Function Hoisting
Function declarations are **hoisted**, meaning they can be called before they are defined.

#### Example:
```js
sayHello(); // Works
function sayHello() {
  console.log("Hello!");
}
```

However, function expressions and arrow functions **are not hoisted**.
```js
// greet(); // Error: Cannot access 'greet' before initialization
const greet = () => console.log("Hi!");
```

## 6 - Closures and Lexical Scoping
A **closure** is a function that remembers the scope in which it was created, even when executed outside that scope.

#### Example:
```js
function outerFunction(outerVariable) {
  return function innerFunction(innerVariable) {
    console.log(`Outer: ${outerVariable}, Inner: ${innerVariable}`);
  };
}
const newFunction = outerFunction("Hello");
newFunction("World"); // Outer: Hello, Inner: World
```

## 7 - Recursion
Recursion occurs when a function calls itself.

#### Example:
```js
function factorial(n) {
  if (n === 0) return 1;
  return n * factorial(n - 1);
}
console.log(factorial(5)); // 120
```

## 8 - Built-in Functions
JavaScript provides built-in functions for various tasks.

#### Example:
```js
console.log(Math.max(1, 2, 3)); // 3
console.log(parseInt("10")); // 10
console.log(JSON.stringify({ name: "Alice" })); // "{"name":"Alice"}"
```

## 9 - Immediately Invoked Function Expressions (IIFE)
A function that runs as soon as it is defined.

#### Example:
```js
(function() {
  console.log("I am executed immediately!");
})();
```

## Summary
| Function Type | Description |
|--------------|-------------|
| Function Declaration | Named function that can be hoisted |
| Function Expression | Assigned to a variable, not hoisted |
| Arrow Function | Short syntax for function expressions |
| Higher-Order Function | Takes or returns a function |
| Callback Function | Passed as an argument to another function |
| IIFE | Executes immediately |
| Recursion | Function calling itself |
| Closures | Functions that retain access to their lexical scope |
| Built-in Functions | Predefined functions like `Math.max`, `JSON.stringify` |

Functions are essential for structuring JavaScript programs efficiently, enabling modular and reusable code.


# Understanding `let` in JavaScript

This document explains how the `let` keyword behaves in JavaScript, including its scoping rules and quirks. Uncomment each section in the code to test how `let` behaves.

## 1 - Basic Variable Declaration
`let` allows you to declare a variable and assign a value to it.

```js
let myName = "Alice";
console.log(myName); // Output: "Alice"
```

## 2 - Assigning Values
You can declare a `let` variable without assigning a value and assign it later.

```js
let age; // Declaring without assigning
age = 25; // Assigning a value
console.log(age); // Output: 25
```

You can also update the value of a `let` variable after it has been assigned.

```js
let mood = "happy";
mood = "excited";
console.log(mood); // Output: "excited"
```

## 3 - Redeclaring a Variable
Unlike `var`, `let` does **not** allow redeclaring the same variable within the same scope. Doing so will cause an error.

```js
let myName = "Alice";
let myName = "Bob"; // Error: Identifier 'myName' has already been declared
```

## 4 - `let` is Block-Scoped
Variables declared with `let` are only accessible within the block `{}` they are defined in.

```js
{
  let myName = "Alice";
}
console.log(myName); // Error: myName is not defined
```

## 5 - Function Scope Restriction
`let` is also function-scoped like `var`, but it does **not** leak outside blocks.

```js
let myName = "She doesn't like you";

function myFunc() {
  let myName = "She likes me!"; // This `myName` is local to the function
}

myFunc();
console.log(myName); // Output: "She doesn't like you" (function variable does not affect global scope)
```

## 6 - Global Scope
When `let` is declared outside of any function, it becomes a global variable but does **not** attach to the `window` object like `var`.

```js
let globalLet = "I am global";

function showGlobal() {
  console.log(globalLet); // Output: "I am global"
}

showGlobal();
console.log(globalLet); // Output: "I am global"
```

Unlike `var`, `let` does not create a global variable if assigned inside a function without `let`, `const`, or `var`.

```js
function badPractice() {
  globalLet = "I became global without let!";
}

badPractice();
console.log(globalLet); // ReferenceError: globalLet is not defined (Unlike `var`, `let` does not allow implicit global variables)
```

## Summary
- `let` **does not** allow redeclaring a variable in the same scope.
- It supports **block scope**, meaning variables inside `{}` are not accessible outside.
- Variables declared with `let` inside a function remain local to that function.
- `let` declared outside functions becomes a global variable but is **not** attached to `window`.
- Unlike `var`, `let` does **not** create a global variable if assigned without `let`, `const`, or `var` inside a function.
- You can declare a `let` variable without assigning a value and assign it later.
- Using `let` prevents many of the pitfalls of `var` and should be preferred for better scoping control.


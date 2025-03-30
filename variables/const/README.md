# Understanding `const` in JavaScript

This document explains how the `const` keyword behaves in JavaScript, including its scoping rules and quirks. Uncomment each section in the code to test how `const` behaves.

## 1 - Basic Variable Declaration
`const` allows you to declare a variable and assign a value to it. However, a `const` variable **must** be assigned a value at the time of declaration.

```js
const myName = "Alice";
console.log(myName); // Output: "Alice"
```

## 2 - Assigning Values
Unlike `let`, you **cannot** declare a `const` variable without assigning a value.

```js
const age; // Error: Missing initializer in const declaration
```

Once assigned, a `const` variable **cannot** be reassigned.

```js
const mood = "happy";
mood = "excited"; // Error: Assignment to constant variable
```

## 3 - Redeclaring a Variable
Like `let`, `const` does **not** allow redeclaring the same variable within the same scope.

```js
const myName = "Alice";
const myName = "Bob"; // Error: Identifier 'myName' has already been declared
```

## 4 - `const` is Block-Scoped
Variables declared with `const` are only accessible within the block `{}` they are defined in.

```js
{
  const myName = "Alice";
}
console.log(myName); // Error: myName is not defined
```

## 5 - Function Scope Restriction
`const` is also function-scoped like `let`, but it does **not** leak outside blocks.

```js
const myName = "She doesn't like you";

function myFunc() {
  const myName = "She likes me!"; // This `myName` is local to the function
}

myFunc();
console.log(myName); // Output: "She doesn't like you" (function variable does not affect global scope)
```

## 6 - Global Scope
When `const` is declared outside of any function, it becomes a global variable but does **not** attach to the `window` object like `var`.

```js
const globalConst = "I am global";

function showGlobal() {
  console.log(globalConst); // Output: "I am global"
}

showGlobal();
console.log(globalConst); // Output: "I am global"
```

Unlike `var`, `const` does not create a global variable if assigned inside a function without `const`, `let`, or `var`.

```js
function badPractice() {
  globalConst = "I became global without const!";
}

badPractice();
console.log(globalConst); // ReferenceError: globalConst is not defined (Unlike `var`, `const` does not allow implicit global variables)
```

## 7 - `const` with Objects and Arrays
While you **cannot** reassign a `const` variable, **you can still modify the contents** of an object or array declared with `const`.

```js
const person = { name: "Alice", age: 25 };
person.age = 26; // Allowed
console.log(person.age); // Output: 26

person = { name: "Bob", age: 30 }; // Error: Assignment to constant variable
```

For arrays:

```js
const numbers = [1, 2, 3];
numbers.push(4); // Allowed
console.log(numbers); // Output: [1, 2, 3, 4]

numbers = [5, 6, 7]; // Error: Assignment to constant variable
```

## Summary
- `const` **must** be assigned a value at declaration.
- It **cannot** be reassigned after declaration.
- It supports **block scope**, meaning variables inside `{}` are not accessible outside.
- Variables declared with `const` inside a function remain local to that function.
- `const` declared outside functions becomes a global variable but is **not** attached to `window`.
- Unlike `var`, `const` does **not** create a global variable if assigned without `const`, `let`, or `var` inside a function.
- **Objects and arrays declared with `const` can have their properties or elements modified but cannot be reassigned.**
- `const` is best used for values that should not change, preventing unintended modifications.


# Understanding `var` in JavaScript

This document explains how the `var` keyword behaves in JavaScript, including its scoping rules and quirks. Uncomment each section in the code to test how `var` behaves.

## 1 - Basic Variable Declaration
`var` allows you to declare a variable and assign a value to it.

```js
var myName = "Alice";
console.log(myName); // Output: "Alice"
```

## 2 - Redeclaring a Variable
`var` allows you to redeclare the same variable in the same scope. The second declaration will override the first one.

```js
var myName = "Alice";
var myName = "Bob"; 
console.log(myName); // Output: "Bob"
```

## 3 - `var` is Function-Scoped, Not Block-Scoped
Even though `myName` is declared inside a block `{}`, it is still accessible outside. This happens because `var` does NOT support block-level scope, only function scope.

```js
{
  var myName = "Alice";
}
console.log(myName); // Output: "Alice" (no error)
```

## 4 - Function Scope Restriction
`var` is function-scoped, so when declared inside a function, it does not affect the outer variable. The function's variable remains inside the function and does not modify the global one.

```js
var myName = "She doesn't like you";

function myFunc() {
  var myName = "She likes me!"; // This `myName` is local to the function
}

myFunc();
console.log(myName); // Output: "She doesn't like you" (function variable does not affect global scope)
```

## 5 - Global Scope
When `var` is declared outside of any function, it becomes a global variable and can be accessed from anywhere in the script.

```js
var globalVar = "I am global";

function showGlobal() {
  console.log(globalVar); // Output: "I am global"
}

showGlobal();
console.log(globalVar); // Output: "I am global"
```

However, if `var` is declared inside a function without `var`, `let`, or `const`, it will automatically become global (which is a bad practice).

```js
function badPractice() {
  globalVar = "I became global without var!";
}

badPractice();
console.log(globalVar); // Output: "I became global without var!" (Avoid this!)
```

## Summary
- `var` can be redeclared within the same scope.
- It does **not** support block scope, only function scope.
- Variables declared with `var` inside a function remain local to that function.
- `var` declared outside functions becomes a global variable.
- Assigning a variable without `var`, `let`, or `const` inside a function makes it global (avoid this).
- Using `var` can lead to unexpected behaviors; prefer `let` or `const` for better scoping control.

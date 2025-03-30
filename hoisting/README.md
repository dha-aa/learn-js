# Hoisting in JavaScript

Hoisting is a JavaScript mechanism where variable and function declarations are moved (hoisted) to the top of their containing scope during compilation. However, different variable declarations (`var`, `let`, and `const`) behave differently with hoisting.

## 1 - Hoisting with `var`
Variables declared with `var` are hoisted to the top and initialized with `undefined`.

```js
console.log(myVar); // Output: undefined
var myVar = "Hoisting example";
```

Even though `var myVar` is declared later in the code, JavaScript moves the declaration to the top, but the assignment remains in place. This is why accessing it before assignment results in `undefined` rather than an error.

## 2 - Hoisting with `let` and `const`
Variables declared with `let` and `const` are also hoisted, but they remain in a **temporal dead zone** until their declaration is reached.

```js
console.log(myLet); // ReferenceError: Cannot access 'myLet' before initialization
let myLet = "Hoisted but not initialized";
```

```js
console.log(myConst); // ReferenceError: Cannot access 'myConst' before initialization
const myConst = "Hoisting with const";
```

Unlike `var`, `let` and `const` do **not** get initialized with `undefined`. Instead, they stay in a **temporal dead zone** from the start of their enclosing scope until their declaration is encountered.

## 3 - Hoisting with Functions
Function declarations are fully hoisted, meaning they can be used before they are defined.

```js
sayHello(); // Output: "Hello!"

function sayHello() {
  console.log("Hello!");
}
```

However, function expressions (assigned to `var`, `let`, or `const`) are not hoisted in the same way.

```js
sayHello(); // TypeError: sayHello is not a function

var sayHello = function() {
  console.log("Hello!");
};
```

With `let` and `const`, it behaves similarly due to the temporal dead zone.

```js
sayHello(); // ReferenceError: Cannot access 'sayHello' before initialization

const sayHello = function() {
  console.log("Hello!");
};
```

## Summary
- `var` is hoisted and initialized with `undefined`.
- `let` and `const` are hoisted but remain in a **temporal dead zone** until their declaration is encountered.
- Function declarations are fully hoisted, allowing them to be used before they are defined.
- Function expressions (assigned to variables) are **not** hoisted in the same way, causing errors if accessed before declaration.

.


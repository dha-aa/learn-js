# Strict Mode in JavaScript

Strict Mode in JavaScript is a feature that helps catch common coding mistakes and prevent the use of unsafe actions. It enforces a stricter set of rules for JavaScript execution.

## 1 - Enabling Strict Mode
Strict Mode can be enabled by adding `'use strict';` at the beginning of a script or a function.

### a) Enabling for an entire script:
```js
'use strict';
// Entire script runs in strict mode
```

### b) Enabling for a specific function:
```js
function myFunction() {
  'use strict';
  // Function runs in strict mode
}
```

## 2 - Features and Restrictions of Strict Mode

### a) Prevents Accidental Global Variables
Without strict mode, assigning a value to an undeclared variable creates a global variable.

#### Example (Non-strict mode):
```js
myVar = 10; // No error (creates a global variable implicitly)
console.log(myVar);
```

#### Example (Strict mode):
```js
'use strict';
myVar = 10; // Error: myVar is not defined
```

### b) Disallows Duplicating Parameter Names
In non-strict mode, duplicate function parameter names are allowed.

#### Example (Strict mode throws an error):
```js
'use strict';
function sum(a, a) { // SyntaxError
  return a + a;
}
```

### c) Prevents Deleting Variables or Functions
Strict Mode prevents the deletion of variables, functions, and certain built-in properties.

#### Example:
```js
'use strict';
let x = 10;
delete x; // SyntaxError: Delete of an unqualified identifier in strict mode.
```

### d) Requires Secure `this` Binding
In non-strict mode, `this` can refer to the global object in functions. In strict mode, `this` remains `undefined` in functions that are not methods of an object.

#### Example:
```js
'use strict';
function showThis() {
  console.log(this); // undefined instead of global object
}
showThis();
```

### e) Prevents Writing to Read-Only Properties
Attempting to assign a value to a non-writable property results in an error.

#### Example:
```js
'use strict';
const obj = {};
Object.defineProperty(obj, 'prop', { value: 42, writable: false });
obj.prop = 50; // TypeError: Cannot assign to read-only property
```

### f) Prevents Octal Literals
Octal literals (numbers with a leading zero) are not allowed.

#### Example:
```js
'use strict';
let num = 010; // SyntaxError: Octal literals are not allowed in strict mode.
```

### g) Prohibits `with` Statements
Strict Mode disallows `with` statements as they can lead to ambiguity.

#### Example:
```js
'use strict';
with (Math) { // SyntaxError: Strict mode code may not include a with statement
  console.log(PI);
}
```

## 3 - Benefits of Using Strict Mode
- Helps prevent common mistakes.
- Makes debugging easier.
- Improves security by restricting unsafe operations.
- Prepares for future JavaScript versions.
- Makes the code run faster in some cases (optimized by JavaScript engines).

## 4 - When to Use Strict Mode
Strict Mode should be used in all modern JavaScript projects to ensure best coding practices and avoid common pitfalls. It is especially useful when writing modular or large-scale applications.

## Summary
| Feature | Non-Strict Mode | Strict Mode |
|---------|---------------|-------------|
| Implicit Global Variables | Allowed | Not Allowed |
| Duplicate Parameters | Allowed | Error |
| Deleting Variables | Allowed | Error |
| `this` in Functions | Global Object | `undefined` |
| Writing to Read-Only Properties | No Error | Error |
| Octal Literals | Allowed | Error |
| `with` Statement | Allowed | Error |

Strict Mode enforces a cleaner, safer coding style, helping developers avoid bugs and security risks in JavaScript.


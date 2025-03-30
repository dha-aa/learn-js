# Naming Rules in JavaScript

In JavaScript, variable and function names must follow certain rules and best practices to ensure code readability and maintainability.

## 1 - Valid Naming Rules
JavaScript variable names:
- Can include **letters (a-z, A-Z), digits (0-9), underscores (_), and dollar signs ($)**.
- **Cannot** start with a digit (0-9).
- Are **case-sensitive** (`myVar` and `myvar` are different variables).
- **Cannot** use JavaScript **reserved keywords** (e.g., `var`, `function`, `return`).

### Examples of valid names:
```js
let myVariable;
let _privateVar;
let $dollarSign;
let camelCaseExample;
let snake_case_example;
```

### Invalid names:
```js
let 1number; // ❌ Error: Cannot start with a number
let var; // ❌ Error: 'var' is a reserved keyword
let my-variable; // ❌ Error: Hyphens are not allowed (used in subtraction)
```

## 2 - Best Practices for Naming Variables
- **Use descriptive names** that clearly indicate what the variable represents.
  ```js
  let userAge = 25; // ✅ Good
  let x = 25; // ❌ Bad (unclear meaning)
  ```
- **Follow camelCase for variables and functions**.
  ```js
  let userName;
  function getUserData() {}
  ```
- **Use PascalCase for constructor functions and classes**.
  ```js
  class UserAccount {}
  function Person() {}
  ```
- **Use ALL_CAPS for constants**.
  ```js
  const MAX_USERS = 100;
  ```

## 3 - Reserved Keywords
JavaScript has a set of reserved words that cannot be used as variable names. Some common reserved keywords include:

```js
break, case, catch, class, const, continue, debugger, default, delete,
do, else, enum, export, extends, false, finally, for, function,
if, implements, import, in, instanceof, interface, let, new,
null, package, private, protected, public, return, static,
super, switch, this, throw, true, try, typeof, var, void,
while, with, yield
```

Attempting to use a reserved keyword as a variable name will result in an error.

```js
let return = 5; // ❌ Error: Unexpected token 'return'
```

## Summary
- Use letters, numbers, `_`, and `$` but never start with a number.
- Avoid reserved keywords.
- Use **camelCase** for variables and functions, **PascalCase** for classes, and **ALL_CAPS** for constants.
- Use meaningful, descriptive names for better code readability.




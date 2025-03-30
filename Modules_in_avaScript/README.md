# Modules in JavaScript

JavaScript **modules** allow you to break code into reusable, independent files, improving maintainability and reusability. Modern JavaScript uses **ES Modules (ESM)**, which support importing and exporting functionalities across files.

## 1 - Exporting and Importing Modules
Modules use the `export` and `import` keywords.

### Named Exports
Named exports allow multiple exports from a single file.

#### Example (`math.js` - exporting file):
```js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;
```

#### Example (`app.js` - importing file):
```js
import { add, subtract } from "./math.js";
console.log(add(2, 3)); // 5
console.log(subtract(5, 2)); // 3
```

### Default Exports
A module can have **one default export**.

#### Example (`message.js` - exporting file):
```js
export default function greet(name) {
  return `Hello, ${name}!`;
}
```

#### Example (`app.js` - importing file):
```js
import greet from "./message.js";
console.log(greet("Alice")); // Hello, Alice!
```

## 2 - Importing Everything
You can import all exports from a module using `*`.

#### Example:
```js
import * as MathUtils from "./math.js";
console.log(MathUtils.add(4, 5)); // 9
```

## 3 - Dynamic Imports
Dynamic imports allow loading modules **conditionally** or **on demand** using `import()`.

#### Example:
```js
async function loadModule() {
  const module = await import("./math.js");
  console.log(module.add(10, 5));
}
loadModule();
```

## 4 - Module Scope
Each module has its **own scope**, meaning variables and functions defined inside a module **do not pollute the global scope**.

#### Example:
```js
// file1.js
const secret = "This is private";
export const publicValue = "This is public";
```

```js
// app.js
import { publicValue } from "./file1.js";
console.log(publicValue); // Works
console.log(secret); // Error: secret is not defined
```

## 5 - CommonJS vs. ES Modules
Older JavaScript environments (like Node.js before ES Modules) use **CommonJS** (`require` instead of `import`).

### CommonJS Syntax:
```js
// Export
module.exports = { add, subtract };

// Import
const math = require("./math.js");
console.log(math.add(3, 2));
```

## 6 - Using Modules in HTML
When using modules in a browser, the script must have `type="module"`.

#### Example:
```html
<script type="module" src="app.js"></script>
```

## Summary
| Feature | Description |
|---------|-------------|
| Named Exports | Allows multiple exports from a module |
| Default Exports | Allows a single export per module |
| Importing Everything | Uses `*` to import all exports |
| Dynamic Imports | Uses `import()` to load modules asynchronously |
| Module Scope | Each module has its own scope |
| CommonJS | Uses `require()` in older JavaScript environments |

Modules enhance code organization, maintainability, and performance, making them essential for modern JavaScript development.


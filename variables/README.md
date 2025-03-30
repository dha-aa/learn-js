
## Variable Declarations in JavaScript

In JavaScript, you can declare variables using `var`, `let`, or `const`. However, `let` and `const` are recommended because they fix issues with `var`.

### `var` (Old way, function-scoped)
```js
var name = "Alice";
var name = "Bob"; // ✅ No error, but can cause bugs
console.log(name); // Output: Bob
```
- `var` can be redeclared, which can lead to unexpected issues.
- It does **not** have block scope.

### `let` (Modern way, block-scoped)
```js
let age = 25;
age = 26; // ✅ Can be updated
console.log(age); // Output: 26
```
- `let` allows reassignment but **cannot** be redeclared in the same scope.
- It is **block-scoped**, meaning it's only accessible within `{}`.

### `const` (For values that don’t change)
```js
const PI = 3.14;
PI = 3.1415; // ❌ Error: Cannot change a constant
```
- `const` cannot be reassigned after declaration.
- It is also **block-scoped** like `let`.

### Key Differences  
| Feature  | `var` | `let` | `const` |
|----------|------|------|------|
| Scope | Function-scoped | Block-scoped | Block-scoped |
| Can be updated? | ✅ Yes | ✅ Yes | ❌ No |
| Can be redeclared? | ✅ Yes | ❌ No | ❌ No |

### Best Practice  
- Use `const` by default.  
- Use `let` only when you **need** to change the value.  
- **Avoid `var`** because it can cause unexpected issues.  
```

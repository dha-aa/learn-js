# Loops and Iterations in JavaScript

Loops are used to execute a block of code multiple times. JavaScript provides several looping mechanisms to handle different iteration scenarios.

## 1 - For Loop
A `for` loop runs a block of code a specific number of times.

### Syntax:
```js
for (initialization; condition; increment/decrement) {
  // Code to execute
}
```

### Example:
```js
for (let i = 0; i < 5; i++) {
  console.log(i); // Prints 0 to 4
}
```

## 2 - While Loop
A `while` loop runs as long as the given condition is `true`.

### Syntax:
```js
while (condition) {
  // Code to execute
}
```

### Example:
```js
let count = 0;
while (count < 3) {
  console.log(count);
  count++;
}
```

## 3 - Do-While Loop
A `do-while` loop runs **at least once** before checking the condition.

### Syntax:
```js
do {
  // Code to execute
} while (condition);
```

### Example:
```js
let num = 0;
do {
  console.log(num);
  num++;
} while (num < 3);
```

## 4 - For...of Loop
A `for...of` loop iterates over **iterable objects** like arrays, strings, or sets.

### Syntax:
```js
for (const item of iterable) {
  // Code to execute
}
```

### Example:
```js
let fruits = ["Apple", "Banana", "Cherry"];
for (const fruit of fruits) {
  console.log(fruit);
}
```

## 5 - For...in Loop
A `for...in` loop iterates over the **keys of an object**.

### Syntax:
```js
for (const key in object) {
  // Code to execute
}
```

### Example:
```js
let person = { name: "Alice", age: 25, city: "New York" };
for (const key in person) {
  console.log(`${key}: ${person[key]}`);
}
```

## 6 - Break and Continue
### `break`: Exits the loop immediately.
```js
for (let i = 0; i < 5; i++) {
  if (i === 3) break;
  console.log(i); // Prints 0, 1, 2
}
```

### `continue`: Skips the current iteration and moves to the next one.
```js
for (let i = 0; i < 5; i++) {
  if (i === 2) continue;
  console.log(i); // Prints 0, 1, 3, 4
}
```

## Summary
| Loop Type | Best Used For |
|-----------|--------------|
| `for` | Fixed number of iterations |
| `while` | Unknown number of iterations (until a condition is met) |
| `do-while` | Ensuring at least one execution before checking the condition |
| `for...of` | Iterating over iterable objects (arrays, strings, etc.) |
| `for...in` | Iterating over object properties |

Choosing the right loop helps in optimizing performance and improving readability in JavaScript code.


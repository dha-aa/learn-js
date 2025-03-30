# Control Flow in JavaScript

Control flow determines the order in which statements are executed in a program. JavaScript provides various control structures for decision-making and flow control.

## 1 - Conditional Statements
### a) `if` Statement
Executes a block of code **if** a condition is `true`.

#### Syntax:
```js
if (condition) {
  // Code to execute if condition is true
}
```

#### Example:
```js
let age = 18;
if (age >= 18) {
  console.log("You are an adult.");
}
```

### b) `if...else` Statement
Executes different blocks based on the condition.

#### Example:
```js
let age = 16;
if (age >= 18) {
  console.log("You are an adult.");
} else {
  console.log("You are a minor.");
}
```

### c) `if...else if...else` Statement
Checks multiple conditions sequentially.

#### Example:
```js
let score = 85;
if (score >= 90) {
  console.log("Grade: A");
} else if (score >= 80) {
  console.log("Grade: B");
} else {
  console.log("Grade: C or below");
}
```

## 2 - Switch Statement
The `switch` statement selects one of many code blocks based on a given value.

#### Syntax:
```js
switch (expression) {
  case value1:
    // Code for value1
    break;
  case value2:
    // Code for value2
    break;
  default:
    // Default case
}
```

#### Example:
```js
let day = "Monday";
switch (day) {
  case "Monday":
    console.log("Start of the week!");
    break;
  case "Friday":
    console.log("Weekend is near!");
    break;
  default:
    console.log("A regular day.");
}
```

## 3 - Ternary Operator (`?:`)
A shorthand for `if...else`.

#### Syntax:
```js
condition ? expressionIfTrue : expressionIfFalse;
```

#### Example:
```js
let age = 20;
let status = (age >= 18) ? "Adult" : "Minor";
console.log(status); // Adult
```

## 4 - Error Handling
Error handling prevents program crashes and provides meaningful error messages.

### `try...catch` Block
Executes code and handles errors if they occur.

#### Example:
```js
try {
  let result = someUndefinedFunction();
} catch (error) {
  console.log("An error occurred: ", error.message);
}
```

### `finally` Block
Executes code **regardless** of an error occurring.

#### Example:
```js
try {
  console.log("Try block executed");
} catch (error) {
  console.log("Error caught");
} finally {
  console.log("Finally block executed");
}
```

## Summary
| Control Structure | Use Case |
|------------------|----------|
| `if` | Executes code when a condition is true |
| `if...else` | Executes one block for true, another for false |
| `if...else if...else` | Checks multiple conditions |
| `switch` | Handles multiple cases efficiently |
| `?:` (Ternary) | Short-hand for `if...else` |
| `try...catch` | Handles runtime errors gracefully |

Control flow structures
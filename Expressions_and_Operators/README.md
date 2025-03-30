# Expressions and Operators in JavaScript

JavaScript provides various expressions and operators to perform computations and manipulate data.

## 1 - Expressions
An **expression** is a combination of values, variables, and operators that results in a value.

### a) Arithmetic Expressions
Perform mathematical operations.
```js
let sum = 5 + 3; // 8
let product = 4 * 2; // 8
```

### b) String Expressions
Concatenates strings.
```js
let greeting = "Hello" + " World!"; // "Hello World!"
```

### c) Logical Expressions
Evaluate to `true` or `false`.
```js
let isValid = (5 > 3) && (10 > 8); // true
```

---

## 2 - Operators
Operators allow performing operations on variables and values.

### a) Arithmetic Operators
| Operator | Description | Example |
|----------|-------------|----------|
| `+` | Addition | `5 + 2 // 7` |
| `-` | Subtraction | `5 - 2 // 3` |
| `*` | Multiplication | `5 * 2 // 10` |
| `/` | Division | `10 / 2 // 5` |
| `%` | Modulus (Remainder) | `10 % 3 // 1` |
| `**` | Exponentiation | `2 ** 3 // 8` |

### b) Assignment Operators
| Operator | Description | Example |
|----------|-------------|----------|
| `=` | Assigns value | `x = 10` |
| `+=` | Adds and assigns | `x += 5` (same as `x = x + 5`) |
| `-=` | Subtracts and assigns | `x -= 2` (same as `x = x - 2`) |
| `*=` | Multiplies and assigns | `x *= 3` |
| `/=` | Divides and assigns | `x /= 2` |

### c) Comparison Operators
| Operator | Description | Example |
|----------|-------------|----------|
| `==` | Equal (loose) | `5 == "5" // true` |
| `===` | Strict equal | `5 === "5" // false` |
| `!=` | Not equal | `5 != 3 // true` |
| `!==` | Strict not equal | `5 !== "5" // true` |
| `>` | Greater than | `10 > 5 // true` |
| `<` | Less than | `5 < 10 // true` |

### d) Logical Operators
| Operator | Description | Example |
|----------|-------------|----------|
| `&&` | AND | `(true && false) // false` |
| `||` | OR | `(true || false) // true` |
| `!` | NOT | `!true // false` |

### e) Bitwise Operators
Used to manipulate binary representations of numbers.
```js
let result = 5 & 1; // Bitwise AND
let resultOr = 5 | 1; // Bitwise OR
```

### f) Ternary Operator (`?:`)
Shorthand for `if...else`.
```js
let age = 20;
let status = (age >= 18) ? "Adult" : "Minor";
console.log(status); // "Adult"
```

### g) Type Operators
| Operator | Description | Example |
|----------|-------------|----------|
| `typeof` | Returns data type | `typeof "Hello" // "string"` |
| `instanceof` | Checks instance of an object | `[] instanceof Array // true` |

---

## Summary
- **Expressions** produce values, such as arithmetic, string, and logical expressions.
- **Operators** manipulate values, including arithmetic, comparison, logical, bitwise, and assignment operators.
- **The ternary operator** provides a shorthand for conditional statements.
- **Type operators** help check types and instances of objects.

Understanding expressions and operators allows for better control and efficiency in JavaScript programming.


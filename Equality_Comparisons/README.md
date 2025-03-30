# Equality Comparisons in JavaScript

JavaScript provides different ways to compare values. Understanding these comparisons is crucial for writing correct and bug-free code.

## 1 - Loose Equality (`==`)
Loose equality compares values after performing type conversion.

### Examples:
```js
console.log(5 == "5"); // true (string "5" is converted to number 5)
console.log(0 == false); // true (false is converted to 0)
console.log(null == undefined); // true (special case)
```

### Key Takeaways:
- Converts types before comparison.
- Can lead to unexpected results if not used carefully.

## 2 - Strict Equality (`===`)
Strict equality checks both **value and type** without type conversion.

### Examples:
```js
console.log(5 === "5"); // false (different types: number vs. string)
console.log(0 === false); // false (number vs. boolean)
console.log(null === undefined); // false (different types)
```

### Key Takeaways:
- Does **not** perform type conversion.
- Safer and more predictable than `==`.

## 3 - Object.is() (SameValue Algorithm)
`Object.is()` is used for precise equality checks, similar to `===`, but handles edge cases differently.

### Examples:
```js
console.log(Object.is(0, -0)); // false (distinguishes +0 and -0)
console.log(Object.is(NaN, NaN)); // true (correctly identifies NaN as equal to itself)
console.log(Object.is(5, 5)); // true (same value and type)
```

### Key Takeaways:
- More precise than `===` for special cases (`NaN`, `+0`, `-0`).
- Used when strict equality is not sufficient.

## 4 - SameValueZero Algorithm
SameValueZero is similar to `Object.is()`, but it treats `+0` and `-0` as equal.

### Examples:
```js
let mySet = new Set();
mySet.add(0);
console.log(mySet.has(-0)); // true (SameValueZero treats +0 and -0 as the same)

console.log([NaN].includes(NaN)); // true (SameValueZero correctly matches NaN)
```

### Key Takeaways:
- Used in data structures like `Set`, `Map`, and array methods (`includes`).
- Treats `+0` and `-0` as equal, unlike `Object.is()`.

## Summary
| Method        | Type Conversion | Treats `NaN === NaN` | Distinguishes `+0` and `-0` |
|--------------|---------------|--------------------|--------------------|
| `==` (Loose) | ✅ Yes         | ❌ No              | ❌ No              |
| `===` (Strict) | ❌ No        | ❌ No              | ❌ No              |
| `Object.is()` | ❌ No        | ✅ Yes             | ✅ Yes             |
| SameValueZero | ❌ No        | ✅ Yes             | ❌ No              |

Choosing the right equality comparison method is essential for writing reliable JavaScript code.


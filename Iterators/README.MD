# Iterators and Generators in JavaScript

JavaScript provides **Iterators** and **Generators** to handle iteration over collections efficiently and lazily.

## 1 - Iterators
An **iterator** is an object that follows the iterator protocol. It has a `next()` method that returns an object with two properties:
- `value`: The next value in the sequence.
- `done`: A boolean indicating if the iteration is complete.

### Example:
```js
function createIterator(array) {
  let index = 0;
  return {
    next: function () {
      return index < array.length
        ? { value: array[index++], done: false }
        : { done: true };
    },
  };
}

const iterator = createIterator(["a", "b", "c"]);
console.log(iterator.next()); // { value: "a", done: false }
console.log(iterator.next()); // { value: "b", done: false }
console.log(iterator.next()); // { value: "c", done: false }
console.log(iterator.next()); // { done: true }
```

## 2 - The Iterable Protocol
An object is **iterable** if it has a `[Symbol.iterator]()` method that returns an iterator.

### Example:
```js
const iterable = {
  data: [1, 2, 3],
  [Symbol.iterator]() {
    let index = 0;
    return {
      next: () =>
        index < this.data.length
          ? { value: this.data[index++], done: false }
          : { done: true },
    };
  },
};

for (const value of iterable) {
  console.log(value);
}
// Output: 1, 2, 3
```

## 3 - Generators
A **generator** is a special function that can pause and resume execution. It is defined using `function*` and uses the `yield` keyword.

### Example:
```js
function* generatorFunction() {
  yield 1;
  yield 2;
  yield 3;
}

const generator = generatorFunction();
console.log(generator.next()); // { value: 1, done: false }
console.log(generator.next()); // { value: 2, done: false }
console.log(generator.next()); // { value: 3, done: false }
console.log(generator.next()); // { done: true }
```

## 4 - Using `for...of` with Generators
Generators are iterable, meaning we can use `for...of` to iterate over them.

### Example:
```js
function* generatorFunction() {
  yield "Hello";
  yield "World";
}

for (const value of generatorFunction()) {
  console.log(value);
}
// Output: "Hello", "World"
```

## 5 - Generator with `return`
A `return` statement inside a generator stops execution immediately.

### Example:
```js
function* generatorFunction() {
  yield 1;
  return 2;
  yield 3; // This will not execute
}

const generator = generatorFunction();
console.log(generator.next()); // { value: 1, done: false }
console.log(generator.next()); // { value: 2, done: true }
console.log(generator.next()); // { done: true }
```

## 6 - Generator Delegation
A generator can delegate execution to another generator using `yield*`.

### Example:
```js
function* subGenerator() {
  yield "a";
  yield "b";
}

function* mainGenerator() {
  yield 1;
  yield* subGenerator();
  yield 2;
}

for (const value of mainGenerator()) {
  console.log(value);
}
// Output: 1, "a", "b", 2
```

## 7 - Asynchronous Generators
Using `async function*`, we can create asynchronous iterators that work well with `for await...of`.

### Example:
```js
async function* asyncGenerator() {
  yield Promise.resolve("Hello");
  yield Promise.resolve("World");
}

(async () => {
  for await (const value of asyncGenerator()) {
    console.log(value);
  }
})();
// Output: "Hello", "World"
```

## Summary
| Feature | Description |
|---------|-------------|
| Iterators | Objects implementing `next()` method to iterate over collections |
| Iterable Protocol | Objects implementing `[Symbol.iterator]()` returning an iterator |
| Generators | Functions that pause and resume using `yield` |
| `for...of` | Iterates over iterables and generators |
| `yield*` | Delegates execution to another generator |
| Asynchronous Generators | Used with `for await...of` for async iteration |

Understanding iterators and generators helps in working with lazy sequences, improving performance, and writing asynchronous code efficiently.


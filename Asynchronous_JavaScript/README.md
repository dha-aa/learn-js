# Asynchronous JavaScript

JavaScript is **single-threaded**, meaning it executes one operation at a time. Asynchronous programming allows JavaScript to perform tasks without blocking the execution of other code.

## 1 - `setTimeout`
The `setTimeout` function schedules a function to run **after** a specified delay.

### Syntax:
```js
setTimeout(callback, delay);
```

### Example:
```js
console.log("Start");
setTimeout(() => console.log("After 2 seconds"), 2000);
console.log("End");
```

### Output:
```
Start
End
After 2 seconds
```

### How it Works:
- `setTimeout` sends the callback to the Web API.
- JavaScript continues executing the remaining code.
- After the delay, the callback moves to the **callback queue** and waits for the event loop.

## 2 - `setInterval`
The `setInterval` function repeatedly calls a function at specified intervals.

### Syntax:
```js
setInterval(callback, interval);
```

### Example:
```js
let count = 0;
const interval = setInterval(() => {
  console.log("Count:", ++count);
  if (count === 5) clearInterval(interval); // Stops after 5 times
}, 1000);
```

## 3 - Callbacks
A **callback** is a function passed as an argument to another function and executed later.

### Example:
```js
function fetchData(callback) {
  setTimeout(() => {
    callback("Data received");
  }, 2000);
}

fetchData((message) => console.log(message)); // Data received
```

## 4 - Callback Hell
When multiple callbacks are nested, making the code difficult to read and maintain, it’s called **callback hell**.

### Example:
```js
setTimeout(() => {
  console.log("Step 1");
  setTimeout(() => {
    console.log("Step 2");
    setTimeout(() => {
      console.log("Step 3");
    }, 1000);
  }, 1000);
}, 1000);
```

## 5 - Promises
A **Promise** represents a value that may be available now, in the future, or never.

### States of a Promise:
1. **Pending** – Initial state, waiting for resolution.
2. **Fulfilled** – The operation was successful.
3. **Rejected** – The operation failed.

### Creating a Promise:
```js
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("Data fetched");
  }, 2000);
});
```

### Handling a Promise:
```js
promise.then((data) => console.log(data)).catch((error) => console.log(error));
```

## 6 - `async` / `await`
`async` functions return a promise and allow `await` to pause execution until the promise resolves.

### Example:
```js
async function fetchData() {
  console.log("Fetching...");
  let data = await new Promise((resolve) => setTimeout(() => resolve("Data received"), 2000));
  console.log(data);
}
fetchData();
```

### Output:
```
Fetching...
(Data received after 2 seconds)
```

## 7 - Event Loop
The **Event Loop** is responsible for handling asynchronous operations in JavaScript, ensuring non-blocking execution.

### How It Works:
1. **Call Stack**: Holds synchronous code execution.
2. **Web APIs**: Handles async operations (`setTimeout`, `fetch`, etc.).
3. **Callback Queue**: Stores async callbacks after execution is complete.
4. **Microtask Queue**: Stores Promises and `async/await` callbacks (executed before callback queue).

### Example:
```js
console.log("Start");
setTimeout(() => console.log("Timeout"), 0);
Promise.resolve().then(() => console.log("Promise"));
console.log("End");
```

### Expected Output:
```
Start
End
Promise
Timeout
```

### Why?
- `Promise` (microtask) executes before `setTimeout` (callback queue).
- The Event Loop prioritizes microtasks over regular callbacks.

## Summary
| Concept | Description |
|---------|-------------|
| `setTimeout` | Runs a function after a delay |
| `setInterval` | Runs a function at regular intervals |
| Callbacks | Functions passed as arguments for async operations |
| Callback Hell | Nested callbacks causing readability issues |
| Promises | Asynchronous operations that can be pending, resolved, or rejected |
| `async/await` | Cleaner syntax for handling promises |
| Event Loop | Handles asynchronous operations and manages execution order |

Using Promises and `async/await` helps to write cleaner and more manageable asynchronous code while understanding the Event Loop ensures better performance optimizations.


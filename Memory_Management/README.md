# Memory Management in JavaScript

JavaScript handles memory management automatically using **garbage collection**, but understanding how memory allocation and deallocation work helps in writing efficient code.

## 1 - Memory Life Cycle
Memory in JavaScript follows a simple lifecycle:
1. **Allocation** - Memory is allocated when variables, objects, or functions are created.
2. **Usage** - The allocated memory is used for computations and data storage.
3. **Deallocation** - Unused memory is automatically freed by the garbage collector.

## 2 - Memory Allocation
### Primitive Types
Primitive values (e.g., numbers, strings, booleans) are stored in the **stack**.
```js
let num = 42; // Allocates memory for a number
let text = "Hello"; // Allocates memory for a string
```

### Objects and Functions
Objects and functions are stored in the **heap**, and references are kept in the stack.
```js
let obj = { name: "Alice" }; // Allocates memory in the heap
let arr = [1, 2, 3]; // Arrays are also stored in the heap
```

## 3 - Garbage Collection
JavaScript uses **automatic garbage collection** to remove unused objects.

### Reference Counting
An object is collected if no references point to it.
```js
let obj = { name: "Bob" };
obj = null; // The object becomes unreachable and is collected
```

### Mark-and-Sweep Algorithm
The garbage collector marks all reachable objects and removes the unmarked ones.
```js
function createUser() {
  let user = { name: "Charlie" };
}
createUser(); // After function execution, 'user' is no longer referenced
```

## 4 - Memory Leaks
Memory leaks occur when memory is allocated but never freed.

### Common Causes of Memory Leaks:
1. **Global Variables**
   ```js
   let globalVar = [];
   function addItem() {
     globalVar.push(new Array(1000000).fill("data"));
   }
   ```

2. **Uncleared Intervals & Timeouts**
   ```js
   let interval = setInterval(() => console.log("Running"), 1000);
   clearInterval(interval); // Always clear unused intervals
   ```

3. **Detached DOM Elements**
   ```js
   let elem = document.createElement("div");
   document.body.appendChild(elem);
   document.body.removeChild(elem);
   elem = null; // Explicitly remove references
   ```

## 5 - Best Practices for Memory Management
1. **Use `let` and `const` to limit scope**
2. **Manually nullify large objects** when no longer needed
3. **Avoid global variables**
4. **Clear intervals and timeouts**
5. **Use WeakMap and WeakSet** for temporary references
   ```js
   let cache = new WeakMap();
   let obj = {};
   cache.set(obj, "cachedValue");
   obj = null; // Memory automatically freed
   ```

## Summary
| Feature | Description |
|---------|-------------|
| Stack | Stores primitive values and references |
| Heap | Stores objects and functions |
| Garbage Collection | Automatic memory cleanup using mark-and-sweep |
| Memory Leaks | Occurs when memory is retained unnecessarily |
| Best Practices | Use proper scoping, nullify references, and clean up intervals |

Understand
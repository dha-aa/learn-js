# Data Structures in JavaScript

Data structures are fundamental in programming as they allow efficient data organization, storage, and manipulation. JavaScript provides built-in data structures to handle different types of data efficiently.

## 1 - Arrays
An **array** is an ordered collection of values.

### a) Creating an Array
```js
let numbers = [1, 2, 3, 4, 5];
let fruits = ["Apple", "Banana", "Cherry"];
```

### b) Accessing and Modifying Elements
```js
console.log(numbers[0]); // 1
numbers[1] = 10;
console.log(numbers); // [1, 10, 3, 4, 5]
```

### c) Common Array Methods
```js
numbers.push(6); // Adds 6 to the end
numbers.pop(); // Removes last element
numbers.shift(); // Removes first element
numbers.unshift(0); // Adds 0 to the beginning
console.log(numbers.length); // Array length
```

## 2 - Objects
An **object** is a collection of key-value pairs.

### a) Creating an Object
```js
let person = {
  name: "Alice",
  age: 30,
  isStudent: false
};
```

### b) Accessing and Modifying Properties
```js
console.log(person.name); // Alice
person.age = 31; // Modify value
person.city = "New York"; // Add new property
```

### c) Object Methods
```js
console.log(Object.keys(person)); // ["name", "age", "isStudent", "city"]
console.log(Object.values(person)); // ["Alice", 31, false, "New York"]
```

## 3 - Sets
A **Set** stores unique values.

### a) Creating and Using a Set
```js
let uniqueNumbers = new Set([1, 2, 3, 3, 4]);
uniqueNumbers.add(5);
uniqueNumbers.delete(2);
console.log(uniqueNumbers.has(3)); // true
console.log(uniqueNumbers.size); // 4
```

## 4 - WeakSets
A **WeakSet** is similar to a Set but only holds weak references to objects.

### a) Creating and Using a WeakSet
```js
let ws = new WeakSet();
let obj1 = { name: "Alice" };
let obj2 = { name: "Bob" };
ws.add(obj1);
ws.add(obj2);
console.log(ws.has(obj1)); // true
ws.delete(obj2);
```

## 5 - Maps
A **Map** is a key-value data structure where keys can be of any type.

### a) Creating and Using a Map
```js
let userRoles = new Map();
userRoles.set("Alice", "Admin");
userRoles.set("Bob", "Editor");
console.log(userRoles.get("Alice")); // Admin
console.log(userRoles.has("Bob")); // true
userRoles.delete("Bob");
```

## 6 - WeakMaps
A **WeakMap** is similar to a Map but only holds weak references to keys, which must be objects.

### a) Creating and Using a WeakMap
```js
let wm = new WeakMap();
let key1 = { id: 1 };
let key2 = { id: 2 };
wm.set(key1, "Value 1");
wm.set(key2, "Value 2");
console.log(wm.get(key1)); // "Value 1"
wm.delete(key2);
```

## 7 - Stacks (LIFO: Last In, First Out)
A **stack** follows LIFO (Last In, First Out) principle.

### a) Implementing a Stack Using an Array
```js
class Stack {
  constructor() {
    this.items = [];
  }
  push(element) {
    this.items.push(element);
  }
  pop() {
    return this.items.pop();
  }
  peek() {
    return this.items[this.items.length - 1];
  }
}
let stack = new Stack();
stack.push(10);
stack.push(20);
console.log(stack.pop()); // 20
```

## 8 - Queues (FIFO: First In, First Out)
A **queue** follows FIFO (First In, First Out) principle.

### a) Implementing a Queue Using an Array
```js
class Queue {
  constructor() {
    this.items = [];
  }
  enqueue(element) {
    this.items.push(element);
  }
  dequeue() {
    return this.items.shift();
  }
}
let queue = new Queue();
queue.enqueue("Task 1");
queue.enqueue("Task 2");
console.log(queue.dequeue()); // Task 1
```

## 9 - Linked Lists
A **linked list** consists of nodes, where each node contains data and a reference to the next node.

### a) Basic Singly Linked List Implementation
```js
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}
class LinkedList {
  constructor() {
    this.head = null;
  }
  append(value) {
    let newNode = new Node(value);
    if (!this.head) {
      this.head = newNode;
      return;
    }
    let current = this.head;
    while (current.next) {
      current = current.next;
    }
    current.next = newNode;
  }
}
let list = new LinkedList();
list.append(10);
list.append(20);
console.log(list.head.value); // 10
```

## Summary
- **Arrays**: Ordered lists, useful for collections.
- **Objects**: Key-value storage, best for structured data.
- **Sets**: Unique values, best for eliminating duplicates.
- **WeakSets**: Stores objects with weak references.
- **Maps**: Key-value pairs, allows keys of any type.
- **WeakMaps**: Key-value pairs with weak referenced keys.
- **Stacks**: LIFO structure, used for backtracking.
- **Queues**: FIFO structure, useful for task scheduling.
- **Linked Lists**: Efficient dynamic data structure for insertions/deletions.



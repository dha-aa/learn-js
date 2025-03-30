# Data Structures in JavaScript

Data structures are fundamental in programming as they allow efficient data organization, storage, and manipulation. JavaScript provides built-in data structures to handle different types of data efficiently.

## 1 - Indexed Collections
Indexed collections store elements in an ordered sequence where each element is assigned a numeric index.

### a) Arrays
An **array** is an ordered collection of values.

#### Creating an Array
```js
let numbers = [1, 2, 3, 4, 5];
let fruits = ["Apple", "Banana", "Cherry"];
```

#### Accessing and Modifying Elements
```js
console.log(numbers[0]); // 1
numbers[1] = 10;
console.log(numbers); // [1, 10, 3, 4, 5]
```

#### Common Array Methods
```js
numbers.push(6); // Adds 6 to the end
numbers.pop(); // Removes last element
numbers.shift(); // Removes first element
numbers.unshift(0); // Adds 0 to the beginning
console.log(numbers.length); // Array length
```

## 2 - Typed Arrays
Typed arrays provide an efficient way to work with binary data.
```js
let intArray = new Int32Array([10, 20, 30]);
console.log(intArray[1]); // 20
```

## 3 - Keyed Collections
Keyed collections store elements where each value is associated with a unique key.

### a) Objects
An **object** is a collection of key-value pairs.

#### Creating an Object
```js
let person = {
  name: "Alice",
  age: 30,
  isStudent: false
};
```

#### Accessing and Modifying Properties
```js
console.log(person.name); // Alice
person.age = 31; // Modify value
person.city = "New York"; // Add new property
```

#### Object Methods
```js
console.log(Object.keys(person)); // ["name", "age", "isStudent", "city"]
console.log(Object.values(person)); // ["Alice", 31, false, "New York"]
```

### b) Maps
A **Map** is a key-value data structure where keys can be of any type.
```js
let userRoles = new Map();
userRoles.set("Alice", "Admin");
userRoles.set("Bob", "Editor");
console.log(userRoles.get("Alice")); // Admin
```

### c) WeakMaps
A **WeakMap** is similar to a Map but only holds weak references to keys, which must be objects.
```js
let wm = new WeakMap();
let key1 = { id: 1 };
wm.set(key1, "Value 1");
console.log(wm.get(key1)); // "Value 1"
```

## 4 - Sets
A **Set** stores unique values.
```js
let uniqueNumbers = new Set([1, 2, 3, 3, 4]);
uniqueNumbers.add(5);
console.log(uniqueNumbers.has(3)); // true
```

## 5 - WeakSets
A **WeakSet** is similar to a Set but only holds weak references to objects.
```js
let ws = new WeakSet();
let obj1 = { name: "Alice" };
ws.add(obj1);
console.log(ws.has(obj1)); // true
```

## 6 - JSON (JavaScript Object Notation)
JSON is a lightweight data format used for data exchange.

### a) Converting an Object to JSON
```js
let data = { name: "Alice", age: 30 };
let jsonData = JSON.stringify(data);
console.log(jsonData); // "{"name":"Alice","age":30}"
```

### b) Parsing JSON into an Object
```js
let parsedData = JSON.parse(jsonData);
console.log(parsedData.name); // Alice
```

## 7 - Stacks (LIFO: Last In, First Out)
A **stack** follows LIFO (Last In, First Out) principle.
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
}
```

## 8 - Queues (FIFO: First In, First Out)
A **queue** follows FIFO (First In, First Out) principle.
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
```

## 9 - Linked Lists
A **linked list** consists of nodes, where each node contains data and a reference to the next node.
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
```

## Summary
- **Indexed Collections**: Arrays for ordered data.
- **Typed Arrays**: Efficient storage of binary data.
- **Keyed Collections**: Objects, Maps, and WeakMaps for key-value storage.
- **Sets & WeakSets**: Used for unique values with strong and weak references.
- **JSON**: Standardized format for data exchange.
- **Stacks & Queues**: LIFO and FIFO structures for efficient data handling.
- **Linked Lists**: Dynamic data structure for efficient insertions/deletions.


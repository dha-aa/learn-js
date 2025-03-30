# JavaScript Classes

JavaScript classes provide a way to define **blueprints** for creating objects with shared properties and methods. Classes were introduced in ES6 as syntactic sugar over JavaScript's prototype-based inheritance.

## 1 - Defining a Class
A class is defined using the `class` keyword.

### Syntax:
```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}
```

## 2 - Creating an Instance
To create an object from a class, use the `new` keyword.

### Example:
```js
const person1 = new Person("Alice", 25);
console.log(person1.name); // Alice
console.log(person1.age); // 25
```

## 3 - Class Methods
Methods are functions inside a class.

### Example:
```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  greet() {
    return `Hello, my name is ${this.name}.`;
  }
}

const person1 = new Person("Alice", 25);
console.log(person1.greet()); // Hello, my name is Alice.
```

## 4 - Static Methods
Static methods belong to the class itself, not instances.

### Example:
```js
class MathUtil {
  static add(a, b) {
    return a + b;
  }
}

console.log(MathUtil.add(5, 3)); // 8
```

## 5 - Getters and Setters
Getters and setters allow controlled access to properties.

### Example:
```js
class Person {
  constructor(name) {
    this._name = name;
  }
  get name() {
    return this._name;
  }
  set name(newName) {
    this._name = newName;
  }
}

const person1 = new Person("Alice");
console.log(person1.name); // Alice
person1.name = "Bob";
console.log(person1.name); // Bob
```

## 6 - Inheritance
Classes can **inherit** properties and methods from other classes using `extends`.

### Example:
```js
class Animal {
  constructor(name) {
    this.name = name;
  }
  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  speak() {
    console.log(`${this.name} barks.`);
  }
}

const dog1 = new Dog("Buddy");
dog1.speak(); // Buddy barks.
```

## 7 - Super Keyword
The `super` keyword calls the constructor or methods from the parent class.

### Example:
```js
class Animal {
  constructor(name) {
    this.name = name;
  }
  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name); // Calls Animal constructor
    this.breed = breed;
  }
}

const dog1 = new Dog("Buddy", "Labrador");
console.log(dog1.name); // Buddy
console.log(dog1.breed); // Labrador
```

## 8 - Private Fields
Private fields are declared with `#` and cannot be accessed outside the class.

### Example:
```js
class BankAccount {
  #balance;
  constructor(initialBalance) {
    this.#balance = initialBalance;
  }
  getBalance() {
    return this.#balance;
  }
}

const account = new BankAccount(1000);
console.log(account.getBalance()); // 1000
// console.log(account.#balance); // SyntaxError
```

## Summary
| Feature | Description |
|---------|-------------|
| Classes | Define object blueprints |
| Constructor | Initializes object properties |
| Methods | Define behavior inside a class |
| Static Methods | Belong to the class, not instances |
| Getters/Setters | Control access to properties |
| Inheritance | Allows a class to derive from another |
| `super` | Calls the parent class constructor or methods |
| Private Fields | Encapsulated properties, inaccessible outside |

JavaScript classes provide a powerful and structured way to manage object-oriented programming in modern development.


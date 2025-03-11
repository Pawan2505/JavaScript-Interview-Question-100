## **Classes in JavaScript**  

A **class** in JavaScript is a blueprint for creating objects. It provides a structured way to define properties and methods that multiple objects can share.  

---

## **1️⃣ Creating a Class**
JavaScript classes are created using the **`class`** keyword.  

🔹 **Example: Defining a Simple Class**  
```js
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    greet() {
        console.log(`Hello, my name is ${this.name}`);
    }
}

const person1 = new Person("Alice", 25);
person1.greet(); // Output: Hello, my name is Alice
```
✔ The `constructor` method initializes object properties.  
✔ The `greet()` method is shared among all instances.  

---

## **2️⃣ Class Inheritance (Extending a Class)**
Classes can inherit properties and methods from another class using **`extends`**.

🔹 **Example: Creating a Subclass (`Student` inherits from `Person`)**
```js
class Student extends Person {
    constructor(name, age, grade) {
        super(name, age); // Calls the parent class constructor
        this.grade = grade;
    }

    study() {
        console.log(`${this.name} is studying in grade ${this.grade}`);
    }
}

const student1 = new Student("Bob", 20, "12th");
student1.greet();  // Inherited from Person: Output: Hello, my name is Bob
student1.study();  // Output: Bob is studying in grade 12th
```
✔ `super(name, age)` calls the parent constructor.  
✔ The `Student` class adds an extra property (`grade`) and a method (`study()`).  

---

## **3️⃣ Getters & Setters in Classes**
Getters (`get`) and setters (`set`) allow controlled access to object properties.

🔹 **Example: Using Getters and Setters**  
```js
class Car {
    constructor(brand) {
        this._brand = brand; // Using _brand to avoid naming conflict
    }

    get brand() {
        return this._brand.toUpperCase(); // Modify output
    }

    set brand(newBrand) {
        this._brand = newBrand;
    }
}

const car1 = new Car("Toyota");
console.log(car1.brand); // Output: TOYOTA
car1.brand = "Honda";
console.log(car1.brand); // Output: HONDA
```
✔ `get` allows accessing properties with custom logic.  
✔ `set` enables controlled updates to properties.  

---

## **4️⃣ Static Methods (Class-level Methods)**
Static methods **belong to the class itself** rather than an instance.

🔹 **Example: Using a Static Method**  
```js
class MathUtils {
    static add(a, b) {
        return a + b;
    }
}

console.log(MathUtils.add(5, 3)); // Output: 8
```
✔ `static` methods **cannot** be called on instances, only on the class itself.  

---

## **5️⃣ Private Fields & Methods (`#`) (ES6 Feature)**
Private fields/methods **cannot be accessed outside the class**.

🔹 **Example: Private Property & Method**  
```js
class BankAccount {
    #balance = 1000; // Private variable

    #calculateInterest() { // Private method
        return this.#balance * 0.05;
    }

    showBalance() {
        console.log(`Balance: $${this.#balance}`);
    }
}

const account = new BankAccount();
account.showBalance(); // Output: Balance: $1000
console.log(account.#balance); // ❌ SyntaxError (Private field)
```
✔ Private members **start with `#`** and cannot be accessed from outside the class.  

---

## **Key Takeaways**
| Feature | Description |
|---------|-------------|
| **`class`** | Defines a blueprint for objects |
| **`constructor`** | Initializes object properties |
| **`extends`** | Enables class inheritance |
| **`super()`** | Calls the parent class constructor |
| **Getters & Setters** | Encapsulate property access |
| **Static Methods** | Methods that belong to the class itself |
| **Private Fields (`#`)** | Restricts access to class-only |

---

## **When to Use Classes?**
✔ When working with **Object-Oriented Programming (OOP)**  
✔ When **creating multiple objects with shared methods**  
✔ When implementing **inheritance**  
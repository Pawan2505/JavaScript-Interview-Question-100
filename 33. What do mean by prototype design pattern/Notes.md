### **Prototype Design Pattern in JavaScript**  

The **Prototype Design Pattern** is a creational design pattern that allows you to **clone** an existing object **instead of creating a new one from scratch**. This helps improve performance, especially when object creation is expensive.  

---

### **How It Works**  
1️⃣ **Create an object as a prototype**  
2️⃣ **Use it as a blueprint to create new objects**  
3️⃣ **Modify or extend the cloned objects if needed**  

---

### **Prototype Pattern in JavaScript**  

JavaScript natively supports the **prototype-based inheritance**, making it a great fit for this pattern.  

#### **Example: Using Object Prototype**
```js
const carPrototype = {
    start() {
        console.log(`${this.brand} is starting...`);
    }
};

// Creating a new object using Object.create()
const car1 = Object.create(carPrototype);
car1.brand = "Tesla"; 

car1.start(); // Output: Tesla is starting...
```
🔹 **Here, `car1` inherits methods from `carPrototype` without duplicating code.**  

---

### **Example: Using Constructor Function & Prototype**
```js
function Person(name, age) {
    this.name = name;
    this.age = age;
}

// Adding a method to the prototype
Person.prototype.greet = function() {
    console.log(`Hello, my name is ${this.name}`);
};

// Creating objects
const person1 = new Person("Alice", 25);
const person2 = new Person("Bob", 30);

person1.greet(); // Output: Hello, my name is Alice
person2.greet(); // Output: Hello, my name is Bob
```
🔹 **Here, `greet()` is stored in the prototype instead of being copied to each object.**  

---

### **Advantages of Prototype Design Pattern**  
✅ **Memory Efficient** – Methods are shared rather than duplicated  
✅ **Performance Boost** – Object creation is faster than recreating from scratch  
✅ **Flexible** – Objects can be extended dynamically  
✅ **Easy to Implement** – JavaScript's built-in support makes it straightforward to use
### **Disadvantages of Prototype Design Pattern**

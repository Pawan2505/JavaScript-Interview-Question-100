### **Constructor Function in JavaScript**  

A **constructor function** in JavaScript is used to create multiple objects with the same properties and methods. It acts as a blueprint for creating instances of an object.

---

### **How to Define a Constructor Function?**
1. The function name starts with an uppercase letter (by convention).
2. The `this` keyword assigns properties to the object being created.
3. The `new` keyword is used to create new instances.

---

### **Example: Creating a `Person` Constructor Function**
```javascript
function Person(name, age) {
    this.name = name;
    this.age = age;

    this.greet = function () {
        console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    };
}

// Creating instances
const person1 = new Person("Alice", 25);
const person2 = new Person("Bob", 30);

person1.greet(); // Output: Hello, my name is Alice and I am 25 years old.
person2.greet(); // Output: Hello, my name is Bob and I am 30 years old.
```

---

### **Key Points About Constructor Functions**
✔ **Used for creating multiple objects with the same structure.**  
✔ **Uses `this` to assign values to object properties.**  
✔ **Requires the `new` keyword to create an instance.**  

---

### **Adding Methods to the Prototype**
Instead of defining methods inside the constructor (which duplicates them for every instance), we can add them to the prototype:

```javascript
function Person(name, age) {
    this.name = name;
    this.age = age;
}

// Adding a method to the prototype
Person.prototype.greet = function () {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
};

const person3 = new Person("Charlie", 35);
person3.greet(); // Output: Hello, my name is Charlie and I am 35 years old.
```

---

### **Advantages of Constructor Functions**
✅ **Memory Efficient** – Methods in the prototype are shared across instances.  
✅ **Reusable Code** – Avoids repetition by using a single constructor.  
✅ **Encapsulation** – Groups related data and behavior in one place.  

---

### **Difference Between Constructor Functions & Classes**
- Constructor functions are an older way to create objects.
- ES6 introduced **classes**, which provide a cleaner and more structured way to define object templates.

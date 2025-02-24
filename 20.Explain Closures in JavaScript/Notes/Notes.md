### **20: Explain Closures in JavaScript.**

#### **Answer:**

A **Closure** in JavaScript is a function that **remembers** and **accesses** its **lexical scope** (the scope in which it was created), even when the function is executed outside that scope.

In simple terms, a closure is created whenever a function is defined inside another function and it **has access to the outer function's variables**.

---

### **How Closures Work:**

A closure allows a function to maintain access to its **outer function's variables** even after the outer function has finished executing.

This is possible because JavaScript functions **remember** the environment (or scope) in which they were created. So even if the outer function finishes execution, the inner function can still access the variables from the outer function's scope.

---

### **Example of a Closure:**

```javascript
function outerFunction() {
  let outerVar = "I am from the outer function";  // Variable in outer function

  function innerFunction() {
    console.log(outerVar);  // Inner function has access to outerVar
  }

  return innerFunction;  // Returning the inner function
}

const closureFunction = outerFunction();  // outerFunction is executed
closureFunction();  // "I am from the outer function" is logged
```

**Explanation:**
- In this example, `outerFunction()` defines a variable `outerVar` and also defines an inner function `innerFunction()`.
- When `outerFunction()` is called, it returns `innerFunction()`, but `innerFunction()` still has access to `outerVar` even after `outerFunction()` has finished executing.
- This is because of the closure—`innerFunction()` "remembers" the **lexical scope** of `outerFunction()`, including `outerVar`, and can still access it when called later.

---

### **Key Characteristics of Closures:**

1. **Access to Outer Function's Variables:**
   - Closures allow inner functions to access variables from their outer functions even after the outer function has finished executing.
   
2. **Data Encapsulation:**
   - Closures help in **data hiding** and **encapsulation**. By using closures, you can create private variables that can’t be directly accessed from outside the function.
   
3. **Preserved State:**
   - A closure "remembers" the environment in which it was created, including the values of the outer function’s variables.

---

### **Practical Use of Closures:**

#### **1. Data Encapsulation / Private Variables:**

You can use closures to **simulate private variables**. A variable inside a closure can be kept hidden from the outside world, and only the functions inside the closure can access and modify it.

```javascript
function counter() {
  let count = 0;  // private variable
  
  return {
    increment: function() {
      count++;
      console.log(count);
    },
    decrement: function() {
      count--;
      console.log(count);
    },
    getCount: function() {
      return count;
    }
  };
}

const myCounter = counter();
myCounter.increment();  // Output: 1
myCounter.increment();  // Output: 2
myCounter.decrement();  // Output: 1
console.log(myCounter.getCount());  // Output: 1
```

**Explanation:**
- The `count` variable is private and cannot be accessed directly from outside the `counter` function.
- The `increment()`, `decrement()`, and `getCount()` methods, which are closures, can access and modify the private `count` variable.

---

#### **2. Function Factories:**

Closures can be used to create **custom functions** that are dynamically generated based on certain arguments.

```javascript
function multiplyBy(factor) {
  return function(number) {
    return number * factor;  // Inner function uses 'factor' from outer function
  };
}

const multiplyBy2 = multiplyBy(2);
const multiplyBy5 = multiplyBy(5);

console.log(multiplyBy2(10));  // Output: 20
console.log(multiplyBy5(10));  // Output: 50
```

**Explanation:**
- `multiplyBy()` is a function that returns a new function.
- The returned function remembers the value of `factor` from the `multiplyBy()` call and uses it when invoked later.

---

### **Real-World Example with Closures:**

Imagine you want to create a simple event handler that remembers the context (data) related to a user, and executes code based on that data:

```javascript
function createUser(name) {
  return function greet() {
    console.log(`Hello, ${name}!`);  // Closure remembers the value of 'name'
  };
}

const user1 = createUser("Raj");
const user2 = createUser("Priya");

user1();  // Output: "Hello, Raj!"
user2();  // Output: "Hello, Priya!"
```

In this case, each `user1()` and `user2()` function call retains access to the `name` that was passed when the `createUser()` function was called. The closure "remembers" that `user1()` should greet "Raj" and `user2()` should greet "Priya."

---

### **Summary of Closures:**

| **Concept**            | **Explanation**                                                   |
|------------------------|-------------------------------------------------------------------|
| **Closure**            | A function that "remembers" its lexical scope, even after the outer function has finished executing. |
| **Lexical Scoping**    | Functions in JavaScript are lexically scoped, meaning they have access to variables in their own scope and outer scopes. |
| **Data Encapsulation** | Closures allow you to create private variables and methods that can't be accessed from outside the closure. |
| **Preserved State**    | Closures preserve the state of variables from their outer function, allowing them to maintain their environment even after the outer function finishes. |

---

### **Why Closures Are Important:**
- **Data encapsulation** and the creation of **private variables**.
- **Preserving state** over time.
- Useful for things like **event handlers**, **callback functions**, and **function factories**.

---

### **Note:**

Closures are a powerful feature of JavaScript. They allow inner functions to access variables from their outer functions even after the outer function has finished executing. This leads to a better organization of code, allows for data encapsulation, and enables more complex behaviors like **function factories** and **private variables**.

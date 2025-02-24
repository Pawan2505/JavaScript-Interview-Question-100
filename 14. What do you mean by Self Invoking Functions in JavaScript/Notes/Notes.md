### **14: What do you mean by Self Invoking Functions in JavaScript?**

#### **Answer:**

A **Self Invoking Function** (also known as an **Immediately Invoked Function Expression** or **IIFE**) is a function that is **defined and executed immediately** after its creation, without needing to be explicitly called.

In JavaScript, a function is normally executed by calling it using its name. But in the case of a Self Invoking Function, the function is called **automatically** as soon as it is defined.

This is useful in cases where we want to create a function with its own scope without polluting the global scope.

---

#### **Syntax of Self Invoking Functions:**

The syntax of a self-invoking function is a **function expression** wrapped in parentheses, followed by `()` to invoke it immediately.

```javascript
(function() {
  // Code here will run immediately
})();
```

Or using an arrow function:

```javascript
(() => {
  // Code here will run immediately
})();
```

---

#### **Example with Indian Context:**

Let's take an example with an Indian name:

```javascript
(function() {
  const name = "Ananya";
  console.log("Hello, " + name);  // This will print "Hello, Ananya"
})();
```

In this example, the function is executed immediately after being defined. The `name` variable is scoped to this function and cannot be accessed outside of it.

---

#### **Why Use Self Invoking Functions?**

1. **Avoid Polluting the Global Scope:** When writing code in JavaScript, variables and functions are added to the global scope by default. This can cause conflicts if multiple scripts are running on the same page. A Self Invoking Function helps to **create a local scope**, avoiding global variable conflicts.

   Example:
   ```javascript
   (function() {
     var localVar = "I am inside the function!";
     console.log(localVar);  // Works fine here
   })();
   
   console.log(localVar);  // Error: localVar is not defined outside the function
   ```

2. **Encapsulation:** It allows you to encapsulate code that should not be accessed from the outside, keeping your code neat and organized. This is commonly used in **modular programming**.

3. **Initialization of Code:** It’s often used to execute setup code that doesn’t need to be repeated or called later.

---

#### **Example of IIFE with Arguments:**

You can also pass parameters to Self Invoking Functions.

```javascript
(function(name) {
  console.log("Welcome, " + name);  // This will print "Welcome, Raj"
})("Raj");
```

In this case, `"Raj"` is passed to the function, and it prints `"Welcome, Raj"` immediately.

---

#### **Note:**

- A **Self Invoking Function** is a function that is executed immediately after being defined.
- It’s written as a function expression and is enclosed in parentheses, followed by `()` to invoke it immediately.
- It helps **avoid polluting the global scope** and allows for **encapsulation**.
- It's commonly used for **initialization tasks** or when you want to create isolated variables.

---
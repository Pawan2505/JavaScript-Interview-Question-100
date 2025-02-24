### 2. Explain Hoisting in JavaScript


# Hoisting in JavaScript

**Hoisting** is a behavior in JavaScript where **variables** and **functions** are moved to the top of their scope (either global or local) during the compilation phase, even before the code is executed. 

Here’s how hoisting works:

1. **Variables declared with `var`**: 
   - They are moved (hoisted) to the top of the scope. However, they are only **initialized with `undefined`**, not with their assigned value.
   
   Example:
   ```javascript
   console.log(x); // undefined
   var x = 5;
   console.log(x); // 5
   ```

2. **Function declarations**: 
   - They are hoisted with their actual **function body**, so they can be called before they are written in the code.
   
   Example:
   ```javascript
   greet(); // "Hello"
   function greet() {
       console.log("Hello");
   }
   ```

3. **`let` and `const` variables**: 
   - These are hoisted, but **they do not get initialized** until the code reaches their declaration line. This is called the **Temporal Dead Zone (TDZ)**. Trying to use them before declaration will throw an error.
   
   Example:
   ```javascript
   console.log(a); // ReferenceError: Cannot access 'a' before initialization
   let a = 5;
   ```

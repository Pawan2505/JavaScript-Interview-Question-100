### 10. **What is an Immediately Invoked Function in JavaScript?**


# Immediately Invoked Function Expression (IIFE) in JavaScript

An **Immediately Invoked Function Expression** (IIFE) is a function that is defined and executed immediately after its creation. It allows you to execute a function as soon as it is defined without having to call it explicitly later.

### Syntax:
The basic syntax of an IIFE is:
```javascript
(function() {
    // code to be executed
})();
```

### Explanation:
1. **Function Expression**: The function is written as an **expression**, meaning it is wrapped inside parentheses `()` to treat it as an expression rather than a declaration.
2. **Immediate Invocation**: The `()` at the end of the function expression immediately calls the function as soon as it is defined.

### Example:
```javascript
(function() {
    console.log("This function runs immediately!");
})();
```
Output:
```
This function runs immediately!
```

### Why Use IIFE?
1. **Avoid polluting global scope**: Variables inside an IIFE are **not** accessible from outside, which helps avoid accidental variable name conflicts in the global scope.
   
2. **Private variables**: You can create private variables inside the function, ensuring they aren't accessible from the outside.

   Example:
   ```javascript
   (function() {
       var privateVariable = "This is private";
       console.log(privateVariable); // "This is private"
   })();
   
   console.log(privateVariable); // Error: privateVariable is not defined
   ```

3. **Module Pattern**: IIFE is often used in JavaScript for creating modules or encapsulating code, especially in older versions of JavaScript before `ES6` modules were introduced.

### Note:
An IIFE is a function that is defined and immediately invoked, useful for creating private variables and keeping code isolated from the global scope.

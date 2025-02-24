

### **11: What do you mean by strict mode in JavaScript and what are the characteristics of JavaScript strict mode?**

#### **Answer:**

**Strict Mode in JavaScript:**
Strict mode is a special way to write JavaScript code that helps you avoid common mistakes and bugs. It makes JavaScript behave in a stricter way by preventing certain actions that are considered unsafe or problematic.

You can enable strict mode by adding `"use strict";` at the beginning of your JavaScript file or inside a function.

For example:
```javascript
"use strict"; // Enable strict mode
var x = 10;   // Normal variable declaration
```

Or inside a function:
```javascript
function myFunction() {
  "use strict";  // Strict mode inside a function
  var y = 20;    // Normal variable declaration
}
```

---

#### **Characteristics of Strict Mode:**

1. **Catches Common Mistakes:**
   - Normally, JavaScript might silently ignore errors, like trying to use an undeclared variable. But in strict mode, it will throw an error instead.
   ```javascript
   "use strict";
   x = 10; // Error: x is not defined
   ```

2. **Prevents Accidental Global Variables:**
   - In strict mode, variables must be declared with `var`, `let`, or `const`. If you forget to declare a variable, it will throw an error, avoiding the creation of unintended global variables.

3. **Improves the Behavior of `this`:**
   - In normal JavaScript, if you use `this` in a function without it pointing to any object, it can be `undefined` or point to the global object. Strict mode makes sure that `this` is always `undefined` in such cases.
   ```javascript
   "use strict";
   function test() {
     console.log(this);  // `this` will be undefined, not the global object
   }
   test();
   ```

4. **Prevents Deleting Certain Variables or Functions:**
   - You can't delete variables or functions in strict mode. This helps to avoid mistakes when trying to remove things that should not be deleted.
   ```javascript
   "use strict";
   var x = 10;
   delete x; // Error: Cannot delete a variable
   ```

5. **Disallows Duplicate Property Names:**
   - Strict mode won’t allow you to define an object with the same property name twice.
   ```javascript
   "use strict";
   var obj = { a: 1, a: 2 }; // Error: Duplicate property names are not allowed
   ```

6. **Disallows `with` Statement:**
   - The `with` statement is not allowed in strict mode because it can make code harder to understand.
   ```javascript
   "use strict";
   with (obj) { // Error: `with` statement is not allowed
     console.log(a);
   }
   ```

---

#### **Why Use Strict Mode?**
- **Helps Avoid Mistakes:** It makes it easier to spot errors early by being more strict about how you write code.
- **Makes Code Safer:** It prevents certain actions that could lead to bugs or security issues.
- **Cleaner Code:** It encourages better coding practices and makes your code easier to understand and maintain.

In short, strict mode is a way of writing JavaScript that helps you write better, safer code by catching potential problems early!

---


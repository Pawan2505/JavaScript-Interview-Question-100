### 5. **Difference between `var` and `let` keyword in JavaScript.**

# Difference Between `var` and `let` Keyword in JavaScript

Both **`var`** and **`let`** are used to declare variables, but they have key differences in scope, hoisting, and reassignment:

1. **`var`**:
   - **Scope**: Function-scoped (if declared inside a function) or globally scoped (if declared outside a function).
   - **Hoisting**: Variables declared with `var` are hoisted to the top of their scope, but they are initialized with `undefined`.
   - **Re-declaration**: Can be re-declared in the same scope without any errors.
   
   **Example**:
   ```javascript
   var x = 10;
   if (true) {
       var x = 20; // re-declared
   }
   console.log(x); // 20
   ```

2. **`let`**:
   - **Scope**: Block-scoped, meaning the variable is limited to the block (enclosed by `{}`) in which it is defined.
   - **Hoisting**: `let` is hoisted but not initialized. It remains in the "temporal dead zone" until the code reaches the declaration.
   - **Re-declaration**: Cannot be re-declared in the same scope.
   
   **Example**:
   ```javascript
   let y = 30;
   if (true) {
       let y = 40; // different block scope
       console.log(y); // 40
   }
   console.log(y); // 30
   ```

### Note:
- Use **`let`** for block-scoped variables and avoid redeclaration issues.
- **`var`** is generally avoided due to its function-scoping and hoisting behavior, which can lead to bugs in larger codebases.





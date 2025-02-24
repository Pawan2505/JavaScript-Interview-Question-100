### 6. **Explain Implicit Type Coercion in JavaScript.**


# Implicit Type Coercion in JavaScript

**Implicit Type Coercion** is a process where JavaScript automatically converts one data type to another during runtime when necessary.

For example, when you try to perform operations between different data types, JavaScript will automatically convert the types to make them compatible.

### Examples:

1. **String and Number Addition:**
   ```javascript
   let result = "5" + 3; 
   console.log(result); // "53" (string)
   ```
   In this case, JavaScript converts the number `3` to a string and performs string concatenation.

2. **String and Number Subtraction:**
   ```javascript
   let result = "5" - 3; 
   console.log(result); // 2 (number)
   ```
   Here, JavaScript converts the string `"5"` to a number and performs the subtraction.

3. **Boolean and Number:**
   ```javascript
   let result = true + 5;
   console.log(result); // 6 (number)
   ```          
   JavaScript converts `true` to `1` and adds it to `5`.

### Note:
Implicit type coercion is done automatically by JavaScript when you mix different data types in operations, making it important to be aware of when writing code.

1.0/87

   
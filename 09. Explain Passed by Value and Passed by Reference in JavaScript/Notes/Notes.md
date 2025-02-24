### 9. **Explain Passed by Value and Passed by Reference in JavaScript.**


# Passed by Value and Passed by Reference in JavaScript

In JavaScript, when you pass data to a function, it can either be passed **by value** or **by reference**. These terms describe how data is passed to the function and how changes made inside the function affect the original data.

### 1. **Passed by Value**:
   - **Definition**: When a variable is passed by value, the function gets a **copy** of the original data. Any changes made to this copy inside the function will not affect the original variable outside the function.
   - **Used with**: **Primitive data types** like `number`, `string`, `boolean`, `undefined`, `null`, `symbol`, and `BigInt`.
   
   **Example**:
   ```javascript
   function changeValue(x) {
       x = 10;
   }

   let num = 5;
   changeValue(num);
   console.log(num);  // Output: 5 (original value is not changed)
   ```

### 2. **Passed by Reference**:
   - **Definition**: When a variable is passed by reference, the function gets a reference (or pointer) to the original data, not a copy. This means any changes made inside the function will **affect the original data**.
   - **Used with**: **Non-primitive data types** like `objects`, `arrays`, and `functions`.
   
   **Example**:
   ```javascript
   function changeValue(arr) {
       arr.push(4);
   }

   let numbers = [1, 2, 3];
   changeValue(numbers);
   console.log(numbers);  // Output: [1, 2, 3, 4] (original array is changed)
   ```

### Key Differences:
1. **Primitive types** (like `number`, `string`, `boolean`) are passed by value, meaning changes inside the function won't affect the original variable.
2. **Objects and arrays** are passed by reference, meaning changes inside the function **will** affect the original object or array.

### Note:
- **Passed by value** creates a copy of the data, while **passed by reference** creates a link to the original data, and changes to the reference affect the original object or array.

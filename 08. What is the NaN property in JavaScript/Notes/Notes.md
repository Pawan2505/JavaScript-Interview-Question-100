### 8. **What is the NaN property in JavaScript?**

# NaN in JavaScript

**NaN** stands for **Not-a-Number** and is a special value in JavaScript that represents an invalid or unrepresentable number.

### Key Points about NaN:
1. **NaN is a value**: It is a property of the global object and represents the result of an invalid mathematical operation. For example, dividing zero by zero or trying to convert a non-numeric value to a number.

   Example:
   ```javascript
   let result = 0 / 0;  // NaN
   console.log(result);  // Output: NaN
   ```

2. **NaN is of type number**: Despite being a value that means "Not a Number," its type is actually `number`.

   Example:
   ```javascript
   console.log(typeof NaN);  // "number"
   ```

3. **NaN is not equal to anything, even itself**: One unique thing about NaN is that it is not equal to any value, including itself. This means that `NaN === NaN` is false.

   Example:
   ```javascript
   console.log(NaN === NaN);  // Output: false
   ```

4. **Checking if a value is NaN**: You cannot directly use `==` or `===` to check if a value is NaN. Instead, you can use the `isNaN()` function or `Number.isNaN()` to check for NaN.

   Example:
   ```javascript
   console.log(isNaN(NaN));  // true
   console.log(Number.isNaN(NaN));  // true
   ```

### Note:
NaN is a special value in JavaScript that represents an invalid number or mathematical operation, and it behaves uniquely when compared to other values.
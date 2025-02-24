### 3. **Why do we use the word “debugger” in JavaScript?**


# The "debugger" Statement in JavaScript

The **`debugger`** statement in JavaScript is used to stop the execution of the code and invoke the debugging process in the browser.

- **Purpose**: It pauses the execution of JavaScript at that point, allowing the developer to inspect variable values, the call stack, and other details during runtime.
- It works like a breakpoint in the browser’s developer tools.

### Example:
```javascript
function test() {
   let a = 10;
   debugger; // Execution will stop here
   let b = 20;
   console.log(a + b);
}
test();

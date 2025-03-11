1. What are the types of errors in javascript?

JavaScript errors can be categorized into several types based on their nature and how they occur. Here are the main types:

1. Syntax Errors
Occur when JavaScript code is not written correctly.

Example:
console.log("Hello World" // Missing closing parenthesis

2. Reference Errors
Happen when trying to access a variable or function that doesn't exist.

Example:
console.log(myVar); // myVar is not defined

3. Type Errors
Occur when a value is not of the expected type.

Example:
let num = 10;
num.toUpperCase(); // Error: num is a number, not a string

4. Range Errors
Occur when a value is outside the allowed range.

Example:
let arr = new Array(-5); // Error: Array size cannot be negative

5. Eval Errors (Rare in modern JavaScript)
Related to the eval() function (which is discouraged).
Example:


eval("alert('Hello)"); // Missing closing quote -->
 6. URI Errors
Occur when using encodeURI() or decodeURI() incorrectly.
Example:


decodeURIComponent("%"); // Invalid URI character
These errors can be handled using try...catch to prevent crashes.
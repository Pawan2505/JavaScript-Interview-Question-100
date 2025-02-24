### 1. What are the different data types present in JavaScript?


# Different Data Types in JavaScript

JavaScript has 8 basic data types:

1. **Primitive Data Types:**
    - **String**: Used to represent textual data. E.g., `"Hello World"`.
    - **Number**: Used to represent both integer and floating point numbers. E.g., `25`, `3.14`.
    - **BigInt**: Represents large integers that are beyond the limit of the Number type. E.g., `1234567890123456789012345678901234567890n`.
    - **Boolean**: Represents a value of either `true` or `false`. E.g., `true`, `false`.
    - **undefined**: Represents a variable that has not been assigned a value. E.g., `let x; console.log(x); // undefined`.
    - **Symbol**: Represents a unique and immutable value often used as object property identifiers. E.g., `let sym = Symbol('description');`.
    - **null**: Represents the intentional absence of any object value. E.g., `let x = null;`.
  
2. **Non-Primitive (Reference) Data Type:**
    - **Object**: Used to store collections of data and more complex entities. E.g., `let person = { name: "John", age: 30 };`.

Each of these data types has unique characteristics and behavior in JavaScript.

In JavaScript, you can retrieve a character from a string at a specific index using the following methods:

### **1. `charAt(index)` Method**  
The `charAt()` method returns the character at a specified index in a string.

#### **Example:**
```js
let text = "Hello";
console.log(text.charAt(1)); // Output: "e"
```

---

### **2. Bracket Notation (`[]`)**  
You can also access characters using bracket notation, similar to an array.

#### **Example:**
```js
let text = "Hello";
console.log(text[1]); // Output: "e"
```

🔹 **Note:** Unlike `charAt()`, if the index is out of range, `charAt()` returns an empty string (`""`), while bracket notation returns `undefined`.

---

### **Which One Should You Use?**  
✅ `charAt(index)` – More explicit and safer (returns an empty string if index is out of range).  
✅ Bracket notation – Shorter and more commonly used.
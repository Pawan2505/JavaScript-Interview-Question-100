### **What is DOM in JavaScript?**  

The **DOM (Document Object Model)** is a programming interface that allows JavaScript to interact with and modify HTML and CSS. It represents the structure of a web page as a **tree-like hierarchy of objects**, where each element (like `<div>`, `<p>`, `<button>`) is a node in the tree.

---

### **Why is the DOM Important?**  
✔ **Allows JavaScript to access and modify web pages dynamically**  
✔ **Enables interaction (clicks, input fields, animations, etc.)**  
✔ **Used for building interactive websites**  

---

### **Example of DOM Structure (Tree Representation)**  

For this HTML:
```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Page</title>
  </head>
  <body>
    <h1>Hello, World!</h1>
    <button>Click Me</button>
  </body>
</html>
```
The DOM represents it as:
```
Document
│
├── <html>
│   ├── <head>
│   │   └── <title>My Page</title>
│   ├── <body>
│   │   ├── <h1>Hello, World!</h1>
│   │   └── <button>Click Me</button>
```

---

### **How to Use JavaScript to Manipulate the DOM**  

#### **1. Selecting Elements**
```js
const heading = document.querySelector("h1"); // Selects the <h1> element
console.log(heading.innerText); // Outputs: Hello, World!
```

#### **2. Changing Content**
```js
heading.innerText = "Welcome to JavaScript!"; // Updates the text
```

#### **3. Changing Styles**
```js
heading.style.color = "blue"; // Changes the text color to blue
```

#### **4. Handling Events**
```js
const button = document.querySelector("button");
button.addEventListener("click", function () {
    alert("Button was clicked!");
});
```

---

### **Key Points About the DOM**  
✅ **Represents an HTML page as a tree**  
✅ **Allows JavaScript to manipulate web pages dynamically**  
✅ **Used for event handling, styling, and animations**  

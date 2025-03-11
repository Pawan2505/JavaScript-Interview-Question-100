### **What is DOM in JavaScript?**  

**DOM (Document Object Model)** is a programming interface that represents an HTML or XML document as a **tree structure** where each element is a node. JavaScript can manipulate the DOM to dynamically change the content, structure, and style of a web page.

---

### **How the DOM Works**  
When a web page is loaded, the browser parses the HTML and creates a tree-like representation called the **DOM Tree**. JavaScript can then access and modify this tree using the DOM API.

---

### **Types of Nodes in DOM**  
1. **Document Node** – Represents the entire HTML document. (`document`)  
2. **Element Nodes** – Represent HTML elements. (`<div>, <p>, <button>`, etc.)  
3. **Text Nodes** – Represent the text inside elements.  
4. **Attribute Nodes** – Represent attributes of elements. (`id, class, src`, etc.)  
5. **Comment Nodes** – Represent comments (`<!-- This is a comment -->`).  

---

### **Selecting DOM Elements in JavaScript**
JavaScript provides various methods to select and manipulate elements:

#### **1. Select by ID**
```javascript
let heading = document.getElementById("title");
console.log(heading.innerText); // Gets the text inside the element
```

#### **2. Select by Class Name**
```javascript
let items = document.getElementsByClassName("list-item");
console.log(items[0]); // Access first element with the class
```

#### **3. Select by Tag Name**
```javascript
let paragraphs = document.getElementsByTagName("p");
console.log(paragraphs.length); // Number of <p> elements
```

#### **4. Select using `querySelector()` (Recommended)**
```javascript
let firstItem = document.querySelector(".list-item"); // Selects first matching element
let allItems = document.querySelectorAll(".list-item"); // Selects all matching elements
```

---

### **Manipulating the DOM**
Once elements are selected, JavaScript can modify them.

#### **1. Change Content**
```javascript
document.getElementById("title").innerText = "Updated Title!";
```

#### **2. Change Style**
```javascript
document.getElementById("title").style.color = "red";
```

#### **3. Add a New Element**
```javascript
let newParagraph = document.createElement("p");
newParagraph.innerText = "This is a new paragraph.";
document.body.appendChild(newParagraph);
```

#### **4. Remove an Element**
```javascript
let element = document.getElementById("title");
element.remove();
```

---

### **Events in DOM**
JavaScript can listen for user interactions and respond dynamically.

#### **Example: Button Click Event**
```javascript
document.getElementById("btn").addEventListener("click", function () {
    alert("Button Clicked!");
});
```

---

### **Why is DOM Important?**
✅ Enables **dynamic content updates** (e.g., interactive UI).  
✅ Allows JavaScript to **modify styles, attributes, and elements**.  
✅ Essential for **handling user events** (clicks, inputs, etc.).  
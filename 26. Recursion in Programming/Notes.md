### **Recursion in Programming**  

Recursion is a programming technique where a function calls itself to solve a problem. It is often used to break complex problems into smaller, more manageable subproblems.  

---

### **How Recursion Works**
A recursive function must have:  
1. **Base Case** – A condition to stop recursion and prevent infinite loops.  
2. **Recursive Case** – A part where the function calls itself with modified arguments.  

---

### **Example: Factorial of a Number**
```javascript
function factorial(n) {
    if (n === 0) return 1;  // Base case
    return n * factorial(n - 1);  // Recursive case
}

console.log(factorial(5)); // Output: 120
```

---

### **Example: Fibonacci Series**
```javascript
function fibonacci(n) {
    if (n <= 1) return n;  // Base case
    return fibonacci(n - 1) + fibonacci(n - 2);  // Recursive case
}

console.log(fibonacci(6)); // Output: 8
```

---

### **Advantages of Recursion**  
✔ **Simplifies complex problems** (e.g., tree traversal, graphs, backtracking).  
✔ **Reduces code length and improves readability**.  

---

### **Disadvantages of Recursion**  
❌ **High memory usage** due to function call stack.  
❌ **Risk of stack overflow** if the base case is not handled correctly.  
❌ **Slower execution** compared to loops in some cases.  

---

### **When to Use Recursion?**  
✅ **Tree or Graph Traversal** (e.g., DOM Traversal, File System)  
✅ **Divide and Conquer Algorithms** (e.g., Merge Sort, Quick Sort)  
✅ **Mathematical Problems** (e.g., Factorial, Fibonacci)  

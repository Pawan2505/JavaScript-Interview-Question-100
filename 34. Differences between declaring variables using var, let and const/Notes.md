### **Differences Between `var`, `let`, and `const` in JavaScript**  

In JavaScript, variables can be declared using **`var`**, **`let`**, and **`const`**. However, they behave differently in terms of **scope, hoisting, and reassignability**.

---

## **1️⃣ `var` (Function-scoped, Hoisted, Reassignable)**
✔ Can be **reassigned** and **redeclared**  
✔ **Function-scoped** (not block-scoped)  
✔ **Hoisted** but **initialized as `undefined`**  

🔹 **Example: `var` is function-scoped**  
```js
function example() {
    if (true) {
        var x = 10;
    }
    console.log(x); // ✅ 10 (accessible outside block)
}
example();
```

🔹 **Example: Hoisting with `var`**  
```js
console.log(a); // ✅ undefined (Hoisted but not assigned)
var a = 5;
```

---

## **2️⃣ `let` (Block-scoped, Hoisted, Reassignable)**
✔ Can be **reassigned**, but **not redeclared**  
✔ **Block-scoped** (only available inside `{}`)  
✔ **Hoisted** but **not initialized**  

🔹 **Example: `let` is block-scoped**  
```js
function example() {
    if (true) {
        let y = 20;
    }
    console.log(y); // ❌ ReferenceError (y is not defined)
}
example();
```

🔹 **Example: Hoisting with `let`**  
```js
console.log(b); // ❌ ReferenceError (Cannot access before initialization)
let b = 10;
```

---

## **3️⃣ `const` (Block-scoped, Hoisted, Not Reassignable)**
✔ **Cannot be reassigned or redeclared**  
✔ **Block-scoped** (same as `let`)  
✔ **Hoisted**, but **must be initialized**  

🔹 **Example: `const` cannot be reassigned**  
```js
const z = 30;
z = 40; // ❌ TypeError (Assignment to constant variable)
```

🔹 **Example: `const` is block-scoped**  
```js
if (true) {
    const a = 50;
}
console.log(a); // ❌ ReferenceError (a is not defined)
```

---

## **Key Differences Summary**  

| Feature  | `var` | `let` | `const` |
|----------|------|------|------|
| **Scope** | Function-scoped | Block-scoped | Block-scoped |
| **Reassignable?** | ✅ Yes | ✅ Yes | ❌ No |
| **Redeclarable?** | ✅ Yes | ❌ No | ❌ No |
| **Hoisted?** | ✅ Yes (as `undefined`) | ✅ Yes (but not initialized) | ✅ Yes (but must be initialized) |

---

### **Which One Should You Use?**  
✔ Use **`let`** when you need a variable that can change.  
✔ Use **`const`** for values that **should not change** (best practice).  
✔ Avoid **`var`**, as it can lead to unexpected issues due to hoisting and function scope.  

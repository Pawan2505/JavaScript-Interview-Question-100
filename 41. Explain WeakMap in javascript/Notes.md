## **WeakMap in JavaScript**  

A **WeakMap** is a special type of `Map` that **only allows objects as keys** and holds them **weakly**, meaning they do not prevent garbage collection if there are no other references to the object.  

---

## **1️⃣ Key Features of WeakMap**  
✔ **Only objects can be used as keys** – Primitive values (`string`, `number`, etc.) **are not allowed** as keys.  
✔ **Weak References** – If no references to an object exist, it gets **garbage collected** automatically.  
✔ **No Iteration** – Unlike `Map`, a `WeakMap` does **not** support `.keys()`, `.values()`, or `.forEach()`.  
✔ **No Size Property** – You **cannot check** the size of a `WeakMap`.  

---

## **2️⃣ Creating a WeakMap**  
A `WeakMap` is created using `new WeakMap()`.  

🔹 **Example: Adding Objects to a WeakMap**  
```js
let weakMap = new WeakMap();

let user1 = { name: "Alice" };
let user2 = { name: "Bob" };

weakMap.set(user1, "Admin");
weakMap.set(user2, "Editor");

console.log(weakMap.get(user1)); // Output: Admin
console.log(weakMap.has(user2)); // Output: true
```
✔ `set(key, value)` – Adds a key-value pair to the `WeakMap`.  
✔ `get(key)` – Retrieves the value for the given key.  
✔ `has(key)` – Checks if a key exists in the `WeakMap`.  

---

## **3️⃣ WeakMap Automatically Removes Unused Objects**  
If an object inside a `WeakMap` is no longer referenced anywhere else, it gets **garbage collected**.  

🔹 **Example: Automatic Garbage Collection**  
```js
let userCache = new WeakMap();

let user = { id: 1, name: "John" };
userCache.set(user, "Active User");

console.log(userCache.get(user)); // Output: Active User

user = null; // Object loses reference

// After some time, garbage collector removes it
console.log(userCache.get(user)); // Output: undefined
```
✔ **Useful for caching temporary data without memory leaks.**  

---

## **4️⃣ WeakMap Methods**  
| Method | Description |
|--------|------------|
| `set(key, value)` | Adds a key-value pair (key must be an object) |
| `get(key)` | Retrieves the value associated with a key |
| `has(key)` | Checks if a key exists in the WeakMap |
| `delete(key)` | Removes a key-value pair from the WeakMap |

---

## **5️⃣ WeakMap vs Map**  
| Feature | `WeakMap` | `Map` |
|---------|----------|------|
| **Keys** | Only objects | Any type (objects, primitives) |
| **Garbage Collection** | Removes unused keys automatically | Keeps all keys unless manually deleted |
| **Iteration** | ❌ Not possible | ✅ Supports `.keys()`, `.values()`, `.forEach()` |
| **Size Property** | ❌ Not available | ✅ Available using `.size` |

---

## **6️⃣ When to Use WeakMap?**  
✔ **Storing private data** related to objects (e.g., user permissions, metadata).  
✔ **Avoiding memory leaks** by allowing garbage collection of unused objects.  
✔ **Tracking elements in the DOM** (e.g., storing event listeners).  
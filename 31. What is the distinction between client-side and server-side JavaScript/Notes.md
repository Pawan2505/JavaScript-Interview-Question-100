### **Client-Side vs. Server-Side JavaScript**  

JavaScript can run both **on the client-side (browser)** and **on the server-side (backend)**, but they serve different purposes.  

---

## **1️⃣ Client-Side JavaScript (CSJS)**
✔ **Runs in the browser**  
✔ Used for creating interactive web pages  
✔ Manipulates the **DOM (Document Object Model)**  
✔ Can’t access databases or server resources directly  

🔹 **Example:**  
```js
document.querySelector("button").addEventListener("click", function() {
    alert("Button Clicked!"); // Runs in the browser
});
```
🔹 **Common Uses:**  
✅ Form validation  
✅ Animations & UI updates  
✅ Handling events (click, hover, etc.)  
✅ Making API calls using `fetch()`  

---

## **2️⃣ Server-Side JavaScript (SSJS)**
✔ **Runs on the server** (using Node.js)  
✔ Handles database interactions, authentication, and business logic  
✔ Doesn’t manipulate the browser DOM  

🔹 **Example (Using Node.js):**  
```js
const http = require('http');

const server = http.createServer((req, res) => {
    res.writeHead(200, {'Content-Type': 'text/plain'});
    res.end('Hello from the Server!');
});

server.listen(3000, () => console.log("Server running on port 3000"));
```
🔹 **Common Uses:**  
✅ Handling requests & responses  
✅ Database operations (MongoDB, MySQL)  
✅ Authentication & security  
✅ Backend APIs  

---

## **Key Differences**  

| Feature | **Client-Side JavaScript** | **Server-Side JavaScript** |
|---------|---------------------------|---------------------------|
| **Where it runs** | Browser | Server (Node.js) |
| **Access to DOM** | Yes | No |
| **Interacts with database?** | No | Yes |
| **Primary Use** | UI interactions, animations | Handling requests, databases, APIs |
| **Examples** | `window`, `document` | `fs`, `http`, `express` |

---

### **Which One Should You Use?**
✔ Use **Client-Side JS** for UI updates, animations, and event handling  
✔ Use **Server-Side JS** for database operations, authentication, and APIs  

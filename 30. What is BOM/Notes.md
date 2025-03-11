
### **What is BOM (Browser Object Model) in JavaScript?**  

The **BOM (Browser Object Model)** is a set of JavaScript objects provided by the browser that allows interaction with the browser itself, apart from the webpage (DOM). It enables JavaScript to control browser-related functionality like windows, history, and navigation.  

---

### **Key Features of BOM**  
✔ **Allows control over browser windows and tabs**  
✔ **Provides access to browser history, URL, and screen info**  
✔ **Enables interaction with cookies and local storage**  

---

### **Main Objects of BOM**  

1️⃣ **`window` Object** (Global object in BOM)  
   - Represents the browser window  
   - Provides methods for alerts, pop-ups, and timeouts  

   **Example:**
   ```js
   alert("Hello!"); // Displays an alert box
   console.log(window.innerWidth); // Logs the browser's width
   ```

2️⃣ **`navigator` Object** (Information about the browser)  
   - Provides details like browser name, version, and OS  

   **Example:**
   ```js
   console.log(navigator.userAgent); // Shows browser details
   console.log(navigator.language);  // Displays browser language
   ```

3️⃣ **`location` Object** (URL & Navigation)  
   - Handles the current page URL and navigation  

   **Example:**
   ```js
   console.log(location.href); // Shows current page URL
   // location.reload(); // Reloads the page
   ```

4️⃣ **`history` Object** (Browser navigation history)  
   - Allows movement through previously visited pages  

   **Example:**
   ```js
   // history.back();  // Goes to the previous page
   // history.forward(); // Moves to the next page
   ```

5️⃣ **`screen` Object** (Screen resolution & properties)  
   - Provides details about screen width, height, and color depth  

   **Example:**
   ```js
   console.log(screen.width, screen.height); // Logs screen dimensions
   ```

---

### **Difference Between BOM and DOM**  

| Feature | **BOM (Browser Object Model)** | **DOM (Document Object Model)** |
|---------|------------------------------|------------------------------|
| **Purpose** | Manages browser behavior | Manipulates webpage content |
| **Key Object** | `window` | `document` |
| **Examples** | Alerts, navigation, screen info | HTML elements, text, styling |

---

### **Why is BOM Important?**  
✅ Controls browser actions (alerts, resizing, navigation)  
✅ Enables interaction with browser history and URL  
✅ Helps collect browser information for customization  
✅ Facilitates cross-browser compatibility testing  
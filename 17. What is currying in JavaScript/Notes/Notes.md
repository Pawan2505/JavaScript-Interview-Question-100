### **17: What is currying in JavaScript?**

#### **Answer:**

**Currying** is a technique in JavaScript (and other functional programming languages) where a function takes multiple arguments one at a time instead of all at once. In other words, currying transforms a function that takes multiple arguments into a series of functions that each take a single argument.

The key idea behind currying is that you break down a function that takes multiple parameters into a chain of functions, where each function takes one argument and returns a new function to take the next argument.

---

### **How Currying Works:**

Instead of writing a function that takes all arguments at once, currying allows you to **partially apply** the function, one argument at a time. Each function in the chain "remembers" the arguments passed to it, and once all arguments are provided, the final result is computed.

---

### **Syntax of a Curried Function:**

```javascript
function multiply(a) {
  return function(b) {
    return a * b;
  }
}
```

In the example above, `multiply()` is a curried function that takes the first argument `a` and returns a function that takes the second argument `b`. When both arguments are provided, the multiplication result is returned.

---

### **Example of Currying:**

Let's take a look at a real-world example with Indian context:

```javascript
function greet(greeting) {
  return function(name) {
    return greeting + ', ' + name;
  }
}

const greetHello = greet("Hello");
console.log(greetHello("Raj"));  // "Hello, Raj"
console.log(greetHello("Priya"));  // "Hello, Priya"

const greetNamaste = greet("Namaste");
console.log(greetNamaste("Aarav"));  // "Namaste, Aarav"
```

In the above example:
1. The `greet()` function is curried.
2. First, it takes the `greeting` (like "Hello" or "Namaste").
3. It returns another function that takes the `name` (like "Raj" or "Aarav").
4. The result is the combination of both, e.g., `"Hello, Raj"`.

---

### **Advantages of Currying:**

1. **Reusability:** Once you create a curried function, you can easily reuse the first argument, which allows you to create more specialized functions.
   
   Example:
   ```javascript
   const greetHello = greet("Hello");
   console.log(greetHello("Arvind"));  // "Hello, Arvind"
   console.log(greetHello("Sita"));    // "Hello, Sita"
   ```

2. **Partial Application:** Currying makes it easier to create functions with pre-defined arguments. You can apply some arguments and get a function that expects fewer arguments.

3. **Cleaner Code:** It helps make the code cleaner by reducing the number of arguments required for a function call, especially when the function has many parameters.

---

### **Another Example :**

Let’s look at a more complex example where we curry a function that calculates the total price with taxes and discounts:

```javascript
function calculatePrice(basePrice) {
  return function(tax) {
    return function(discount) {
      const priceWithTax = basePrice + (basePrice * tax);
      const finalPrice = priceWithTax - (priceWithTax * discount);
      return finalPrice;
    };
  };
}

const priceWithTaxAndDiscount = calculatePrice(100);  // base price is 100
const priceAfterTax = priceWithTaxAndDiscount(0.18);  // tax is 18%
const finalPrice = priceAfterTax(0.1);  // discount is 10%

console.log(finalPrice);  // 107.8 (after applying 18% tax and 10% discount)
```

In this example:
1. The `calculatePrice()` function is curried to take the `basePrice`, then `tax`, and then `discount` one by one.
2. It calculates the final price after applying the tax and discount.

---

### **Note:**

- **Currying** is a technique that transforms a function that takes multiple arguments into a sequence of functions, each taking one argument.
- It allows for **partial application** of functions and can be used to create more specialized functions with predefined arguments.
- Currying is particularly useful for **reusability** and **cleaner code**.

---

Currying is a powerful technique used in functional programming and can make your JavaScript code more modular and flexible.


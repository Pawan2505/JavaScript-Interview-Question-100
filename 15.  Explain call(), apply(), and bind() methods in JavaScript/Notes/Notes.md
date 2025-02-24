### **15: Explain `call()`, `apply()`, and `bind()` methods in JavaScript.**

#### **Answer:**

In JavaScript, **`call()`**, **`apply()`**, and **`bind()`** are methods used to **change the context** of **`this`** in a function. These methods allow you to specify what `this` should refer to when calling a function, instead of using the default context.

Let’s understand each method in detail with examples.

---

### **1. `call()` Method:**

The **`call()`** method allows you to **call a function with a specific `this` value** and pass arguments individually.

**Syntax:**
```javascript
func.call(thisValue, arg1, arg2, arg3, ...);
```

- **`thisValue`**: The value of `this` that you want to bind to the function.
- **`arg1, arg2, arg3, ...`**: Arguments that you want to pass to the function.

---

#### **Example:**

Let’s consider a scenario where we have a `person` object and we want to use the `greet` function with different `this` values:

```javascript
const person1 = { name: "Arjun" };
const person2 = { name: "Priya" };

function greet(city, country) {
  console.log(`Hello, I am ${this.name} from ${city}, ${country}.`);
}

// Using call() to change the context of 'this'
greet.call(person1, "Mumbai", "India");  // Hello, I am Arjun from Mumbai, India.
greet.call(person2, "Delhi", "India");   // Hello, I am Priya from Delhi, India.
```

In this case, `call()` allows us to invoke `greet()` with different `this` values (i.e., `person1` and `person2`), and we can also pass arguments like `city` and `country`.

---

### **2. `apply()` Method:**

The **`apply()`** method is **very similar to `call()`**, but instead of passing arguments individually, you pass them as an **array** or an **array-like object**.

**Syntax:**
```javascript
func.apply(thisValue, [arg1, arg2, arg3, ...]);
```

- **`thisValue`**: The value of `this` that you want to bind to the function.
- **`[arg1, arg2, arg3, ...]`**: An array or array-like object that contains the arguments.

---

#### **Example with `apply()` :**

Let’s use the same `greet` function but with the `apply()` method:

```javascript
const person1 = { name: "Arjun" };
const person2 = { name: "Priya" };

function greet(city, country) {
  console.log(`Hello, I am ${this.name} from ${city}, ${country}.`);
}

// Using apply() to change the context of 'this'
greet.apply(person1, ["Mumbai", "India"]);  // Hello, I am Arjun from Mumbai, India.
greet.apply(person2, ["Delhi", "India"]);   // Hello, I am Priya from Delhi, India.
```

Here, instead of passing arguments directly, we pass them as an array: `["Mumbai", "India"]`.

---

### **3. `bind()` Method:**

The **`bind()`** method is **different** from `call()` and `apply()` because it does not **immediately invoke** the function. Instead, it **returns a new function** with the specified `this` value and arguments. This new function can be called later.

**Syntax:**
```javascript
const newFunc = func.bind(thisValue, arg1, arg2, arg3, ...);
```

- **`thisValue`**: The value of `this` that you want to bind to the function.
- **`arg1, arg2, arg3, ...`**: Optional arguments to be passed when the returned function is called.

---

#### **Example with `bind()` :**

Let's look at an example using `bind()` to create a new function that is already bound to a specific `this` value:

```javascript
const person1 = { name: "Arjun" };
const person2 = { name: "Priya" };

function greet(city, country) {
  console.log(`Hello, I am ${this.name} from ${city}, ${country}.`);
}

// Using bind() to create a new function with 'this' bound to 'person1'
const greetArjun = greet.bind(person1);

// Later, we can call greetArjun with arguments
greetArjun("Mumbai", "India");  // Hello, I am Arjun from Mumbai, India.

// We can also use bind for person2
const greetPriya = greet.bind(person2);
greetPriya("Delhi", "India");   // Hello, I am Priya from Delhi, India.
```

In this example:
- `greet.bind(person1)` creates a new function `greetArjun` where `this` is already set to `person1`.
- We call `greetArjun()` with the arguments `"Mumbai"` and `"India"`, and it prints the result using the `this` value from `person1`.

---

### **Differences:**

| Method   | Behavior                                         | Arguments     | Execution Timing        |
|----------|--------------------------------------------------|---------------|-------------------------|
| **`call()`** | Invokes the function immediately with a specific `this` value and arguments passed individually. | Individual arguments. | Immediately.            |
| **`apply()`** | Invokes the function immediately with a specific `this` value and arguments passed as an array. | Arguments as an array. | Immediately.            |
| **`bind()`**  | Returns a new function with a specific `this` value, which can be invoked later. | Arguments (optional) that are passed when calling the returned function. | Doesn’t execute immediately, returns a new function to be invoked later. |

---

### **When to Use Each Method:**

- **`call()`** is used when you want to call a function immediately, but with a specific `this` value and individual arguments.
- **`apply()`** is used when you want to call a function immediately, but with a specific `this` value and arguments passed as an array.
- **`bind()`** is used when you want to create a new function with a fixed `this` value that can be invoked later.

---

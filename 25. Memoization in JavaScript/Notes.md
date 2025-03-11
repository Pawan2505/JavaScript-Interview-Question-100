2. Memoization in JavaScript

### **Memoization in JavaScript**

Memoization is an optimization technique used to improve the performance of functions by caching their previously computed results. When a function is called with the same arguments, the cached result is returned instead of recalculating the value.

#### **How Memoization Works**

1. Store function results in a cache (object or Map).
2. Before executing the function, check if the result exists in the cache.
3. If found, return the cached result.
4. If not, compute the result, store it in the cache, and return it.

#### **Example: Memoization with Recursion (Fibonacci Sequence)**

```javascript
function memoize(fn) {
  let cache = {};
  return function (...args) {
    let key = JSON.stringify(args);
    if (cache[key]) {
      console.log("Fetching from cache:", key);
      return cache[key];
    } else {
      console.log("Calculating result for:", key);
      let result = fn(...args);
      cache[key] = result;
      return result;
    }
  };
}

// Recursive Fibonacci function
function fibonacci(n) {
  if (n <= 1) return n;
  return fibonacci(n - 1) + fibonacci(n - 2);
}

// Memoized version
const memoizedFibonacci = memoize(fibonacci);

console.log(memoizedFibonacci(10)); // Calculates and stores results
console.log(memoizedFibonacci(10)); // Fetches from cache
```

#### **Benefits of Memoization**

✅ Improves performance, especially for expensive function calls (e.g., recursion).  
✅ Reduces redundant calculations.  
✅ Enhances responsiveness in applications (e.g., UI updates, API calls).

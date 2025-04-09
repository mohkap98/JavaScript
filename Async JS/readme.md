# 🫼 Callback Hell & Promises in JavaScript

This project illustrates how JavaScript handles asynchronous operations using **Promises**, helping avoid **callback hell**. We'll walk through a real-world-inspired example: completing daily chores—**cleaning the kitchen**, **walking the dog**, and **taking out the trash**.

---

## 🔍 What is a Promise?

A **Promise** is an object in JavaScript that represents the eventual completion (or failure) of an asynchronous operation.

### Promise States:
- **Pending**: Initial state, neither fulfilled nor rejected.
- **Fulfilled (Resolved)**: Operation completed successfully.
- **Rejected**: Operation failed.

### Syntax:
```js
new Promise((resolve, reject) => {
  // async operation
})
```

---

## 💡 Why Not Just Use Callbacks?

Callbacks can quickly become messy and hard to manage when they're nested within each other. This is called **callback hell**. Promises help by flattening the structure and improving readability.

---

## 🧽 Example: Chores with Promises

### The tasks:
1. Clean the kitchen
2. Walk the dog
3. Take out the trash

### Code:

```js
let cleanKitchen = () => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const cleanedKitchen = true;

      if (cleanedKitchen) {
        resolve("You cleaned the kitchen");
      } else {
        reject("Kitchen is not cleaned yet!");
      }
    }, 2500);
  });
};

let walkDog = () => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const walkedDog = true;

      if (walkedDog) {
        resolve("You walked the dog!");
      } else {
        reject("You didn't walk the dog");
      }
    }, 1500);
  });
};

let takeTrash = () => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const tookTrash = false;

      if (tookTrash) {
        resolve("You took the trash out");
      } else {
        reject("You did not take the trash out");
      }
    }, 500);
  });
};

// Chaining the Promises
cleanKitchen()
  .then((value) => {
    console.log(value);
    return walkDog();
  })
  .then((value) => {
    console.log(value);
    return takeTrash();
  })
  .then((value) => {
    console.log(value);
    console.log("All chores are done!");
  })
  .catch((err) => {
    console.error(err);
  });
```

---

## ✅ Output (Expected):
```
You cleaned the kitchen
You walked the dog!
You did not take the trash out
```

---

## 🚀 What's Next?

You can take this further by:
- Converting to **async/await**
- Handling multiple promises with `Promise.all()`
- Learning about `finally()` for cleanup

---

Made with ☕ and JavaScript.  
Happy coding! ✨


# 🧹 Async & Await in JavaScript

This project demonstrates how to use `async` and `await` in JavaScript to handle asynchronous tasks in a cleaner, more readable way than traditional Promises or callbacks.

## 💡 What are `async` and `await`?

- **`async`**: Declares a function as asynchronous, which means it will return a Promise.
- **`await`**: Pauses the execution of an `async` function until a Promise is resolved or rejected.

These keywords make asynchronous code look and behave like synchronous code.

---

## 🧼 Real-World Example: Doing Chores!

We simulate a sequence of asynchronous household tasks:
- Cleaning the kitchen
- Walking the dog
- Taking out the trash

Each task returns a Promise that resolves after a short delay.

### ✅ Task Flow

```js
let cleanKitchen = () => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const cleanedKitchen = true
            cleanedKitchen ? resolve("You cleaned the kitchen") : reject("Kitchen is not cleaned yet!");
        }, 2500);
    });
};

let walkDog = () => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const walkedDog = true
            walkedDog ? resolve("You walked the dog!") : reject("You didn't walk the dog");
        }, 1500);
    });
};

let takeTrash = () => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const tookTrash = true
            tookTrash ? resolve("You took the trash out") : reject("You did not take the trash out");
        }, 500);
    });
};

async function doChores() {
    try {
        const cleanedKitchen = await cleanKitchen();
        console.log(cleanedKitchen);

        const walkedDog = await walkDog();
        console.log(walkedDog);

        const tookTrash = await takeTrash();
        console.log(tookTrash);

        console.log("🎉 All chores done!");
    } catch (error) {
        console.error("❌", error);
    }
}

doChores();

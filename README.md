# JavaScript Concepts - Cheat Sheet 🚀

This README covers core JavaScript concepts with working examples. Perfect for beginners and intermediates who want to revise or learn by example.

---

## 🔑 DOM Manipulation
```js
let username;
document.getElementById("submit").onclick = function () {
    username = document.getElementById("myinput").value;
    document.getElementById("myh1").textContent = `Welcome ${username}`;
};
```

---

## 🔠 Type Casting
```js
Number("3");
String(23);
Boolean(0); // false
```

---

## π Circumference Calculator
```js
const PI = 3.14;
let radius;
let circumfrence;

document.getElementById("submit").onclick = function () {
    radius = Number(document.getElementById("myinput").value);
    circumfrence = 2 * PI * radius;
    document.getElementById("output").textContent = circumfrence;
};
```

---

## ⚖️ Math Methods
```js
Math.floor(3.7);  // 3
Math.ceil(3.7);   // 4
Math.pow(2, 3);   // 8
Math.sqrt(81);    // 9
Math.log(10);
Math.abs(-3.21);  // 3.21
Math.sign(-9.1);  // -1

Math.max(4, 5, 1); // 5
Math.min(3, 4, 1); // 1
```

---

## ⚀ Dice Roll Example
```js
let diceRoll = Math.ceil(Math.random() * 6);
document.getElementById("myh1").textContent = diceRoll;
```

---

## 📄 Strings
```js
s.charAt(0);
s.length;
s.trim();
```

## ⚡ Method Chaining
```js
username = window.prompt("Enter username!");
username = username.trim().charAt(0).toUpperCase() + username.trim().slice(1).toLowerCase();
document.getElementById("myh1").textContent = username;
```

---

## 🤾 Spread Operator
```js
let items = [3, 1, 4];
let maximum = Math.max(...items);
console.log(maximum); // 4

let ages = [4, 5, 9];
let names = ["Mohak", "Garima", "Sapna"];
let copies = [...ages, ...names];
console.log(copies);
```

---

## 🔋 Rest Parameters
```js
function openFridge(...foods) {
    console.log(foods);
}

openFridge("Ramen", "Shushi", "Burger", "Pizza");
```

---

## ⟳ Callbacks in JS
Used for async operations like file reading, network requests, etc.
```js
function hello(callback) {
    setTimeout(function () {
        console.log("hello");
    }, 3000);
    callback();
}

function goodbye() {
    console.log("Goodbye!");
}

hello(goodbye);
```

---

## ✨ Arrow Functions
```js
const addNums = (a) => console.log(a);
addNums([2, 2, 1, 1]);
```

---

## 🤐 Optional Chaining
```js
let user = {
    name: "Mohak",
    age: 25,
    gender: "Male",
    address: {
        houseNum: 62,
        street: "D",
        city: "Delhi"
    }
};

console.log(user.address.town?.subtown ?? "Azadpur");
```

---

## 📃 Array Methods
```js
let arr = [3, 4, 1, 2, 5];

let d = arr.map(ele => ele * 2);
let filtered = arr.filter(ele => !(ele & 1));
const total = arr.reduce((acc, ele) => acc + ele);

arr.sort((a, b) => a - b); // ascending
arr.sort((a, b) => b - a); // descending
```

---

## 📂 CRUD with Array of Objects
```js
const cars = [
  { brand: "Toyota", model: "Corolla", year: 2020, color: "White" },
  { brand: "Honda", model: "Civic", year: 2019, color: "Black" },
  { brand: "Ford", model: "Mustang", year: 2021, color: "Red" },
  { brand: "Tesla", model: "Model 3", year: 2022, color: "Blue" }
];

// Create
let updated_cars = [...cars, {
  brand: "Mahindra",
  model: "Be 6e",
  year: 2024,
  color: "Black"
}];

// Delete
let filtered_cars = updated_cars.filter(car => car.brand != "Honda");

// Update
let new_cars = filtered_cars.map(car =>
  car.brand === "Mahindra" ? { ...car, color: "Red" } : car
);

console.log(new_cars);
```

---

### 🎉 That's it!
This cheat sheet covers a wide variety of essential JavaScript concepts and is a great reference for quick review. Happy coding!


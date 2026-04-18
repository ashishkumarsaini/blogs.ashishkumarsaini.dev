---
title: "Understanding Object-Oriented Programming in Javascript"
seoTitle: "Understanding Object Oriented Programming in JS"
seoDescription: "This blog is about the object-oriented programming concept in JS. Beginner-friendly explanation of classes, objects, methods, and other terminologies."
datePublished: 2026-04-18T19:04:30.778Z
cuid: cmo4phs1j008h2cmi6we56wgu
slug: understanding-object-oriented-programming-in-javascript
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/91bfd74e-8923-4d6d-ac4b-24ab93af7d6d.png

---

Object-oriented programming is a concept of writing code in which we organize everything around objects.

An object is a combination of

1.  Properties
    
2.  Methods
    

Instead of writing separate variables and functions, we bundle them together.

## Real-World Analogy: Blueprint → Objects

Let’s understand object-oriented programming with a simple example:

Imagine you are a car manufacturer.

You first create a **blueprint** (design)

*   Then you use that blueprint to create multiple cars
    

👉 In JavaScript:

*   Blueprint = **Class**
    
*   Car = **Object (Instance)**
    

So instead of rewriting code again and again, we define a class once and reuse it.

* * *

## 🧱 What is a Class in JavaScript?

A **class** is a blueprint used to create objects.

It defines:

*   What properties an object will have
    
*   What actions it can perform
    

### Example:

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hi, my name is ${this.name}`);
  }
}
```

* * *

## 🧪 Creating Objects (Instances)

We use the `new` keyword to create objects from a class.

```javascript
const person1 = new Person("Ashish", 25);
const person2 = new Person("Rahul", 30);

person1.greet(); // Hi, my name is Ashish
person2.greet(); // Hi, my name is Rahul
```

👉 Each object:

*   Has its own data
    
*   Shares the same structure and methods
    

* * *

## ⚙️ Understanding the Constructor

The **constructor** is a special method inside a class.

### Key Points:

*   It runs automatically when an object is created
    
*   It initializes object properties
    

```javascript
constructor(name, age) {
  this.name = name;
  this.age = age;
}
```

👉 `this` refers to the current object.

* * *

## 🔧 Methods Inside a Class

Methods define what an object can do.

```javascript
greet() {
  console.log(`Hi, my name is ${this.name}`);
}
```

👉 Methods are shared across all instances (memory efficient).

* * *

## 🔒 Basic Idea of Encapsulation

Encapsulation means:

👉 **Keeping data and methods together and controlling access**

### Real-world example:

Think of a car:

*   You don’t directly control the engine
    
*   You use steering, brakes, accelerator
    

Same in code:

*   Internal data is hidden
    
*   Access is controlled via methods
    

### Simple Example:

```javascript
class BankAccount {
  constructor(balance) {
    this.balance = balance;
  }

  deposit(amount) {
    this.balance += amount;
  }

  getBalance() {
    return this.balance;
  }
}
```

👉 We interact using methods instead of directly modifying data.

* * *

## ♻️ Why Use OOP?

OOP helps you write better code:

*   ✅ Reusable (write once, use many times)
    
*   ✅ Organized (structured code)
    
*   ✅ Scalable (easy to expand)
    
*   ✅ Maintainable (easy to debug and update)
    

* * *

## 🧠 Class vs Object (Quick Comparison)

| Concept | Meaning |
| --- | --- |
| Class | Blueprint |
| Object | Real instance created from class |

* * *

## 🎯 Assignment

Try this yourself 👇

### Task:

Create a `Student` class with:

*   Properties: `name`, `age`
    
*   Method: `printDetails()`
    

### Example Solution:

```javascript
class Student {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  printDetails() {
    console.log(`Name: ${this.name}, Age: ${this.age}`);
  }
}

const student1 = new Student("Aman", 20);
const student2 = new Student("Neha", 22);

student1.printDetails();
student2.printDetails();
```

* * *

## 🧩 Visual Understanding (Conceptual)

```plaintext
Class (Blueprint)
      ↓
Create using new
      ↓
Objects (Instances)
```

Example:

```plaintext
Car (Class)
  ↓
car1, car2, car3 (Objects)
```

* * *

## 📌 Common Mistakes Beginners Make

❌ Forgetting `new` keyword ❌ Not using `this` properly ❌ Thinking each object has separate methods (they are shared) ❌ Confusing class with object

* * *

## 🧠 Final Thoughts

OOP is not just a concept—it’s a **way of thinking**.

Once you understand:

*   Class
    
*   Object
    
*   Constructor
    
*   Methods
    

You can build real-world applications much more easily 🚀

* * *

Happy Coding! 💻
---
title: "Understanding the new Keyword in JavaScript"
seoTitle: "Understanding the new Keyword in JavaScript"
seoDescription: "Learn how the new keyword creates objects in JavaScript, connects prototypes, and helps constructor functions build reusable object instances."
datePublished: 2026-05-07T22:04:37.753Z
cuid: cmow1alfa00bc1qkkeooz05vn
slug: understanding-the-new-keyword-in-javascript
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/b7c88841-1847-48a3-b523-7d69a87cd2bf.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/47af2292-3027-495c-80ed-a3f8f2f2c142.png
tags: javascript, new-keyword, js-new-keyword

---

In JavaScript, the `new` keyword is used to create a new object from a constructor function.

Think of a constructor function like a blueprint, and `new` as the tool that builds an actual object from that blueprint.

```javascript
function User(name, age) {
  this.name = name;
  this.age = age;
}

const user1 = new User("Rahul", 22);

console.log(user1.name); // Rahul
console.log(user1.age);  // 22
```

Here, `User` is a constructor function, and `user1` is an object created from it.

When we write:

```javascript
const user1 = new User("Rahul", 22);
```

JavaScript does a few things behind the scenes:

1.  Creates a new empty object.
    
2.  Sets `this` to point to that new object.
    
3.  Links the object to the constructor’s prototype.
    
4.  Runs the constructor function.
    
5.  Returns the newly created object.  
    

So internally, it feels something like this:

```javascript
const user1 = {};
user1.name = "Rahul";
user1.age = 22;
```

But `new` does this in a proper JavaScript way, including prototype linking.

### Constructor Functions

Constructor functions are normal functions, but they are usually written with a capital first letter.

```javascript
function Car(brand, model) {
  this.brand = brand;
  this.model = model;
}
```

Now we can create multiple car objects:

```javascript
const car1 = new Car("Toyota", "Fortuner");
const car2 = new Car("Honda", "City");

console.log(car1.brand); // Toyota
console.log(car2.brand); // Honda
```

Each object gets its own values, but both are created from the same constructor.

### How `new` Links Prototypes

Every function in JavaScript has a `prototype` object.

When we create an object using `new` keyword, that new object gets linked to the constructor’s prototype.

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.sayHello = function () {
  console.log(`Hello, my name is ${this.name}`);
};

const person1 = new Person("John");

person1.sayHello(); // Hello, my name is John
```

Here, `sayHello` is not directly inside `person1`. It comes from `Person.prototype`.

So the relation looks like this:

```plaintext
Person constructor -> Person.prototype -> person1 object
```

Or in simple words:

```plaintext
Constructor Function -> Prototype -> Instance Object
```

### Why This Is Useful

Using prototypes helps us avoid repeating the same method inside every object.

Instead of creating a new copy of `sayHello` for every person, JavaScript stores it once in the prototype, and all instances can use it.

```javascript
const person2 = new Person("Rahul");

person1.sayHello();
person2.sayHello();
```

Both objects can use the same method from the prototype.

## `new` keyword with Classes in JavaScript

Classes in JavaScript are a cleaner and more modern way to create constructor functions.

Behind the scenes, classes still work using prototypes and the `new` keyword.

## Creating Objects with Classes

```javascript
class User {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

const user1 = new User("Pankaj", 22);

console.log(user1.name); // Pankaj
console.log(user1.age);  // 22
```

Here:

*   `User` is a class
    
*   `constructor()` runs automatically when `new` is used
    
*   `user1` becomes an instance of the class
    

Without `new`, classes cannot create instances.

```javascript
const user1 = User("Pankaj");
```

This throws an error:

```plaintext
Class constructor User cannot be invoked without 'new'
```

Because classes are designed specifically for object creation through `new`.

### Final Thought

The `new` keyword is mainly responsible for creating object instances from constructor functions.

It creates a fresh object, connects it with the constructor’s prototype, and sets `this` to that object, and returns it.

So whenever you see this:

```javascript
const obj = new Constructor();
```

You can read it as:

```plaintext
Create a new object using this constructor blueprint.
```

  
  
Follow the series to learn more about Javascript.
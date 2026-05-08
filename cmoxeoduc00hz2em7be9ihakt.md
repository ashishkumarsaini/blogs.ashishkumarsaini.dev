---
title: "Understanding this, call(), apply(), and bind() in JavaScript"
seoTitle: "Understanding call(), apply(), and bind() in JavaScript"
seoDescription: "Learn JavaScript this, call(), apply(), and bind() with simple examples, real-world use cases, and easy explanations for beginners."
datePublished: 2026-05-08T21:07:02.295Z
cuid: cmoxeoduc00hz2em7be9ihakt
slug: this-call-apply-and-bind-in-javascript
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/12a6b805-42a5-45b6-b2e7-d5e3d939ce7e.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/0b9abeb6-c55b-41b3-9ab8-b5a020bf8378.png
tags: this-keyword-in-javascript, call-apply-and-bind-methods

---

JavaScript gives developers a lot of flexibility, but one thing that confuses almost everyone at first is `this`.

In this article, we’ll understand:

*   What `this` means in JavaScript
    
*   How `this` behaves in functions and objects
    
*   What does call(), apply(), and bind() do and their differences
    
*   Simple real-world examples
    

Let’s make it simple.

## What is `this` in JavaScript?

The easiest way to understand the concept of `this`. Just remember one thing:

**This refers to the object that is calling the function.**

In simple words, whoever calls the function becomes `this` for the function.

### Inside Object

Example:

```javascript
const user = {
    name: 'Rahul',
    greet: function (){
        console.log(`Hello ${this.name}`)
    }
}

user.greet();
```

Here, `user` calls the greet function.

So, `this` -> `user` for greet function.

```javascript
const person1 = {
    name: "Rahul",
    greet() {
        console.log(`Hello ${this.name}`);
    }
};

const person2 = { name: "Aman", };

person2.greet = person1.greet;

person2.greet();
```

Here, as the person2.greet is initialized with person1.greet.

But still, as the person2 is calling the greet function, the output will be 'Hello Aman'

### Inside Normal Functions

Let’s understand with a regular function example.

```javascript
function show() { 
    console.log(this);
}

show();
```

In browsers, this usually prints `window`, because the show function is directly called from the global object (i.e. `window` for browser).

But in strict mode:

```javascript
"use strict"

function show() {
    console.log(this);
}

show();
```

The output becomes `undefined`.

That’s because strict mode prevents JavaScript from automatically attaching this to the global object.

## What is call() in JavaScript?

`call()` lets you manually decide what this should be.

Syntax:

```javascript
functionName.call(thisValue, arg1, arg2)
```

functionName.call(thisValue, arg1, arg2)

Example:

```javascript
const user = { name: "Ashish", }

function greet(city) {
    console.log(`Hello ${this.name} from ${city}`) 
}

greet.call(user, "Delhi")
```

Output: Hello Ashish from Delhi

Here what happened, you can see the `greet` is not attached to the `user` object, but if I want to pass the `user` as a context to the `greet`, we can use `call()`.

call() is commonly used for:

*   Function borrowing
    
*   Reusing methods
    
*   Setting custom this
    

Example:

```javascript
const person1 = {
    name: "Rahul",
    introduce() {
        console.log(`Hi, I am ${this.name}`)
    },
};

const person2 = { name: "Aman" };

person1.introduce.call(person2);
```

Output: Hi, I am Aman

Here, person2 borrowed the method from person1.

## What is apply() in JavaScript?

`apply()` works almost exactly like `call()`.

The only difference is that `apply()` it accepts arguments as an array.

Syntax:

```javascript
functionName.apply(thisValue, [args]);
```

Example:

```javascript
const user = { name: "Ashish" };

function greet(city, country) {
    console.log(`Hello ${this.name} from ${city}, ${country}`) 
}

greet.apply(user, ["Delhi", "India"]);
```

Output: Hello Ashish from Delhi, India

## call() vs apply()

Both do the same thing:

*   They immediately invoke the function
    
*   They manually set this
    

The difference is only in how arguments are passed.

*   call:
    
    ```javascript
    greet.call(user, "Delhi", "India");
    ```
    
*   apply:
    
    ```javascript
    greet.apply(user, ["Delhi", "India"]);
    ```
    

## What is bind() in JavaScript?

`bind()` is slightly different than call and apply.

Instead of immediately calling the function, bind() returns a new function.

Syntax:

```javascript
functionName.bind(thisValue);
```

Example:

```javascript
const user = { name: "Ashish" };

function greet() {
    console.log(`Hello ${this.name}`);
}

const newFunction = greet.bind(user);

newFunction();
```

Output: Hello Ashish

**Why is bind() Useful?**

bind() is useful when you want to:

*   Store a function
    
*   Pass functions around
    
*   Keep the correct this
    

Example:

```javascript
const user = {
    name: "Ashish",
    greet() {
        console.log(this.name) 
    },
}

const button = user.greet;

button();
```

This may lose the correct `this`.

Using `bind()`:

```javascript
const button = user.greet.bind(user)

button()
```

Now this always points to user.

## Real Difference Between call, apply, and bind

| Method | Calls Function Immediately | Arguments Style | Returns New Function? |
| --- | --- | --- | --- |
| call | Yes | Separate arguments | No |
| apply | Yes | Array of arguments | No |
| bind | No | Separate arguments | Yes |

## Simple Visual Understanding

Function → Caller Relationship:

*   this
    
    ```plaintext
    user.greet()
    
    caller -> user
    this -> user
    ```
    
*   call
    
    ```plaintext
    greet.call(user, 'Pankaj', 26);
    
    Caller manually set to user2
    this = user2
    ```
    
*   apply
    
    ```plaintext
    greet.apply(user, ["Delhi", "India"])
    
    Caller manually set to user2, arguments passed as array
    this = user2
    ```
    
*   bind
    
    ```plaintext
    const fn = greet.bind(user)
    
    Creates a new function
    this = user
    ```
    

## Final Thoughts

Understanding this is one of the biggest turning points in JavaScript.

Once you understand the concept of who is calling the function, how `call()`, `apply()` , and `bind()` control `this`

JavaScript becomes much easier to read and debug.

The best way to master these concepts is to practice small examples repeatedly.

Start simple, experiment with different callers, and everything will begin to click naturally.  

Follow the series to learn more about Javascript.
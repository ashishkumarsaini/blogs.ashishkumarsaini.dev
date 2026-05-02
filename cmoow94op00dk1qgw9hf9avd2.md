---
title: "Destructuring in JavaScript"
seoTitle: "Master JavaScript Destructuring: Arrays and Objects"
seoDescription: "Learn JavaScript destructuring with simple examples. Understand arrays, objects, defaults, and write cleaner code easily."
datePublished: 2026-05-02T22:09:08.090Z
cuid: cmoow94op00dk1qgw9hf9avd2
slug: destructuring-in-javascript
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/7a6dffdb-a58a-44e6-a435-834c94928186.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/1e1fe771-f53a-493b-9453-1e58b993860b.png
tags: js, destructuring-in-javascript, objects-in-js, array-js

---

JavaScript gives us a feature called destructuring. It makes working with arrays and objects much cleaner and less repetitive.

If you have ever written code like this:

```javascript
const user = { name: "Ashish" age: 22 };

const name = user.name;
const age = user.age;
```

You already know the pain of writing the same object while extracting each value from the object

Let’s fix that.

## What is destructuring?

Destructuring is a syntax which is introduced in ES6 (ECMAScript 2015), that allows to extract values from arrays or objects into variables in a simple, shorter, and cleaner way.

Update the same example using destructuring:

```javascript
const user = { name: "Ashish" age: 22 };

const {name, age} = user;
```

Now JavaScript does the work for you. You do not have to write [`user.name`](http://user.name) over.

## Destructuring Objects

Object destructuring is based on keys (property names).

Before ES6,

```javascript
const user = {
  name: "Ashish",
  age: 22
};

const name = user.name;
const age = user.age;
```

After (Destructuring):

```javascript
const { name, age } = user;
```

Renaming Variables: We can also rename the variables on the go, while destructuring.

```javascript
const { name: username } = user;
```

## Destructuring Arrays

Array destructuring works based on position (also called index).

Before ES6,

```javascript
const colors = ['red', 'blue', 'pink'];

const first = colors[0];
const second = colors[1];
const third = colors[2];
```

After ES6, destructuring is much easier.

```javascript
const colors = ['red', 'blue', 'pink'];

const [first, second, third] = colors;
```

Just in case, we do not want a second color:

```javascript
const colors = ['red', 'blue', 'pink'];

const [first, , third] = colors;
```

This is fine for one or a maximum of 2 indexes, but we should not skip multiple indexes by keeping empty for so many positions in between. In that case, we can use the older approach `const color = colors[10];`

## Why Use Destructuring?

*   Less Repetitive Code
    
*   Cleaner and more readable
    

## Final Thoughts

Destructuring is one of those features that:

*   Reduces boilerplate
    
*   Improves readability
    
*   Makes your code feel more modern
    

Start using it in small places, and soon it’ll become second nature.

Follow series to learn more about Javascript.
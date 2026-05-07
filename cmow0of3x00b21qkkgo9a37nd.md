---
title: "Understanding this in JavaScript"
seoTitle: "A Beginner-Friendly Guide to this in JavaScript"
seoDescription: "Understand JavaScript this in the simplest way with easy examples, objects, functions, classes, and calling context."
datePublished: 2026-05-07T21:47:23.135Z
cuid: cmow0of3x00b21qkkgo9a37nd
slug: understanding-this-in-javascript
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/14a845a7-9359-4073-9698-e02880817620.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/39822f52-b75b-4f71-9160-3b9e95b11c3d.png
tags: javascript, this-keyword, this-in-js

---

If you have started learning Javascript, you might have already seen the `this` keyword. It might be so confusing at first, but it is required knowledge.

Honestly, almost every JavaScript developer gets confused about `this` at first. You don’t need to learn complicated internals or memorize weird rules to understand it.

A simple way to think about `this` is:

`this` **usually refers to whoever is calling the function.**

That is it.

Once this idea clicks, most examples start making sense.

## What does `this` actually represent?

`this` is a special keyword in JavaScript. The value of `this` depends on how the function is being called, instead of where it is written.

Only **who is calling** matters most of the time. The output changes based on the context.

## `this` in the global context

Let’s start simple. Try to run the code below at different places:

```javascript
console.log(this);
```

If you run this inside the browser, you’ll see:

```javascript
window
```

Because in the browser, the global object is `window`.

So basically:

```javascript
this === window; // true
```

At the global level, `this` points to the global object.

## `this` inside an object

Now, let’s look at the most common use case of `this`

```javascript
const user = {
  name: "John",

  greet() {
    console.log(this.name);
  },
};

user.greet(); // John
```

Are you wondering why the output is "John"? Because `user` is calling `greet()`.

So inside that function, `this` represents the `user`.

Remember, `this` refers to whoever is calling, and again, the user here is calling the greet function.

Also, a very easy trick is to look to the left of the dot.

```javascript
user.greet()
```

The thing before the dot is usually what `this` becomes.

## `this` inside a normal function

Now, let's see how `this` behaves inside the usual functions.

```javascript
function showThis() {
  console.log(this);
}

showThis();
```

Here, no object is calling the function.

It’s just being called directly.

So, the output of `this` would be `undefined`. Because nobody is calling the function.

There’s no object connected to it.

## Same function, different `this`

This is where things become interesting.

```javascript
function sayName() {
  console.log(this.name);
}

const student = {
  name: "Rahul",
  sayName,
};

const teacher = {
  name: "Priya",
  sayName,
};

student.sayName();
teacher.sayName();
```

Output:

```plaintext
Rahul
Priya
```

The function is exactly the same for both objects.

But the caller changes.

So `this` changes too.

```javascript
student.sayName(); // this = student

teacher.sayName(); // this = teacher
```

This is the most important thing to remember about `this`.

## `this` in classes

If you have understood the above behaviour, `this` will be easier to understand in classes.

Example:

```javascript
class User {
  constructor(name) {
    this.name = name;
  }

  greet() {
    console.log(`Hello ${this.name}`);
  }
}

const user1 = new User("John");

user1.greet(); // Hello John
```

Here, when a new object of the User class has been created with the arguments "John", a new this has been created.

So, this line:

```javascript
this.name = name
```

becomes

```javascript
user1.name // John
```

## Easiest way to understand `this`

Whenever you see `this`, ask:

> “Who is calling this function?”

That question solves most confusion.

Example:

```javascript
user.login(); // this -> user;
```

`user` is calling the function.

But, if only login function is called:

```javascript
login(); // this -> undefined
```

Nobody is calling it an object method.

So `this` becomes `undefined` in strict mode.

## Simple diagram idea

You can visualize it like this:

```plaintext
user  ─────► greet()

Inside greet():
this = user
```

Another one:

```plaintext
No object ─────► showThis()

Inside showThis():
this = undefined
```

## Final thoughts

The reason `this` feels confusing because its value changes.

But once you stop thinking about *where the function is written* and start focusing on *who is calling the function*, things become much clearer.

So remember this one line:

`this` is usually the caller of the function

And that single idea will help you understand most `this` examples in JavaScript.
---
title: "Understanding Variables and Data Types in JavaScript"
seoTitle: "JavaScript Variables and Datatypes explained for Beginners"
seoDescription: "Understand JavaScript variables clearly with practical examples, exercises, and explanations for new developers."
datePublished: 2026-03-11T21:18:02.792Z
cuid: cmmmjj4th00ir2cp040pwe3zp
slug: js-variables-and-datatypes
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/12dcd61e-377e-43a2-9d63-a2d9d9dd496f.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/931139c1-2037-4d65-b3b7-a69041c77554.jpg
tags: js, javascript, js-data-type, js-datatypes

---

Let's imagine you and your friends are moving to a city for your new job. Both of you have packed the necessary items that would be needed initially in the new city. You have packed your bags with labels, keeping in mind which item is in which bag. However, your friend has just mixed up all the things and thrown them into the bags. On your first day of the job, both of you start getting ready in the morning to reach the office on time.

Now, what will happen? Your friend won't remember which bag the required item is in. If he had labeled everything, it wouldn't be a mess for him.

So, think of a JavaScript variable like a box used to store things in real life.

## How to declare the variables?

Javascript has three keywords used to declare variables. These are:

1.  let
    
2.  const
    
3.  var
    

### Declaring a variable with let keyword

let is used to declare variables whose value might change later.

Example:

```javascript
let count = 10;

console.log(count); // 10

count = 20;

console.log(count) // 20
```

In the above example, the value of `count` the variable changes from 10 to 20.

### Declaring a variable with the const keyword

const is used to declare such variables, whose value is initialized once at the time of declaration and cannot be changed later.

Example:

```javascript
const count = 10;

console.log(count); // 10

count = 20; // Error: Uncaught SyntaxError: 
            // Identifier 'count' has already been declared
```

Before using const, make sure that the value of the variable will not change.

### Declaring a variable with the var keyword

var is an old way of declaring variables, which has been replaced in modern JavaScript by let and const.

```javascript
var count = 10;

console.log(count); // 10

count = 20;

console.log(count) // 20
```

The value can also be initialized/updated later as seen in the above example.

### Rules for variable names

*   Should start with a letter, `_` or `$` . Cannot start with a number.
    

```javascript
const name = "Ashish";
const $age = 20;
const $gender = 'M';

const 1age = 10; ❌
```

*   Cannot Contain Spaces
    

```javascript
const first name = "Ashish"; ❌
```

*   Only Letters, Numbers, `_`, and `$` Allowed
    

```javascript
const first_name = "Ashish";
const profileLink1 = 'https://www.ashishkumarsaini.dev';

const profileLink-2 = 'https://linkedin.com/in/devaksaini/'; ❌
```

*   Cannot use reserved JavaScript keywords
    
*   Case sensitive
    

```javascript
const value = 10;
const valuE = 20;
const VALUE = 30;

console.log(value); // 10
console.log(valuE); // 20
console.log(VALUE); // 30
```

## What are datatypes?

We understand that there are boxes to store something, which we call variables. But what are we going to store in that box?

Imagine you have a box where you store something, like apples.

*   The box → is the variable
    
*   The label on the box → is the variable name
    
*   The item inside the box → is the value
    

Here, apple is a datatype. Similarly, we can store multiple types of things in the boxes.

In JS, we call them datatypes.

![](https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/78bdfbfd-ff61-415f-bf22-f9d2e987e68d.png align="center")

There are two types of datatypes:

1.  Primitive Datatypes
    
2.  Non-primitive Datatypes
    

### Primitive Datatypes

Think of a primitive data type as simple values stored inside the variable. Primitive datatypes are immutable, meaning their value can be replaced but not changed directly.

> *Note: You might get confused here about the immutability of the datatype.*
> 
> *Here we are talking about the immutability of datatype not variable. Variable themselves are mutable.*
> 
> *You cannot alter the number 5 to make it 6. Instead you replace the value of variable containing 5 to 6.*
> 
> ```javascript
> let a = 'apple'; // the value 'apple' will always 
>                  // be 'apple'. datatype is immutable
> a = 'orange';    // new value 'orange' re-assign to 
>                  // variable. variable is mutable
> ```

There are multiple primitive datatypes:

### Number

Used to store **numeric values** (integers or decimals).

```javascript
const count1 = 10;
const count2 = 2.5;
const count2 = -10;

console.log(count1); // output: 10
console.log(count2); // output: 2.5
console.log(count2); // output: -10

console.log(typeof count1); // 'number'
```

### String

User to store text values.

```javascript
const text1 = 'Hey, this is a text';
const text2 = `2 + 3 = ${2+3}`; // template literals

console.log(text1); // output: 'Hey, this is a text'
console.log(text2); // output: '2 + 3 = 5'

console.log(typeof text1); // 'string'
```

### Boolean

Use to store true or false.

```javascript
const isRegistered = true;
const isLoggedIn = false;

console.log(isRegistered); // output: true
console.log(isLoggedIn); // output: false

console.log(typeof isRegistered); // 'boolean'
```

### BigInt

Used to store large numbers beyond the number limits. Adding `n` to an integer literal makes it BigInt. It is used to represent numbers larger than `Number.MAX_SAFE_INTEGER`  
`(2^53 − 1 → 9007199254740991).`

```javascript
const count = 123456n;

console.log(count); // 123456n

console.log(typeof count); // 'bigint'
```

### Undefined

Undefined is defined as having no value.

```javascript
let sum;

console.log(sum); // output: undefined

console.log(typeof sum); // 'boolean'
```

### Null

Null is defined as having an empty value.

```javascript
let count = null;

console.log(count); // output: null

console.log(typeof count); // 'object'
```

## What is the scope in JS?

Scope defines where a variable can be accessed in a program.

Real World Analogy:

*   Some things are placed inside each room of your house.
    
*   Some things are placed in the common area of all rooms.
    

Types of scope:

1.  Block scope (`let` and `const`): Variables that are declared in any block or we can say inside any `{}` (curly braces).
    
2.  Function scope: Variables declared inside a function can only be used inside that function.
    
3.  Global Scope: Variable which are declared outside of a block or function scope. It will be accessible to all functions and blocks.
    

```markdown
_________________________________________________________________
| const name = 'Pankaj';  // global variable                    |
| const age = 25;         // global variable                    |
|                                                               |
| if(age == 25) {                                               |
|                                                               |
| ---------Block Scope-----------------                         |
| |                                    |                        |
| | const isSubscriber = true;         | isSubscriber will only |
| | console.log(isSubscriber); // true | accessible inside this |
| |                                    | block                  |
| |                                    |                        |
| | console.log(name); // Pankaj       | name is accessible.    |
| |                                    | as global variable.    |
| --------------------------------------                        |
|                                                               |
| }                                                             |
|                                                               |
|                                                               |
| function sum() {                                              |
|                                                               |
| -------Function Scope-----------------                        |
| |                                    |                        |
| | const isVerified = false;          | isVerified will only   |        
| | console.log(isVerified); // false  | accessible inside this |
| |                                    | function               |
| |                                    |                        |
| | console.log(age); // 25            | age is accessible.     |
| |                                    | as global variable     |
| --------------------------------------                        |
|                                                               |
| }                                                             |
|                                                               |
|                                                               |
| console.log(name); // Pankaj                                  |
| console.log(age); // 25                                       | 
|                                                               |                                              
| console.log(isSubscriber); ❌ Uncaught ReferenceError:        |
|                               isSubscriber is not defined     |
| console.log(isVerified);   ❌ Uncaught ReferenceError:        |
|                               isVerified is not defined       |
|                                                               |
-----------------------------------------------------------------
```

**Variables and Datatypes** are the fundamental topics to learn before starting learning any language. Understanding and practicing the topics that we have covered in this blog will help you with further topics.

Assignment for practice:

Open the console in the devtools of any browser by right-clicking on any page (in most of the browsers, ex: Chrome) and selecting the Inspect option.

Try to create the variables mentioned below:

1.  name
    
2.  age
    
3.  isStudent
    

Try to play around using let, var, and const to declare variables and changing the declared type from var -> let, let -> const, and observe the behaviour changes of each declaration type.

Also, try to put them in a block and access those variables outside the block to see the errors in real-time.

Follow this series to learn more about Javascript!
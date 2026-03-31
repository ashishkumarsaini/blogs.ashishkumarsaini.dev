---
title: "Arrow Functions in JavaScript (Beginner-Friendly Guide)"
seoTitle: "Arrow Functions in JavaScript Explained"
seoDescription: "Learn arrow functions in JavaScript with simple examples. Understand syntax, implicit return, and differences from normal functions."
datePublished: 2026-03-23T04:16:51.600Z
cuid: cmn2oc3nx00cs1qlsb1nzag19
slug: arrow-functions-in-javascript
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/df9b52f8-3678-415d-8585-0dac364068c0.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/136d3d9f-b870-401e-af4b-2e9e86c414be.png
tags: javascript, js-arrow-functions, js-arrow

---

## Why arrow functions?

Before arrow functions, writing a function felt like writing duplicate code again and again.

Function Before Arrow Functions:

```javascript
function add(a, b) {
  return a + b;
}
```

Arrow function syntax:

```javascript
const add = (a, b) => a + b;
```

Benefits of using arrow functions:

1.  Clear Syntax
    
2.  Easier to read
    
3.  Less Code than normal functions
    

That's why you can see arrow functions are widely used in modern Javascript.

## What Are Arrow Functions?

Arrow functions were introduced in ES6 (ES2015) to make code easier and more readable. It is a shorter way of writing functions.

### Basic Arrow Function Syntax

```javascript
const functionName = (parameters) => {
    // write function logic here  
};
```

Example:

```javascript
const greet = () => {
  console.log("Hello!");
};
```

### Arrow Function with One Parameter

If there is only one parameter, you can skip the parentheses.

```javascript
const square = num => {
  return num * num;
};
```

### Arrow Function with Multiple Parameters

If there are **multiple parameters**, parentheses are required.

```javascript
const add = (a, b) => {
  return a + b;
};
```

## Implicit Return vs Explicit Return

### Explicit Return (using `return`)

Explicit return in arrow functions means it uses the return keyword inside the function body to return the final result. It is used when the function's body requires multiple statements to calculate the result.

```javascript
const multiply = (a, b) => {
  return a * b;
};
```

### Implicit Return (no `return` keyword)

The function result can also be returned without the return keyword by removing the function curly braces. This approach will only be applicable where the function will calculate the value in a single statement.

```javascript
const multiply = (a, b) => a * b;
```

## Converting Normal Function → Arrow Function

Normal Function:

```javascript
function greet(name) {
  return "Hello " + name;
}
```

Arrow Function:

```javascript
const greet = name => "Hello " + name;
```

## Arrow Function vs Normal Function

| Feature | Normal Function | Arrow Function |
| --- | --- | --- |
| Syntax | Longer | Shorter |
| `this` | Own `this` | Inherits `this` |
| Use Case | General-purpose | Short functions, callbacks |

> For beginners: Use arrow functions for short and simple tasks

## Simple Examples

*   Greeting
    

```javascript
const greet = name => "Hello " + name;
```

*   Addition
    

```javascript
const add = (a, b) => a + b;
```

*   Square
    

```javascript
const square = num => num * num;
```

Using an Arrow Function with `map()`

```javascript
const numbers = [1, 2, 3, 4];

const squares = numbers.map(num => num * num);

console.log(squares); // [1, 4, 9, 16]
```

## Assignment

Try these on your own 👇

1.  Write a normal function to calculate the square of a number
    
2.  Rewrite it using an arrow function
    
3.  Create an arrow function that checks if a number is even or odd
    
4.  Use an arrow function inside `map()` on an array
    

## Arrow Function Breakdown

```javascript
const add = (a, b) => a + b;
```

*   `const add` → function name
    
*   `(a, b)` → parameters
    
*   `=>` → arrow syntax
    
*   `a + b` → returned value
    

## Conclusion

*   Arrow functions make your code.
    
*   Cleaner
    
*   Shorter
    
*   More modern
    

Follow the series for more blogs!
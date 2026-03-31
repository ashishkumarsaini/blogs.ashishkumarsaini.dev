---
title: "Javascript Function Declaration vs Function Expression: What’s the Difference?"
seoTitle: "JavaScript Functions Explained: Declarations vs Expressions"
seoDescription: "Learn JavaScript functions from scratch with simple examples. Understand function declarations, expressions, hoisting, and when to use them."
datePublished: 2026-03-21T13:07:48.371Z
cuid: cmn0cf76600051qmffb3bddqh
slug: javascript-function
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/a22dc3df-d503-467f-b716-28b45d731478.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/bd1a1f13-d76d-41f5-9834-492a2e847e6f.png
tags: javascript, js-functions

---

While you start writing programs for real world problems, you might have notices that there are many actions which need to be perform multiple times. For that you might have write duplicate code at separate places in the code.

That’s where functions come in.

## What are functions? Why we need functions?

Functions are a piece of code written that can perform a specific task. There are a code blocks which can be reusable at multiple places.

Instead of writing same logic to separate places you can it inside a function and use it where ever you need it.

### Real life analogy

Imagine a coffee machine ☕️

Actions perform in a coffee machine:

1.  Press the button
    
2.  Grinding
    
3.  Brewing
    
4.  Filtering
    
5.  Gives coffee
    

These are all the separate methods done by the coffee machine.

Examples: Without function:

```javascript
const sum1 = 1 + 2; // 3
const sum2 = 2 + 3; // 5
const sum3 = 3 + 4; // 7
const sum4 = 4 + 5; // 9
```

You can see we have the write the logic to add the number multiple times. Instead of this we can write a function sum which can return the sum of two number. We just had to provide the two numbers to the functions.

Examples: With function:

```javascript
function sum (number1, number2){
    return number1 + number2;
}

const sum1 = sum(1, 2); // 3
const sum2 = sum(2, 3); // 5
const sum2 = sum(3, 4); // 7
const sum2 = sum(4, 5); // 9
```

## How to create functions?

We can create functions by different ways:

1.  Function Declaration Syntax
    
2.  Function Expression Syntax
    

Let's discuss them one by one:

## Function Declaration Syntax

This is the most common way of creating the functions:

```javascript
function sum (number1, number2) {
    return number1 + number2
}
```

Key points:

1.  `function` keyword
    
2.  name of the functions (`sum`)
    
3.  Can be called anywhere (explained more later in this blog)
    

## Function Expression Syntax

In this approach, a function is stored in a variable:

```javascript
const sum = function (number1, number2) {
    return number1 + number2
}
```

Key points:

1.  Function is declared using `function` keyword.
    
2.  Function has no name.
    
3.  Function reference is stored in a variable. A variable should have a name.
    
4.  Can be called using the variables. In this case, you can call `sum()` as it stores the reference of the function. Ideally, the function is called
    

### Declaration vs Expression (Side-by-Side)

| Feature | Function Declaration | Function Expression |
| --- | --- | --- |
| Syntax | `function add() {}` | `const add = function() {}` |
| Hoisting | ✅ Fully hoisted | ❌ Not fully hoisted |
| Usage before definition | ✅ Works | ❌ Error |
| Common use | General functions | Callbacks, dynamic logic |

## Hoisting in Functions

Let's first understand what hoisting is:

Hoisting means: javascript moves declarations to the top before execution.

Example:

```javascript
console.log(number1); // undefined

var number1 = 10;
```

You might be wondering that `console.log(number1)` should give an error instead of printing `undefined`. In Javascript, this is possible because of the concept of **hoisting.**

Now try to run the logic below in the browser console dev tool or by creating a JS file and running it using `node <filename.js>`.

```javascript
console.log(number2);
// ReferenceError: Cannot access 'number2' before initialization

const number2 = 20;
```

```javascript
console.log(number3);
// ReferenceError: Cannot access 'number3' before initialization


const number3 = 30;
```

Now, you can see the error while executing this code.

Same applicable on the function.

Hoisting works in declaration syntax:

```javascript
const result = sum(1, 2);
console.log(result); // 3

function sum (number1, number2){
    return number1 + number2;
}
```

Hoisting doesn't work in declaration syntax:

```javascript
const result = sum(1, 2);
console.log(result);
// ReferenceError: Cannot access 'sum' before initialization

const sum = function (number1, number2){
    return number1 + number2;
}
```

## When to Use What?

### Use Function Declaration when:

*   You want simple, reusable functions
    
*   You need to call it anywhere in your code
    
*   You want a cleaner structure
    

### Use Function Expression when:

*   You’re passing functions as arguments (callbacks)
    
*   You want more control over execution
    
*   You’re working with modern patterns (like arrow functions) (Arrow functions we can study in the next blog)
    

## Execution flow of function call

You can also read about Javascript code execution in detail in the blog "**Understanding JavaScript Global & Local Execution Context".**

For functions, we can understand it stepwise. When a JS code is been executed:

1.  Javascript scans all the code
    
2.  Hoist function declaration on top
    
3.  Start execution line by line
    
4.  When executing the code, if the function called is hoisted, it will execute that function.
    

## Assignment (Try It Yourself)

1.  Write a function declaration that multiplies two numbers and returns the result.
    
2.  Write the same logic using a function expression approach.
    
3.  Call both the functions and try to re-run the logic by updating the values passed to the variable.
    
4.  Call both the functions before they are defined and try to observe the output (error/result).
    

## Conclusion

Functions are the building blocks of any program. You should know that the functions are used for:

1.  Reusability
    
2.  Combining Logic
    
3.  Make code clean and readable
    

Follow my Javacript series to learn more!
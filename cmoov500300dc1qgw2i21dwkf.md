---
title: "Callbacks in JavaScript: Why They Exist"
seoTitle: "JavaScript Callback Functions Explained Simply"
seoDescription: "Learn JavaScript callbacks with simple examples, async use cases, and callback hell explained clearly for beginners."
datePublished: 2026-05-02T21:37:55.782Z
cuid: cmoov500300dc1qgw2i21dwkf
slug: callbacks-in-javascript
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/12890e26-3720-43dc-9827-012d9d61beb5.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/4a98f8da-6ca3-413e-8cb9-c0db35455f5c.png
tags: javascript, callbacks, callback-in-js

---

Javascript is a very powerful language not just because if what is can do, but how it actually does the things. One of the core and fundamental concept of Javascript is callbacks which is widely used in production.

Let's break it down.

## Function as values

Javascript is one of the language which supports functions as values.

In programming, a language is said to treat functions as values when it supports first class functions. This means functions can be assigned to variables, passed as arguments to other functions, and returned from other functions, just like any other data type.

Examples:

*   Stored in variables
    
    ```javascript
    // Regular functions
    function message(name){
        return `Hey ${name}!`;
    }
    
    const greet = message;
    console.log(greet('Rahul')); // Hey Rahul!
    
    //Arrow functions
    const sum = (a, b) => {
        return a + b;
    }
    
    console.log(sum(1, 2)); // 3
    ```
    
*   Pass them in arguments
    
    ```javascript
    function calculate(num1, num2, action){
        return action(num1, num2)
    }
    
    function sum(value1, value2){
        return value1 + value2;
    }
    
    function difference(value1, value2){
        return value1 - value2;
    }
    
    calculate(3, 2, sum);       // return 5
    calculate(3, 2, difference) // return 1
    ```
    
*   Return functions from another functions
    
    ```javascript
    function greet(name){
        function message(){
            return `Welcome ${name}!`;
        }
        
        return message;
    }
    
    const messageFunction = greet('Rahul'); 
    messageFunction(); // Welcome Rahul
    ```
    

## What is a callback function?

A callback function is a simple function that is passed to another function to be executed later.

```javascript
// functio
function processAction(callback){
    const message ='Machine is  ';
    callback(message);    
}

function brewCoffee(message){
    console.log(`${message}: brewing coffee!`)
}

function startingMachine(message){
    console.log(`${message}: starting!`)
}


processAction(startingMachine); // Machine is starting!
processAction(brewCoffee);      // Machine is brewing coffee!
```

In the above example, what happened is

*   `processAction` -function accepting another function as a callback.
    
*   `brewCoffee` - a function that will be passed later as a callback
    
*   `startingMachine` - a function that will be passed later as a callback
    

Now,

*   when `processAction(startingMachine)` is called with `startingMachine` as callback, it has been called with `'Machine is'`. That string is passed to startMachine function argument and printed as 'Machine is starting!'.
    
*   Same for `processAction(brewCoffee)`
    

## Why Do We Use Callbacks?

Callbacks are specially used in asynchronous programming.

Javascript has a behaviour of not waiting for long operations until we program them to wait (Example: API calls). Callbacks are used in such cases that when the execution is completed/failed, callbacks are fired.

```javascript
console.log('Start')

setTimeout(() => {
  console.log("This runs later");
}, 2000);

console.log('End');

/*
* Output
*
*
*    Start
*    End
*    This runs later
*
*/
```

Here, `setTimeout` has a callback function that is executed after 2 seconds.

## Common use cases

1.  **Array Methods**  
    You have seen the callbacks in the pre-defined methods of the array. One of them is array.map.  
    
    ```javascript
    const arr = [1, 2, 3, 4, 5];
    
    const doubledArr = array.map((num)=> num * 2);
    
    console.log(doubledArr); // [2, 4, 6, 8, 10]
    ```
    
    Here, `num => num * 2` is a callback.
    
2.  **Event Handling**  
    If you have worked with DOM event handlers, you must have seen `addEventHandler`.  
    
    ```javascript
    const button = document.getElementById('btn');
    
    button.addEventHandler('click', () => {
        console.log('Button clicked!');
    });
    ```
    
    In above example, when the button is clicked, `'Button clicked!'` will be printed. Here, two arguments has been passed to `addEventHandler`
    
    *   `'click'` -> string
        
    *   callback with `console.log('Button clicked!')`
        
3.  **Async Operations**  
    In JS, we fetch data from an API, which is also an example of asynchronous programming.
    
    ```javascript
    const fetchData = (callback) => {
        fetch('api-endpoint')
            .then((data) => callback(data))
    }
    
    const callAfterComplete = (data) => {
        console.log(data);
    }
    
    fetchData(callAfterComplete);
    ```
    

## Understanding Problem: Callback Hell

Callback hell is nothing, just nested callbacks. When callbacks depend on each other, they can become deeply nested and hard to manage.

```javascript
getData(function(x){
    getMoreData(x, function(y){
        getMoreMoreData(y, function(z){ 
            ...
        });
    });
});
```

Here,

*   getData will execute and will be called with the callback having `x` argument.
    
*   Only if the `getData` is executed successfully, the inner function `getMoreData` will execute with arguments - `x` and a function with `y`.
    
*   Only if the `getMoreData` is executed successfully, the inner function getMoreMoreData will execute with arguments - `y` and a function with `z`.
    

**Issues in callback hell**

1.  Structure grows horizontally like a pyramid, which reduces code readability.
    
2.  Make debugging complex and error handling difficult.
    

## Final Thoughts

Callbacks are simple in concept but incredibly powerful:

*   They enable async behavior
    
*   They make functions reusable
    
*   They form the base for modern JS patterns
    

But like any tool, they need to be used wisely—especially when nesting starts to grow.
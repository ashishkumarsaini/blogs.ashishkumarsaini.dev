---
title: "Error Handling in JavaScript: try, catch, finally"
seoTitle: "Error Handling in JavaScript: try, catch, finally"
seoDescription: "Learn JavaScript error handling with try, catch, finally, and custom errors using simple examples and beginner-friendly explanations."
datePublished: 2026-05-09T18:55:15.758Z
cuid: cmoypersc01qa2em7ayqb1m3r
slug: error-handling-in-javascript
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/fdc064af-bce3-432b-9dd4-f0218492d17b.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/151d28c2-7578-414c-8f07-e3e667d87fbf.png
tags: javascript, error-handling, error-handling-js, js-error-handling

---

While writing a Javascript code, no matter how carefully you have written the code but once the user input a invalid data and the API fails, the application might crash at runtime due to some edge case or unexpected behaviour.

That's why the error handling is important skills for every Javascript developer. Good error handling makes applications more stable, easier to debug, and much more user-friendly.

In this article we will understand how error works in Javascript and learn more about how to tackle those scenarios using try, catch and finally.

## What Are Errors in JavaScript?

Errors are problems that occur while the code is running. These problems can stop the normal execution of the program.

For example:

```javascript
console.log(userName);

// ReferenceError: userName is not defined
```

Here, JavaScript throws an error because of the variable does not exist.

Another example:

```javascript
const user = null;

console.log(user.name);

// TypeError: Cannot read properties of null
```

These are called runtime errors because they happen while the program is running.

## Common Types of JavaScript Errors

1.  ReferenceError  
    Occurs when a variable does not exist.
    
    ```javascript
    console.log(age);
    ```
    
2.  TypeError  
    Occurs when a value is used incorrectly.
    
    ```javascript
    const num = 10;
    
    num.toUpperCase();
    ```
    
    Numbers do not have toUpperCase().
    

3.  SyntaxError  
    Occurs when JavaScript syntax is invalid.
    
    ```javascript
    if(true {
        console.log("Hello");
    }
    ```
    
    Missing closing bracket.
    

## Why Error Handling Matters

Imagine a shopping website where a single error can crash the entire website. Once crashed, the user will immediately leaves the website without purchasing.

To handle this, developer has to handle the error gracefully. This means:

*   Showing a meaningful message
    
*   Prevent app crashes
    
*   If once part of website is crashed, should be handled that it will not crash entire website
    
*   For developers, make debugging easier. Error handling also helps developers quickly identify problems during development.
    

Without proper error handling, debugging large applications becomes extremely difficult.

## Using try and catch in JavaScript

JavaScript provides try and catch blocks to safely handle errors.

Basic syntax:

```javascript
try { 
// risky code 
} catch(error) { 
// handle error 
}
```

The code inside try block will get execute first. If any error occurs, the execution of try block code immediately stops and the control move to the catch block.

The error object now contains the error that occurred in the try block.

Example:

```javascript
try {
  const user = null;

  console.log(user.name);
} catch(error) {
  console.log("Something went wrong");
  console.log(error.message);
}

// Output
// Something went wrong
// Cannot read properties of null
```

Instead of crashing the application, the error is handled properly.

## Understanding Graceful Failure

Graceful failure means handling errors in a controlled way.

*   Displaying the message "App Crashed!" to the user is a bad practice.
    
*   "Unable to load your profile. Please try again later." - Displaying a custom message like this is a good user experience. The user should never see the technical errors.
    

That’s why developers use error handling to improve user experience.

## Understanding Error Object

Inside catch, JavaScript provides an error object.

Example:

```javascript
try { 
    console.log(data);
} catch(error) {
    console.log(error);
}
```

The error object contains useful information like:

1.  name
    
2.  message
    
3.  stack
    

Example:

```javascript
console.log(error.name); 
// ReferenceError

console.log(error.message);
// data is not defined
```

This information is very useful while debugging applications.

## The finally Block

Sometimes we want code to run in both cases, whether an error occurs or not.

That’s where finally is used.

Syntax:

```javascript
try {
    // code 
} catch(error) {
    // handle error 
} finally {
    // always runs
} 
```

Example:

```javascript
try {
    console.log("Trying...");
    riskyFunction(); 
} catch(error) {
    console.log("Error handled"); 
} finally {
    console.log("Execution completed");
}

// Trying...
// Error handled
// Execution completed
```

The finally block always runs.

### Where is finally useful

The finally block is commonly used for:

1.  Closing database connections
    
2.  Stopping loaders/spinners
    
3.  Cleaning resources
    
4.  Resetting states
    

Example:

```javascript
try {
    console.log("Fetching data...");
} catch(error) {
    console.log("API failed");
} finally {
    console.log("Hide loading spinner");
}
```

Even if the API fails, the loading spinner will still stop.

## Throwing Custom Errors

JavaScript also allows developers to create their own errors using throw. This is useful when we want to validate data manually.

Example" of throw const age = -5;

```javascript
try {
    if(age < 0) {
        throw new Error("Age cannot be negative"); 
    }
    console.log("Valid age"); 
} catch(error) {
    console.log(error.message); 
}
```

Output:

```plaintext
Age cannot be negative
```

Here, we manually created a custom error.

### Why Custom Errors Are Useful

Custom errors help developers:

1.  Validate user input
    
2.  Create meaningful messages
    
3.  Improve debugging
    
4.  Control application flow
    

For example:

```javascript
throw new Error("Password must contain 8 characters");
```

This message is much clearer than a generic error.

## Conclusion

Errors are a normal part of programming. What matters is how we handle them.

JavaScript provides powerful tools like:

try catch finally throw

These features help developers build reliable and user-friendly applications.

Good error handling prevents crashes, improves debugging, and creates a smoother experience for users.

Instead of fearing errors, developers should learn how to handle them gracefully. That’s what makes applications truly production-ready.
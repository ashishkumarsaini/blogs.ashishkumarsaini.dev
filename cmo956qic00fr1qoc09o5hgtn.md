---
title: "String Polyfills and Common Interview Methods in JavaScript"
datePublished: 2026-04-21T21:34:54.134Z
cuid: cmo956qic00fr1qoc09o5hgtn
slug: string-polyfills-and-common-interview-methods-in-javascript

---

In Javascript, strings are used everywhere, but many developers do not know how they actually work behind the scenes.

When you call a method like `.toUpperCase()` on a string primitive, JavaScript creates a temporary wrapper object (using the `String` constructor) so the method can be executed. Once the operation is done, that object is immediately discarded, and the result is returned as a primitive.

## What Are String Methods?

String methods are the built-in functions that are used to manipulate and update the string.

Here are some of the string methods:

*   `toUpperCase()`
    
*   `toLowerCase()`
    
*   `slice()`
    
*   `substring()`
    
*   `includes()`
    
*   `split()`
    
*   `trim()`
    

These methods don’t modify the original string (because strings are immutable). Instead, they return a new string.

## How string method work internally?

Let's take an example `toUpperCase` and understand how it works.

When you call `string.toUpperCase()`

```javascript
const str = 'Hello';

str.toUpperCase();
```

1.  Javascript iterate over each character
    
2.  Convert that character into uppercase
    
3.  Build a new string
    

> Think of execution like this
> 
> Input String → Process Each Character → Apply Logic → Return New String

## What are polyfills?

Polyfills are a custom implementation of the built-in functions. It is mostly used to create the same functionality that built-in functions offer.

### Why Developers Write Polyfills?

*   Provide support for new methods in older browsers
    
*   Understanding internal logic
    
*   To practice the built-in methods logic by creating them of their own
    

Let's implement
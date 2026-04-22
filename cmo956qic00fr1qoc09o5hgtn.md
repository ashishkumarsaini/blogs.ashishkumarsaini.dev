---
title: "String Polyfills and Common Interview Methods in JavaScript"
seoTitle: "String pollyfills and related interview questions"
seoDescription: "This blog is about polyfills in JS using string examples. Also includes beginner-friendly polyfill examples with the related interview questions."
datePublished: 2026-04-21T21:34:54.134Z
cuid: cmo956qic00fr1qoc09o5hgtn
slug: string-polyfills-and-common-interview-methods-in-javascript
tags: js-strings, stringpolyfills, js-polyfills

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
    

### Polyfill Examples

Let's implement some polyfills for string methods

1.  **string.toLowerCase()**  
    Here I will be writing a custom polyfill for toLowerCase.
    
    ```javascript
    if(!String.prototype.toLowerCase){
        String.prototype.toLowerCase = function () {
            let result = "";
    
            // this refer to string on which method is called
            for (let char of this) {
                const code = char.charCodeAt(0);
    
                // a-z → A-Z
                if (code >= 97 && code <= 122) {
                    result += String.fromCharCode(code - 32);
                } else {
                    result += char;
                }
            }
    
            return result;
        };
    }
    ```
    
    This will only work if the browser doesn't support `string.toLowerCase`, it will use the polyfill `toLowerCase`
    
2.  `string.includes`
    
    ```javascript
    if(!String.prototype.includes){
        String.prototype.myIncludes = function(searchString) {
            return this.indexOf(searchString) !== -1;
        };
    }
    ```
    

## Common String Interview Questions

If you're preparing for interviews, these are must-practice:

1.  Reverse a String function without using built-in methods  
    Logic: Iterate over the string and append the new string with each character in an order so that the last character comes first.
    
2.  Check Palindrome  
    Logic: Reverse and create a new string. Check if both strings are equal or not.
    
3.  Count Characters  
    Logic: Use a "Map" or an object to store counts as you iterate through the string.
    
4.  Anagram Detection: Do two strings contain the same characters?  
    Logic: Sort both strings and compare them.
    

## Why Understanding Built-in Behavior Matters

Most developers stop at using methods. But in an interview, the interviewer tests:

*   How things work internally
    
*   Your problem-solving ability
    
*   Your understanding of edge cases
    

Understanding internals helps you in writing better code, debugging faster, and performing well in interviews.

Example questions:

1.  How does slice() differ from substring()?
    
2.  Why are strings immutable?
    
3.  How would you optimize a string search?
    

## Conclusion

If you want to stand out as a developer:

Don’t just use methods — understand them, practice writing polyfills, and solve real interview problems.

That’s where real growth happens.

Follow the series to learn more about Javascript.
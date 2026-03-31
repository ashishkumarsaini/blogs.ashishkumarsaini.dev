---
title: "Array Flatten in Javascript"
seoTitle: "Array Flattening in JavaScript Explained"
seoDescription: "Struggling with nested arrays? This guide explains JavaScript array flattening step by step with practical examples and common interview scenarios."
datePublished: 2026-03-26T19:29:20.149Z
cuid: cmn7v93wz028u2dmmd5ingtfh
slug: array-flatten-in-javascript
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/638f3690-8db6-46aa-a628-326d881b16a2.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/029b6928-2961-492d-80f6-5e3144f750a5.png
tags: javascript, flatten-array, array-method-js, array-js

---

You have read in the previous blog on datatypes that an array is a non-primitive data type that can contain various data types.

But have you ever wondered what would happen if an array contained another array? How are we going to handle this?

Understanding nested arrays and handling operations on them is an important skill, especially for problem-solving and is usually asked in interviews as well.

## What are nested arrays?

If an array contains a nested array, it is called a nested array.

Example:

```javascript
const nestedArray = [1, 2, 3, [4, 5, 6], 7, [8, [9, 10]]];
```

The above example might be confusing to see. Let me break it down to see multiple array properly.

```javascript
const nestedArray = [
    1,
    2,
    3,
    [4, 5, 6],
    7,
    [
        8, 
        [9, 10]
    ]
]
```

Now the values on each index can be seen clearly.

Values with respective index:

*   `0` -> `1` (`number`)
    
*   `1` -> `2` (`number`)
    
*   `2` -> `3` (`number`)
    
*   `3` -> `[4, 5, 6]` (`array`)
    
*   `4` -> `7` (`number`)
    
*   `5` -> `[8, [9, 10]]` (`nested array`)
    

## Why is flattening an array used?

Flattening an array means converting a multidimensional array to a single-dimensional array.

*   Extracting values from all nested arrays
    
*   Arrange them in a single array
    

This is an important concept needed when:

1.  Easier data processing
    
2.  Useful in APIs and transforming data
    
3.  Common in real-world scenarios (e.g., comments, categories with products)
    

Example:

```javascript
const categories = [
    ["p1", "p2", "p3"],
    ["p4", "p5"]
];
```

After flattening:

```javascript
const products = ["p1", "p2", "p3", "p4", "p5"];
```

## Different approaches to flatten arrays

There are multiple ways to flatten an array:

### Using in-build flat() method

An array has an in-built method `flat()`. This is the most common and simple approach.

```javascript
const array = [1, 2, [3, 4], [5, 6]];

const flatArr = arr.flat(Infinity);

console.log(flatArr); // [1, 2, 3, 4, 5, 6, 7]
```

### Using Recursion

Recursion is a way to call the same function repeatedly.

```javascript
const array = [1, 2, [3, 4], [5, 6]];

function flattenArray(arr) {
    let result = [];

    for (let item of arr) {
        if (Array.isArray(item)) {
            result = result.concat(flattenArray(item));
        } else {
            result.push(item);
        } 
    }

    return result; 
};

console.log(flattenArray([1, [2, [3, 4], 5]])); // [1, 2, 3, 4, 5]
```

### Using reduce()

```javascript
const array = [1, 2, [3, 4], [5, 6]];

const flattenArray = (arr) => {
    return arr.reduce((acc, item) => {
        if (Array.isArray(item)) {
            return acc.concat(flattenArray(item));
        }
        
        return acc.concat(item); 
    }, []); 
};

console.log(flattenArray([1, [2, [3, 4]]])); // [1, 2, 3, 4, 5]
```

## Common Interview Scenarios

You may be asked:

1.  Flatten only one level arr.flat(1);
    
2.  Flatten up to depth n
    
3.  Don’t use built-in methods. Use recursion or a stack approach.
    

Try to practice in any Javascript code editor.

## Conclusion

Flattening arrays is a fundamental concept in JavaScript that helps you:

*   Work with complex data structures
    
*   Improve problem-solving skills
    
*   Prepare for coding interviews
    

Start with `flat()` for simplicity, but master recursion for interviews.
---
title: "Understanding Arrays in JavaScript"
seoTitle: "JavaScript Arrays Basics for Beginners"
seoDescription: "This guide explains arrays with simple examples, diagrams, and exercises to help you understand indexing, updating elements, and looping."
datePublished: 2026-03-14T18:23:50.524Z
cuid: cmmqnmnsq01ho1qir6mfb0zcc
slug: understanding-arrays-in-javascript
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/523a92db-2219-41bf-95b7-80c1cd442132.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/8550ad64-2e9b-4f74-b25a-071d1e5c4f2b.png
tags: js, jsarray, js-array-basics

---

When we start learning programming, we usually store values in variables.

```javascript
let fruit1 = "Apple";
let fruit2 = "Banana";
let fruit3 = "Mango";
```

This works fine for a few values.  
But what if we need to store 20 fruits? 100 student marks? 1000 tasks?

Creating separate variables for each value becomes messy and hard to manage.

This is where arrays help us.

## What is an Array?

An array is a collection of data elements that can be of the same or different types. In an array, the individual elements of data are referred to as elements.

Example:

```javascript
let fruits = ["Apple", "Banana", "Mango"];
```

## Why Do We Need Arrays?

Arrays help us when we want to store multiple values together.

Common examples:

*   List of fruits
    
*   Student marks
    
*   Shopping list
    
*   Tasks in a to-do list
    
*   Comments on a post
    

Example:

```javascript
let marks = [78, 85, 92, 67, 88];
```

Instead of 5 variables, we store everything in one array.

## How to Create an Array

In JavaScript, arrays can be created using multiple ways:

1.  square brackets `[]` (beginner-friendly)
    

Example:

```javascript
let fruits = ["Apple", "Banana", "Mango"];
let numbers = [10, 20, 30, 40];
let data = ["Ashish", 22, true];
```

2.  Using the `Array` Constructor. You can also use the `new Array()` constructor.
    

*   Empty Array
    

```javascript
const emptyArrayConstructor = new Array();
```

*   Array with initial values
    

```javascript
const fruitsConstructor = new Array("apple", "banana", "cherry");
```

*   Array with a specified length: If a single number is passed, it creates an array with that number of empty slots, not a single-element array.
    

```javascript
const newArray = new Array(3); 
// Creates an array with 3 empty slots, not [3]
// But accessing newArray[0] gives undefined.
```

*   `Array.of()`**:** The `Array.of()` static method creates a new `Array` instance from a variable number of arguments, regardless of the number or type of the arguments.
    

```javascript
const singleNumberArray = Array.of(8); // Creates [8]
const multipleElementsArray = Array.of(1, 2, 3); // Creates [1, 2, 3]
```

*   `Array.from()`**:** The `Array.from()` static method creates a new, shallow-copied `Array` instance from an iterable or array-like object.
    

```javascript
// Create an array from a string
const fromString = Array.from("word"); // Creates ["w", "o", "r", "d"]

// Create an array with sequential numbers
const range = Array.from({ length: 5 }, (v, i) => i); // Creates [0, 1, 2, 3, 4]
```

### Understanding Array Index

Every element in an array has a position number called an index.

Array indexing starts from 0.

Example:

```javascript
const arr = ['Apple', 'Banana', 'Mango'];


Index:   0        1        2
        ----------------------
Array:  Apple   Banana   Mango
```

## Accessing Array Elements

If we want a specific element of an array we can access it by its index using square brackets.

Example:

```javascript
let fruits = ["Apple", "Banana", "Mango"];


console.log(fruits[0]); // Apple
console.log(fruits[1]); // Banana
console.log(fruits[2]); // Mango
```

So,

*   `fruits[0]` is the first element
    
*   `fruits[1]` is the second element
    
*   `fruits[2]` is the third element
    

## Updating Array Elements

We can use the index of the element to update the array.

Example:

```javascript
let fruits = ["Apple", "Banana", "Mango"];

fruits[1] = "Orange";

console.log(fruits); // ["Apple", "Orange", "Mango"]
```

In this case we replaced `Banana` with `Orange`.

## Array Length Property

Every array has a built-in property called `length`. This property tells us how many elements there are inside of the array.

Example:

```javascript
let fruits = ["Apple", "Banana", "Mango"];

console.log(fruits.length); // 3
```

## Looping Through an Array

If we don't want to manually print each element, we can use a loop.

Example:

```javascript
let fruits = ["Apple", "Banana", "Mango"];

for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}

// Output:
// Apple
// Banana
// Mango
```

Explanation:

*   Start at index `0`
    
*   Continue until `fruits.length`
    
*   Print each element.
    

This allows us to easily work with arrays of any size.

## Visualizing an Array

You can think of an array like boxes placed next to each other.

```javascript
Index →   0        1        2
        ----------------------
Value →  Apple   Banana   Mango
```

Or like memory blocks:

```plaintext
[0] → Apple
[1] → Banana
[2] → Mango
```

Each box has:

*   a position (index)
    
*   a value
    

## Assignment

Try solving the following exercises:

*   Define an array of 5 of your favourite movies
    
*   Print the first and the last movies
    
*   Update the second movie in the array and print the array
    
*   Use a for loop to print all the movies
    

## **Final Thoughts**

Arrays are one of the most important data structures in JavaScript.

They allow us to:

*   store a collection of data
    
*   access that collection using an index
    
*   alter that collection
    
*   Easily iterate through that collection
    

After learning the basics, you can learn to use the various array methods. Learning the basics will help you understand the array methods more easily. Master the basics first, and your future learning will be easier!

Follow the JS series to learn more about Javascript.
---
title: "JavaScript Array Methods Every Beginner Should Know"
seoTitle: "JavaScript Array Methods Explained"
seoDescription: "Learn essential JavaScript array methods like push(), pop(), map(), filter(), reduce(), and forEach() with simple examples, before/after outputs."
datePublished: 2026-03-17T20:13:32.861Z
cuid: cmmv1vard00qa2bjbdfkk2f7v
slug: javascript-array-methods
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/69fab99d-9ef7-4cd9-b701-04105d88ebf6.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/482415c7-edf8-41b7-8209-5234c77e0022.png
tags: jsarray, jsarraymethods, js-basic

---

When working with JavaScript, arrays are everywhere. They store lists of items like numbers, names, tasks, or products. But storing data is just the beginning. We often need to add items, remove items, change values, or filter data.

JavaScript has built-in array methods that simplify these tasks.

In this article, we will explore some of the most useful array methods with simple examples:

*   push() and pop()
    
*   shift() and unshift()
    
*   map()
    
*   filter()
    
*   reduce()
    
*   forEach()
    

You can try all examples directly in your browser console or Node.js.

Lets first understand the methods which are used to add or remove the data in an array:

## push()

The push() method adds a new element to the end of an array.

Example:

```javascript
let fruits = ["Apple", "Banana"];

const newLength = fruits.push("Mango");

console.log(newLength) // 3
console.log(fruits); // ["Apple","Banana","Mango"]
```

It returns the updated length of array.

Push is generally used when adding a new item to a list, such as adding a task to a to-do list.

## pop()

The pop() is used to remove the last element from the array.

Example:

```javascript
const items = ["Shoe", "Tshirt", "Trouser"];

const popItem = items.pop();

console.log(popItem); // 'Trouser'
console.log(items);   // ["Shoe", "Tshirt"]
```

It returns the element that is removed.

## shift()

The shift() method removes the first element of an array.

Example:

```javascript
const items = ["Shoe", "Tshirt", "Trouser"];

const shiftItem = items.shift();

console.log(shiftItem); // "Shoe"
console.log(items);     // ["Tshirt", "Trouser"]
```

It returns the item which is removed. This works same as Queues in real life

## unshift()

The unshift() method adds an item to the start of the array.

Example:

```javascript
const items = ["Shoe", "Tshirt", "Trouser"];

const popItem = items.unshift("Shirt");

console.log(popItem); // 4
console.log(items);   // [ 'Shirt', 'Shoe', 'Tshirt', 'Trouser' ]
```

It returns the new length of the array.

Let's understand the methods that are used to perform iteration (loop) on an array

## forEach()

forEach() is used to perform an action on each element of an array.

It accepts a callback function that accepts three arguments, provided by forEach itself.

*   value: element of array
    
*   index: position of element in array
    
*   array: complete array
    

forEach() runs a function for every item in the array.

Example:

```javascript
const numbers = [1, 2, 3]

numbers.forEach((num) => {
    console.log(num);
});

Output:
1
2
3
```

## Traditional Loop vs forEach()

for loop:

```javascript
let numbers = [1, 2, 3];

for (let i = 0; i < numbers.length; i++) {
    console.log(numbers[i]);
}
```

vs

forEach:

```javascript
let numbers = [1, 2, 3];

numbers.forEach(function(num) { 
    console.log(num); 
});
```

As we can see in the above example, forEach is more cleaner and easier to read and use.

## map()

map() creates a new array by updating each element based on the logic inside the callback.

> Assume map() to be turning a crate of fruit into a crate of juices.
> 
> The number of juice will remain same as the number of fruits.

It accepts a callback function that accepts three arguments, provided by map itself.

*   value: element of array
    
*   index: position of element in array
    
*   array: complete array
    

Example:

```javascript
const numbers = [1, 2, 3];

const doubledNumbers = numbers.map((num) => {
    return num * 2;
});

console.log(doubledNumbers);

Output: [2, 4, 6] // updated values

console.log(numbers);

Output: [1, 2, 3] // remains same
```

map() returns an updated elements array. Also, it doesn't update the original array.

## filter()

filter() creates a new array that only includes elements that satisfy the condition inside the callback function.

It accepts a callback function that accepts three arguments, provided by filter itself.

*   value: element of array
    
*   index: position of element in array
    
*   array: complete array
    

Example:

```javascript
const numbers = [3, 7, 10, 2];

const filteredNumbers = numbers.filter((num) => {
    if(num > 5){
        return true;
    }
    
    return false;
});

console.log(filtersNumbers);

Output: [7, 10]
```

So, returned array only includes those values for which callback return true.

### How filter() work?

Here:

*   For 3, the callback returns false. `filteredNumbers` doesn't contain 3
    
*   For 7, the callback returns true. `filteredNumbers` contain 7
    
*   For 10, the callback returns true. `filteredNumbers` contain 10
    
*   For 2, the callback returns false. `filteredNumbers` doesn't contain 2
    

## reduce()

reduce() combines all values of an array into a single value.

> Reduce is like combining flour, eggs, and sugar to bake one single cake.

Common use cases include:

*   total sum
    
*   calculating totals
    
*   combining data
    

Example:

```javascript
let numbers = [5, 10, 20];

let total = numbers.reduce((accumulator, value) => {
 return accumulator + value; 
}, 0);

console.log(total);

Output: 35
```

Returns the single value after the final calculation.

### How reduce() works?

Sometimes, reduce is very confusing for beginners.

| value | accumulator | calculation | initialValue |
| --- | --- | --- | --- |
| 5 | 0 | 0 + 5 = 5 | 5 |
| 10 | 5 | 5 + 10 = 15 | 15 |
| 20 | 15 | 15 + 20 = 35 | 35 |

Visual Idea for reduce()  
\[5, 10, 15\]

Step 1 → 0 + 5 = 5  
Step 2 → 5 + 10 = 15  
Step 3 → 15 + 15 = 30

Final Result = 30

## Assignment for Practice

Try this in your browser console.

*   Try map()
    
    1.  Create an array
        
    2.  Double each number using map()
        
    3.  Console the output and observe by updating the array.
        
*   Try filter()
    
    1.  Apply filter() method on map() output
        
    2.  Filter numbers greater than 10
        
*   Try reduce()
    
    1.  Create an array
        
    2.  Add those numbers using reduce() method.
        
    3.  Check the output and retry after updating the values and number of values in array.
        

## Final Thoughts

Array methods make JavaScript more powerful and readable.

Instead of writing long loops, you can use:

*   map() to change data
    
*   filter() to select data
    
*   reduce() to combine data
    
*   forEach() to loop through items
    

These methods are commonly used in modern JavaScript, React, and backend development.

The best way to learn them is simple: open your console and experiment with them.

Follow Javascript Series to learn more!
---
title: "Spread vs Rest Operators in JavaScript"
seoTitle: "Spread vs Rest Operator in JavaScript Explained Simply"
seoDescription: "Learn the difference between spread and rest operators in JavaScript with examples, use cases, and simple explanations."
datePublished: 2026-05-03T15:03:06.129Z
cuid: cmopwh3m600p51qgwfclk59de
slug: spread-vs-rest-operators-in-javascript
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/8e8197d5-2095-49c0-959f-0aabec24ef91.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/f57b27a3-7afc-43b9-ba0a-e6d5b62f54dd.png
tags: javascript, javascript-spread-vs-rest-operator, spread-in-js, rest-in-js

---

In ES6 (ECMAScript 2015), Javascript has introduced spread (`...`) and rest (`...`) operators. You might be wondering both looks same but the working and behaviour are completely different.

After this blog, you will get a crystal clear idea about expanding vs combining values using these operators.

## What is spread operator?

The spread operator (`...`) is used to expand the values from the array, objects, or iterables into individual values.

*   **Expanding objects:**
    
    ```javascript
    const user = {id: 101, name: 'John', age: 22};
    
    const updatedUser = {...user, city: 'Delhi'};
    
    console.log(user);
    // {id: 101, name: 'John', age: 22}
    
    console.log(updatedUser);
    // {id: 101, name: 'John', age: 22, city: 'Delhi'}
    ```
    
    Here, we have expanded user details into another object using the spread operator.
    
    So, a `updatedUser` will have user + city values.
    
    But, if the user already contains the city value, then updatedUser will have the override value.
    
    ```javascript
    const user = {id: 101, name: 'John', age: 22, city: 'Delhi'};
    
    const updatedUser = {...user, city: 'Jaipur'};
    
    console.log(user);
    // {id: 101, name: 'John', age: 22, city: 'Delhi'}
    
    console.log(updatedUser);
    // {id: 101, name: 'John', age: 22, city: 'Jaipur'}
    ```
    
*   **Expanding arrays:**
    
    ```javascript
    const nums = [1, 2, 3];
    
    const newNums = [...nums, 4, 5];
    
    console.log(newNums); // [1, 2, 3, 4, 5]
    ```
    
    Here, `...nums` expands into `1, 2, 3`. So, `newNums` will contain both `nums` values and new values (4, 5).
    

## What is the Rest Operator?

The rest operator (`...`) is used to collect multiple values into a single array or object.

Example with Function Parameters

```javascript
function sum(...numbers) {
  return numbers.reduce((acc, curr) => acc + curr, 0);
}

console.log(sum(1, 2, 3, 4)); // 10
```

Here, `...numbers` collects all arguments into the array

Example with Destructuring

```javascript
const [first, ...restValues] = [10, 20, 30, 40];

console.log(first); // 10
console.log(rest);  // [20, 30, 40]
```

The remaining elements are collected into restValues.

## Differences between Spread vs Rest

| Feature | Spread Operator | Rest Operator |
| --- | --- | --- |
| Purpose | Expands values | Collects values |
| Usage | Arrays, objects | Function params, destructuring |
| Direction | Inside → Outside | Outside → Inside |
| Output | Individual elements | Individual elements |

## Practical Use Cases

1.  Copying the Arrays (Immutable Updates)
    
    ```javascript
    const original = [1, 2, 3];
    const copy = [...original];
    ```
    
2.  Merging the Arrays
    
    ```javascript
    const numbers1 = [1, 2];
    const numbers2 = [3, 4];
    
    const merged = [...numbers1, ...numbers2]; // [1,2,3,4]
    ```
    
3.  Cloning and Updating the objects
    
    ```javascript
    const user = {name: 'John', age: 21};
    
    const updatedUser = {...user, age: 22};
    ```
    
4.  Flexible Functions Arguments
    
    ```javascript
    function print(...args){
        console.log(args); // print all the values -> 1, 2, 4
    }
    
    print(1, 2, 4);
    ```
    
5.  Extract/Remove any properties using rest
    
    ```javascript
    const user = {name: 'John', age: 21, email: 'abc@email.com'};
    
    const {email, ...remainingProperties} = user;
    
    console.log(remainingProperties); 
    // {name: 'John', age: 21};
    ```
    

## Visual Understanding

```plaintext
Spread Operator
[1, 2, 3] -> ...nums -> 1, 2, 3

Rest Operator
1, 2, 3 -> ...nums -> [1, 2, 3]
```

## When to Use What?

Use the spread operator when you want to

*   Copy or merge arrays/objects
    
*   Pass multiple values
    

Use the rest operator when you want to:

*   Handle an unknown number of arguments
    
*   Extract remaining values
    

## Final Thoughts

Even though spread and rest share the same syntax (`...`).

Their purpose is opposite:

*   Spread → breaks things apart
    
*   Rest → groups things together
    

Mastering this distinction will make your JavaScript code cleaner, more flexible, and easier to maintain.

  
Follow series to learn more about Javascript.
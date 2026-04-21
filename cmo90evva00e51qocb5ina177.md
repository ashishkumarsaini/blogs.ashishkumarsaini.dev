---
title: "Map and Set in JavaScript"
seoTitle: "Map and Set "
seoDescription: "A comparison of a map and a set with an array and objects in Javascript. Explaination with simple examples and necessary functions for beginners"
datePublished: 2026-04-21T19:21:16.249Z
cuid: cmo90evva00e51qocb5ina177
slug: map-and-set-in-javascript
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/32af7866-67cb-4028-936b-d40e94dd3d44.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/658a33ca-0137-4fa0-993a-d506ed12eb64.png
tags: javascript, map-in-js, map-and-set-in-javascript, set-in-js

---

While working in Javascript, you have mostly worked with objects and arrays. But there are some limitations when used for large data or applying complex operations.

## Problems in Objects

*   Object must have a key as a string. If you use a number, it will automatically be used as a string.
    
*   Objects inherit properties from their prototypes. For example: Object.*keys* is a predefined property that should not be used as a key. This may lead to unexpected bugs.
    
*   You cannot directly iterate over the object's values/keys. You have to use object.keys() or object.entries() to do iteration.
    
*   Order of insertion is not maintained.
    

## Problems with Arrays

*   Removing a specific value from an array requires another iteration to find the position of the value in the array.
    
*   The array might have duplicate values. In some cases the developer doesn't want to insert duplicate values into the array. To achieve the same, they need to iterate over the whole array to check if the value already exists.
    

## Understanding Map and Set

### What is Map?

Map is a built-in datatype in Javascript. It is used to store key-value pairs. It is like an object with some extra powers.

1.  Key can be of any type (string, number, array...)
    
2.  Key should be unique
    
3.  Maintain insertion order. This means if you iterate over a map, it will be the same order in which they are inserted.
    

**Map Methods:**

1.  Insert value,  
    To insert a value in map, use `map.set(key, value)`.  
    Examples:
    
    ```javascript
    const employee = new Map();
    
    employee.set("id", 101);
    employee.set("name", "Rahul");
    ```
    
2.  Get a value  
    To get a value, use `map.get(key)`
    
    ```javascript
    const employee = new Map();
    
    employee.set("id", 101);
    employee.set("name", "Rahul");
    
    const employeeName = employee('name');
    
    console.log(employeeName); // Rahul
    ```
    
3.  Check if value exisits, use `map.has(key)`, return boolean state.
    
    ```javascript
    const employee = new Map();
    
    employee.set("id", 101);
    employee.set("name", "Rahul");
    
    console.log(employee.has('name'));   // true
    console.log(employee.has('salary')); // false
    ```
    
4.  Delete a value, use `map.delete(key)`
    
    ```javascript
    const employee = new Map();
    
    employee.set("id", 101);
    employee.set("name", "Rahul");
    
    employee.delete("id");
    
    console.log(employee.has("id")); // false
    ```
    

## What is Set?

A set is also a built-in datatype in Javascript used to store unique values. It is more like an array but with the power of uniqueness.

*   Store unique values
    
*   Store only values, not keys
    
*   Maintain insertion order
    

**Set methods:**

1.  Insert a value, use `set.add(value)`.
    
    ```javascript
    const set = new Set();
    
    set.add(42);
    set.add(42);
    set.add(13);
    
    for (const item of set) {
      console.log(item);
      // Expected output: 42
      // Expected output: 13
    }
    ```
    

1.  Check if the value exists, use `set.has(key)`, return a boolean state.
    
    ```javascript
    const set = new Set();
    
    set.add(42);
    set.add(13);
    
    console.log(set.has(42));   // true
    console.log(set.has(40)); // false
    ```
    
2.  Delete a value, use `set.delete(value)`, returns a boolean value indication if value is deleted successfully.
    
    ```javascript
    const set = new Set();
    
    set.add(42);
    set.add(13);
    
    console.log(set.delete(42)); // true
    console.log(set.delete(40)); // false
    
    console.log(set) // Set(1) {13}
    ```
    

Both Map and Set have other methods like `values`, `entries`, `size` and `forEach` for iteration. Here I have explained you the necessory methods for insertion and deletion of values.

### Comparison between Map vs Object

Object vs Map:

|  |  |  |
| --- | --- | --- |
|  |  |  |
|  |  |  |

Array vs Set
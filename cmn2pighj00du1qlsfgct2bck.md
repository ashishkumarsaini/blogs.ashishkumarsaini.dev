---
title: "Understanding Object in JS"
seoTitle: "JavaScript Objects Explained for Beginners"
seoDescription: "Learn JavaScript objects from scratch with simple examples. Understand key-value pairs, property access, updates, loops, and real-world use cases."
datePublished: 2026-03-23T04:49:47.769Z
cuid: cmn2pighj00du1qlsfgct2bck
slug: understanding-object-in-js
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/4eed3e81-4cd9-4e0e-971b-6db3668b0272.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/ab0924bc-1f90-4ddd-8e6b-52f3ab783f5a.png
tags: javascript, objects, js-objects

---

When you start learning Javascript, array helps you to store the list of data. But is there a possibility of storing structured information like details of an employee?

1.  name
    
2.  age
    
3.  salary
    

That’s where objects come in.

## What Are Objects?

An object is a collection of data stored in key-value pairs.

Think of it like a real-world entity.

Example: A person has:

*   name
    
*   age
    
*   city
    

In JavaScript, we represent this using an object:

```javascript
const person = {
  name: "Ashish",
  age: 25,
  city: "Delhi"
};
```

Here:

*   `name`, `age`, `city` are keys
    
*   `"Ashish"`, `25`, `"Delhi"` are their values
    

## Why Do We Need Objects?

Arrays store data using indexes:

```javascript
const user = ["Ashish", 25, "Delhi"];
```

But this is confusing. What if I don't know on which index the value actually exists?

Objects solve this by using keys:

```javascript
person.name
```

You can directly access the value by using its key name.

## Creating Objects

You can create an object using curly braces `{}`:

```javascript
const student = {
  name: "John",
  age: 20,
  course: "BCA"
};
```

## Accessing Properties

### 1\. Dot Notation

The object values can be accessed using . (`dot`) notation:

```javascript
console.log(student.name); // John
```

### 2\. Bracket Notation

The object values can also be accessed using \[\] (bracket) notation. Inside the bracket, the key name will be specified as a string.

```javascript
console.log(student["age"]); // 20
```

## Dot notation vs Bracket notation

*   Dot notation → simple and common
    
*   Bracket notation → useful when the key is dynamic
    

```javascript
const key = "course";
console.log(student.course) // BCA
console.log(student[key]);  // BCA
```

## Updating Object Properties

Updating object value is simple and uses only dots. Just specify the . and keyname with the assignment operator and value

```javascript
student.age = 21;
console.log(student.age); // 21
```

Breakdown:

*   `age` -> key
    
*   `=` -> assignment operator
    
*   `21` -> value
    

## Adding New Properties

New properties can also be added using the same approach for updating the object.

```javascript
student.city = "Mumbai";

console.log(student);
```

If the city doesn't exisits in object, it will add new property. Otherwise update exisiting.

## Deleting Properties

Object properties can be deleted using delete keyword following with object property name.

```javascript
delete student.course;

console.log(student);
```

## Looping Through Object Keys

To loop through an object, we use `for...in`:

```javascript
for (let key in student) {
  console.log(key, student[key]);
}

// Output:
// name Rahul
// age 21
// city Mumbai
```

## Array vs Object (Simple Comparison)

| Feature | Array | Object |
| --- | --- | --- |
| Structure | Ordered list | Key-value pairs |
| Access | Index (0, 1, 2) | Key (name, age) |
| Use Case | List of items | Structured data |
| Example | `["a", "b"]` | `{ name: "Ashish" }` |

## Visual Representation (Mental Model)

Think of an object like a labeled box:

```plaintext
person = {
  name → "Ashish"
  age  → 25
  city → "Delhi"
}
```

Each value is stored with a label (key).

## Assignment (Practice)

Create a student object and perform the following:

1.  Create an object named "employee"
    
2.  Add name, id, and salary fields
    
3.  Update the salary of the employee object.
    
4.  Loop through the employee object to print all properties.
    

> Practice by converting real-life things (car, phone, user profile) into objects.

## Conclusion

Objects are one of the most important concepts in JavaScript.

They help you:

*   Organize data in key-value format
    
*   Make code more readable
    
*   Represent real-world entities
    

Once you’re comfortable with objects, you’ll find it much easier to work with APIs, JSON data, and real applications.  
  
  
Follow and learn more about Javascript!
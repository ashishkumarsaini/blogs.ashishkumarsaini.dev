---
title: "Template Literals in JavaScript"

---

Before ES6, JavaScript developers used string concatenation with the + operator

```javascript
const name = "Vishal";

const age = 30;

const message = "My name is " + name + " and I am " + age + " years old.";

console.log(message); // My name is Vishal and I am 30 years old.
```

But there are various difficulties or problems developers face while performing string concatenations:

*   Hard to read strings
    
*   String gets too long
    
*   Cluttered code
    
*   Difficulty in managing dynamic values
    

As the application grows, it becomes messier and increases the risk of errors.

After ES6, this has been resolved using Template Literals.

## What Are Template Literals?

Template literals are the modern way to work with string concatenations in JavaScript. They use backticks (` `` ` ) instead of quotes (`''`/`""`).

Example:

```javascript
const name = "Vishal";

const age = 30;

const message = `My name is ${name} and I am ${age} years old.`;

console.log(message); // My name is Vishal and I am 30 years old.
```

Use of template literals instead of quotes allows:

*   multi-line strings  
    Example:
    
    ```javascript
    const message = `This is a 
                     string to show template literals
                     multiline.`;
    
    console.log(message);
    // This is a string to show template literals multiline.
    ```
    
*   Embedding variables or operations. Instead of using + operator you can inject variable using ${}.  
    Example:
    
    ```javascript
    const number = 3;
    const message = `Square of ${number} is ${ number ** 2 }.`;
    
    console.log(message); // Square of 3 is 9.
    ```
    

## Benefits of using Template Literals

✅ Benefits: Cleaner and more readable No need for + Easier to maintain 📊 Before vs After (Comparison) ❌ Old Way (Concatenation) const product = "Laptop"; const price = 50000;

const text = "The price of " + product + " is Rs. " + price + "."; ✅ New Way (Template Literals) const text = `The price of ${product} is Rs. ${price}.`;

👉 Clearly more readable and modern!

📄 Multi-line Strings Made Easy

Before template literals, multi-line strings were awkward:

❌ Old Way const text = "This is line one.\\n" + "This is line two."; ✅ Template Literals const text = `This is line one. This is line two.`;

🎯 No special characters, no concatenation—just write naturally.

🧠 Real-World Use Cases

1.  Dynamic Messages const user = "Ashish"; console.log(`Welcome back, ${user}!`);
    
2.  HTML Templates (Very Common) const title = "JavaScript Basics";
    

const html = \`

# ${title}

\`; 3. Logging and Debugging const count = 5; console.log(\`Total items: ${count}\`); 4. Expressions Inside Strings

You can even run JavaScript inside ${}:

const a = 5; const b = 10;

console.log(`Sum is ${a + b}`); 🎯 Why Template Literals Matter Improves code readability Reduces syntax noise Makes dynamic strings easy to write Widely used in modern frameworks (React, Node.js) 🧩 Visual Idea (Conceptual)

String Interpolation Flow:

Variables → ${variable} → Template Literal → Final String

Before vs After:

Old: "Hello " + name + "!" New: `Hello ${name}!` 🏁 Final Thoughts

Template literals are one of the simplest yet most powerful features in modern JavaScript.

Once you start using them: 👉 You’ll rarely go back to + concatenation.
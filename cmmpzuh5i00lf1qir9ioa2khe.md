---
title: "Control Flow in JavaScript: If, Else, and Switch Explained"
seoTitle: "JavaScript if else and switch Statement – Complete Beginner'"
seoDescription: "Confused about if, else, and switch in JavaScript? This beginner-friendly guide breaks down every control flow statement with simple examples."
datePublished: 2026-03-14T07:18:04.377Z
cuid: cmmpzuh5i00lf1qir9ioa2khe
slug: control-flow-in-javascript
cover: https://cdn.hashnode.com/uploads/covers/696877fccb285855f0758646/f1ce6a35-269f-4cc3-8b36-3f5ce318dd59.png
ogImage: https://cdn.hashnode.com/uploads/og-images/696877fccb285855f0758646/5fafd5e2-7aaf-4a38-9d64-34790e0702d0.png
tags: javascript-control-flow, js-if-else, js-switch

---

Everyday you made so many decisions without thinking of them. You going to office, if it is raining, you think of carrying an umbrella, other you leave it at home. When you check your exam results, you think: *"*If I scored above 90, I passed with distinction. If I scored between 70 and 90, I just passed. Otherwise, I need to study harder.*"*

These are called conditional decisions.

Programming works the same way.

In programming, control flow refers to the order in which your program executes instructions. By default, code runs line by line, top to bottom. But real programs need to make decisions, repeat actions, and skip steps based on conditions. That's where control flow structures come in.

In this blog, we will cover the most fundamental of condition programming using:

*   if
    
*   else if
    
*   else
    
*   switch
    

## What is control flow?

Control flow is a mechanism to handle the execution of code lines. It determines which lines of code, in what order and under which conditions.

Without control flow, programming is just a code flow in a single direction. Using control flow gives a different path to the code flow. Usually, all programs/software need control flow as each program has different flows to handle.

```markdown
Line 1 -> Line 2 -> Line 3 -> Line 4 -> Line 5 -> Line 6
```

With control flow:

```markdown
Line 1 -> Line 2 -> Line 3 -> if   -> Line 4
                              else -> Line 5 -> Line 6
```

## Understanding control flow statements

### If statement

Imagine you are at a ticket counter. The rule is, "if a person is less than 18, you are not allowed to buy a ticket." You are only allowed if you are 18 or older.

There is no other action, it's either you can buy or not allowed to buy.

Code version:

The `if` statement works exactly like that. It checks a condition, and **only if the condition is true**, it executes the block of code inside the curly braces.

```javascript
const age = 15;

if(age >= 18){
    console.log("You are allowed to buy the ticket");
}

console.log("Program ends!")
```

When `age` is 15, the condition `age >= 18` is **false**, so the `console` inside the `if` block is skipped entirely. The program jumps straight to the next line after the closing brace.

How It Runs Step by Step

1.  The program reaches the `if` statement.
    
2.  It evaluates the condition inside the parentheses.
    
3.  If the condition is true, it enters the block `{ ... }` and runs the code inside.
    
4.  If the condition is false, it skips the block entirely.
    
5.  Execution continues with whatever comes after the closing `}`. (`Program ends!` )
    

### If-else

### The Real-Life Version

Now imagine there is an election going on in your city. So, if you age is 18 or above, you can vote. Otherwise, you cannot. Here we can see there are two flows. Either you vote in the election or not.

Code Version

```javascript
const age = 20;

if(age >= 20) {
    console.log("You are eligible for voting");
}
else {
    console.log("You are not eligible for voting");
}

console.log("Program ends!")
```

Try to run the above code snippet in your browser console or in any online Javascript compiler.

In the previous example, we have seen the condition inside `if (condition)` does not fulfill. `(false)` , "Program ends!" prints out. But here, it will go into the else block.

### Else-if

In real life or in programming, there might be more than two outcomes. Consider a grading system:

*   90 and above → Grade A
    
*   75 to 89 → Grade B
    
*   60 to 74 → Grade C
    
*   35 to 59 → Grade D
    
*   Below 35 → Fail
    

That's five possible outcomes. You need to check multiple conditions in sequence, and execute the block that matches the first true condition. This is called an `else if` **ladder**.

```javascript
const marks = 82;

if (marks >= 90) {
    console.log("A");
} else if (marks >= 75) {
    console.log("B");
} else if (marks >= 60) {
    console.log("C");
} else if (marks >= 35) {
    console.log("D");
} else {
    console.log("Fail");
}
```

### Else

Else is used for the last case, if all the `if` or `else if` conditions will not be fulfilled. In the above code example, you can see we are printing "Fail" as it is the last option in the programming flow.

### Switch

Imagine you're writing a program: "Enter 1 for Monday, 2 for Tuesday, 3 for Wednesday..." You have one variable (the user's choice), and many exact values to compare it against. Using a long `else if` ladder for this works, but it's repetitive and harder to read.

The `switch` statement was used exactly for this scenario. It takes a single expression, compares it against multiple fixed values, and jumps directly to the matching one.

Example:

```javascript
const day = 3;

switch (day) {
    case 1:
        console.log("Monday");
    case 2:
        console.log("Tuesday");
    case 3:
        console.log("Wednesday");
    case 4:
        console.log("Thursday");
    case 5:
        console.log("Friday");
    case 6:
        console.log("Saturday");
    case 7:
        console.log("Sunday");
    default:
        console.log("Invalid day number.");
}
```

Try to run this program in the browser console or Javascript compiler.

Have you noticed the problem? What is the output of the above program?  
  
Monday  
Tuesday  
Wednesday  
Thursday  
Friday  
Saturday  
Sunday  
Invalid day number.  
  
Have you wondered why all the days get printed? Here, what helps is the `break` keyword.

### Break

The `break` statement tells the program: *"*You're done with this case, exit the switch now." If you forgot to use break, just like the above example, the program will continuously execute all the cases until it gets the break.

Let's see the same example with `break` statment:

```javascript
const day = 6;

switch (day) {
    case 1:
        console.log("Monday");
        break;
    case 2:
        console.log("Tuesday");
        break;
    case 3:
        console.log("Wednesday");
        break;
    case 4:
        console.log("Thursday");
        break;
    case 5:
        console.log("Friday");
        break;
    case 6:
        console.log("Saturday");
        break;
    case 7:
        console.log("Sunday");
        break;
    default:
        console.log("Invalid day number.");
}
```

Now, try to run the program with multiple values of days. You will find that it was printing only the valid day. In this case, value of day is 6, so it will print "Saturday".

Change the value of day to 10 or "10", and observe the change in the result.

## Assignment: Practice These Yourself

The best way to understand control flow is to write code. Here are two exercises:

### Assignment 1 — Positive, Negative, or Zero

Write a program that checks an integer and prints whether it is positive, negative, or zero.

> Hint: Use an `if-else` ladder

Example output:

```plaintext
const intNum = 10;
Result: The number is positive.

const intNum = -3;
Result: The number is negative.

const intNum = 0;
Result: The number is zero.
```

* * *

### Assignment 2 — Day of the Week

Write a program for a vending machine using `switch`. Create a variable item\_name and check the cases for the item\_name.

Cases:

*   When `item_name` is "coffee", print "Dispensing Coffee"
    
*   When `item_name` is "tea", print "Dispensing Tea"
    
*   When `item_name` is "cookie", print "Dispensing Cookie"
    
*   Invalid case, print "Invalid Item Name"
    

> Use switch with break statement

## Conclusion

Programming is just teaching computers to make decisions like humans. Control flow is a necessary part of programming, as a program will have different flows that need to be controlled using these statements.

Follow this series to learn more about Javascript!
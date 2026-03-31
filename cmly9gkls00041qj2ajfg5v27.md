---
title: "Javascript Operators"
seoTitle: "JavaScript Operators Explained for Beginners"
seoDescription: "Understand JavaScript operators step by step. Includes arithmetic, comparison, logical, and assignment operators with console examples."
datePublished: 2026-02-22T21:29:38.899Z
cuid: cmly9gkls00041qj2ajfg5v27
slug: javascript-operators
cover: https://cloudmate-test.s3.us-east-1.amazonaws.com/uploads/covers/696877fccb285855f0758646/10f09c86-f4eb-4161-b306-8af41a3b77ef.png
tags: js-operators, beginner-js

---

When we start learning JS, after variables, we first encounter the operators. When some variables are declared, you need to perform some operations on those variables. Operators help to do some calculations, comparisons, or make decisions on variables.

In this blog, we will understand operators with simple examples.

## What are Operators?

Operators are nothing but the symbols that perform operations. Let's take an example:

```javascript
const a = 10;
const b = 20;

const c = a + b;

console.log(c); // 30
```

Here, `+` is the operator.

## What are Operands?

Variables on which operation is done, are called operands.

```javascript
const a = 10;
const b = 20;

const c = a + b;
```

Here:

*   `a` is left operand
    
*   `b` is right operand
    

### Types of Operators

In JS, there are multiple types of operators, but we will cover the basic, mandatory operators in this blog.

1.  Arithmetic operators (`+`, `-`, `*`, `/`, `%`)
    
2.  Comparison operators (`==`, `===`, `!=`, `>`, `<` , `>=`, `<=` )
    
3.  Logical operators (`&&`, `||`, `!`)
    
4.  Assignment operators (`=`, `+=`, `-=`)
    

Let's understand them one by one:

## Arithmetic Operators

These are used for basic mathematical operations.

<table style="min-width: 248px;"><colgroup><col style="min-width: 25px;"><col style="min-width: 25px;"><col style="min-width: 25px;"><col style="width: 173px;"></colgroup><tbody><tr><th colspan="1" rowspan="1"><p>Operator</p></th><th colspan="1" rowspan="1"><p>Meaning</p></th><th colspan="1" rowspan="1"><p>Expression</p></th><th colspan="1" rowspan="1" colwidth="173"><p>Result</p></th></tr><tr><td colspan="1" rowspan="1"><p>+</p></td><td colspan="1" rowspan="1"><p>Addition</p></td><td colspan="1" rowspan="1"><p>9 + 3</p></td><td colspan="1" rowspan="1" colwidth="173"><p>12</p></td></tr><tr><td colspan="1" rowspan="1"><p>-</p></td><td colspan="1" rowspan="1"><p>Substraction</p></td><td colspan="1" rowspan="1"><p>9 - 3</p></td><td colspan="1" rowspan="1" colwidth="173"><p>6</p></td></tr><tr><td colspan="1" rowspan="1"><p>*</p></td><td colspan="1" rowspan="1"><p>Multiplication</p></td><td colspan="1" rowspan="1"><p>9 * 3</p></td><td colspan="1" rowspan="1" colwidth="173"><p>27</p></td></tr><tr><td colspan="1" rowspan="1"><p>/</p></td><td colspan="1" rowspan="1"><p>Division</p></td><td colspan="1" rowspan="1"><p>9 / 3</p></td><td colspan="1" rowspan="1" colwidth="173"><p>3</p></td></tr><tr><td colspan="1" rowspan="1"><p>%</p></td><td colspan="1" rowspan="1"><p>Remainder</p></td><td colspan="1" rowspan="1"><p>10 % 3</p></td><td colspan="1" rowspan="1" colwidth="173"><p>1</p></td></tr></tbody></table>

## Comparison operators

These operators are used for comparison between two values and return a Boolean (true/false) value.

<table style="min-width: 100px;"><colgroup><col style="min-width: 25px;"><col style="min-width: 25px;"><col style="min-width: 25px;"><col style="min-width: 25px;"></colgroup><tbody><tr><th colspan="1" rowspan="1"><p>Operator</p></th><th colspan="1" rowspan="1"><p>Meaning</p></th><th colspan="1" rowspan="1"><p>Expression</p></th><th colspan="1" rowspan="1"><p>Example</p></th></tr><tr><td colspan="1" rowspan="1"><p>==</p></td><td colspan="1" rowspan="1"><p>Equals (loose comparison)</p></td><td colspan="1" rowspan="1"><p>"5" == 5</p></td><td colspan="1" rowspan="1"><p>true</p></td></tr><tr><td colspan="1" rowspan="1"><p>===</p></td><td colspan="1" rowspan="1"><p>Equals (strict comparison)</p></td><td colspan="1" rowspan="1"><p>"5" === 5</p></td><td colspan="1" rowspan="1"><p>false</p></td></tr><tr><td colspan="1" rowspan="1"><p>!=</p></td><td colspan="1" rowspan="1"><p>Not equal (loose comparison)</p></td><td colspan="1" rowspan="1"><p>"5" != 5</p></td><td colspan="1" rowspan="1"><p>false</p></td></tr><tr><td colspan="1" rowspan="1"><p>!==</p></td><td colspan="1" rowspan="1"><p>Not equal (strict comparison)</p></td><td colspan="1" rowspan="1"><p>"5" !== 5</p></td><td colspan="1" rowspan="1"><p>true</p></td></tr><tr><td colspan="1" rowspan="1"><p>&lt;</p></td><td colspan="1" rowspan="1"><p>Less than</p></td><td colspan="1" rowspan="1"><p>5 &lt; 10<br>5 &lt; 5</p></td><td colspan="1" rowspan="1"><p>true<br>false</p></td></tr><tr><td colspan="1" rowspan="1"><p>&lt;=</p></td><td colspan="1" rowspan="1"><p>Less than or equal to</p></td><td colspan="1" rowspan="1"><p>5 &lt;= 10<br>5 &lt;= 5</p></td><td colspan="1" rowspan="1"><p>true<br>true</p></td></tr><tr><td colspan="1" rowspan="1"><p>&gt;</p></td><td colspan="1" rowspan="1"><p>Greater than</p></td><td colspan="1" rowspan="1"><p>5 &gt; 2<br>5 &gt; 5</p></td><td colspan="1" rowspan="1"><p>true<br>false</p></td></tr><tr><td colspan="1" rowspan="1"><p>&gt;=</p></td><td colspan="1" rowspan="1"><p>Greater than or equal to</p></td><td colspan="1" rowspan="1"><p>5 &gt;= 2<br>5 &gt;= 5</p></td><td colspan="1" rowspan="1"><p>true<br>true</p></td></tr></tbody></table>

Understanding loose and strict comparison is very important.

Why `"5" == 5` gives a result of `true`?

When there is `==` operator, JS first converts the value to the same type before comparison.

Which means "5" (string) is first converted to 5 (number) and then `5 == 5` comparison gives `true` result.

Whereas in `===` strict comparison, JS does not change the type of both left and right operands and compares both the type and value.

On the left side, there is a string operand and on the right side, there is a number operand. That's why in a strict case it will give a `false` result.

## Logical operators

These operators help in combining the conditions.

*   **&&**  
    This is also known as AND operator.  
      
    **Truthy Table**
    
    <table style="min-width: 100px;"><colgroup><col style="min-width: 25px;"><col style="min-width: 25px;"><col style="min-width: 25px;"><col style="min-width: 25px;"></colgroup><tbody><tr><th colspan="1" rowspan="1"><p>A</p></th><th colspan="1" rowspan="1"><p>B</p></th><th colspan="1" rowspan="1"><p>Expression</p></th><th colspan="1" rowspan="1"><p>Result</p></th></tr><tr><td colspan="1" rowspan="1"><p>true</p></td><td colspan="1" rowspan="1"><p>true</p></td><td colspan="1" rowspan="1"><p>true &amp;&amp; true</p></td><td colspan="1" rowspan="1"><p>true</p></td></tr><tr><td colspan="1" rowspan="1"><p>false</p></td><td colspan="1" rowspan="1"><p>true</p></td><td colspan="1" rowspan="1"><p>false &amp;&amp; true</p></td><td colspan="1" rowspan="1"><p>false</p></td></tr><tr><td colspan="1" rowspan="1"><p>true</p></td><td colspan="1" rowspan="1"><p>false</p></td><td colspan="1" rowspan="1"><p>true &amp;&amp; false</p></td><td colspan="1" rowspan="1"><p>false</p></td></tr><tr><td colspan="1" rowspan="1"><p>false</p></td><td colspan="1" rowspan="1"><p>false</p></td><td colspan="1" rowspan="1"><p>false &amp;&amp; false</p></td><td colspan="1" rowspan="1"><p>false</p></td></tr></tbody></table>
    
    By analysing the truthy table, we can see that even if one side of expression is false, the final result is false. In order to get true, both side values should be true.
    
*   `||`  
    This is also known as OR operator  
      
    **Truthy Table**
    
    <table style="min-width: 100px;"><colgroup><col style="min-width: 25px;"><col style="min-width: 25px;"><col style="min-width: 25px;"><col style="min-width: 25px;"></colgroup><tbody><tr><th colspan="1" rowspan="1"><p>A</p></th><th colspan="1" rowspan="1"><p>B</p></th><th colspan="1" rowspan="1"><p>Expression</p></th><th colspan="1" rowspan="1"><p>Result</p></th></tr><tr><td colspan="1" rowspan="1"><p>true</p></td><td colspan="1" rowspan="1"><p>true</p></td><td colspan="1" rowspan="1"><p>true || true</p></td><td colspan="1" rowspan="1"><p>true</p></td></tr><tr><td colspan="1" rowspan="1"><p>false</p></td><td colspan="1" rowspan="1"><p>true</p></td><td colspan="1" rowspan="1"><p>false || true</p></td><td colspan="1" rowspan="1"><p>true</p></td></tr><tr><td colspan="1" rowspan="1"><p>true</p></td><td colspan="1" rowspan="1"><p>false</p></td><td colspan="1" rowspan="1"><p>true || false</p></td><td colspan="1" rowspan="1"><p>true</p></td></tr><tr><td colspan="1" rowspan="1"><p>false</p></td><td colspan="1" rowspan="1"><p>false</p></td><td colspan="1" rowspan="1"><p>false || false</p></td><td colspan="1" rowspan="1"><p>false</p></td></tr></tbody></table>
    
    Here we can see that if either side of the operator is true, the final result will be true. Only in the case of both sides of values to being false gives the false result.
    
*   **!**  
    This is known as the NOT operator. As the name suggests, it reverses the given value.  
      
    **Truthy Table**
    
    <table style="min-width: 75px;"><colgroup><col style="min-width: 25px;"><col style="min-width: 25px;"><col style="min-width: 25px;"></colgroup><tbody><tr><th colspan="1" rowspan="1"><p>A</p></th><th colspan="1" rowspan="1"><p>Expression</p></th><th colspan="1" rowspan="1"><p>Result</p></th></tr><tr><td colspan="1" rowspan="1"><p>true</p></td><td colspan="1" rowspan="1"><p>!true</p></td><td colspan="1" rowspan="1"><p>false</p></td></tr><tr><td colspan="1" rowspan="1"><p>false</p></td><td colspan="1" rowspan="1"><p>!false</p></td><td colspan="1" rowspan="1"><p>true</p></td></tr></tbody></table>
    

## Assignment Operators

These operators are used to assign values to variables.

*   **\=**  
    This is known as assign operator. It is used to assign a value to a variable.
    

```javascript
let a;

a = 10;

console.log(a); // prints 10
```

*   **+=**  
    This is known as Add and assign operator
    

```javascript
let a;

a = 10;

console.log(a); // prints 10

a += 5; // Adding 5 to a variable value and assing back

console.log(a) // prints 15
```

*   **\-=**  
    This is known as the Subtract and assign operator
    

```javascript
let a;

a = 10;

console.log(a); // prints 10

a -= 5; // Subtracy 5 from the variable value and assing back

console.log(a) // prints 5
```

###   
Final thoughts

JavaScript operators are the building blocks of logic and calculations in your code. Mastering these will make your JavaScript journey much easier.  
  
To learn JS from fundamentals to advanced, follow this series [https://blog.ashishkumarsaini.dev/series/javascript-for-beginners](https://blog.ashishkumarsaini.dev/series/javascript-for-beginners)
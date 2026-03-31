---
title: "HTML Basics – Understanding the Structure of a Webpage"
seoTitle: "HTML Basics for Beginners – Tags, Elements, and Page Structure Explain"
seoDescription: "This beginner-friendly HTML guide explains tags, elements, block vs inline differences, and commonly used HTML tags in a clear and practical way."
datePublished: 2026-01-31T20:27:18.392Z
cuid: cml2rjnqw000102lb0i29fjms
slug: html-basics
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1769883230362/d7a7866b-fcc2-4a26-bbb7-f857768256f5.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1769891153107/90f5d2ce-a837-4dc9-a308-f731d62d99df.jpeg
tags: html, html5, basic-html, html-for-beginners

---

## What is HTML and Why Do We Use It?

HTML (HyperText Markup Language) is the standard language used to create web pages.

When you open any website, the basic structure of that page is written in HTML. It is also known as the skeleton of any webpage.

### Simple Analogy

Think of building a house:

* HTML → Structure of the house (walls, doors, rooms)
    
* CSS → Paint & decoration (colors, design)
    
* JavaScript → Electricity & automation (interaction, behavior)
    

Without HTML, a browser would not be able to know:

* Which is heading
    
* From where the paragraph starts
    
* Where an image should appear
    
* Cannot differentiate between a link and plain text
    

HTML gives meaning and structure to content so browsers can display it properly.

## What is an HTML Tag?

An HTML tag is a special keyword written inside angle brackets `< >`.

Example:

```xml
<div>
```

A tag acts like a label or instruction to the browser.

It tells the browser:

* From where the element starts
    
* Where it ends
    
* What type of element is it
    

Tags themselves are not displayed on the webpage. They only guide the browser on which element and how the element should be displayed.

## Opening Tag, Closing Tag, and Content

Most HTML tags come in pairs:

```xml
<p>Hello World</p>
```

Let’s break it down:

**Opening Tag:** This is defined as a tag that tells the browser where an element starts.

```css
<p>
```

**Content:** It is actually the content which comes in between the tags. It is actually displayed on the web page in the browser.

```css
Hello World
```

**Closing Tag:** This tells the browser that this is the end of the element. The **forward slash** `/` is what makes it a closing tag.

```css
</p>
```

Closing tag is very important as the browser might get confused that till where the content is and mix other tags, which leads to incorrect and mixed layout issues.

## What is an HTML Element?

This is where beginners often get confused.

### Tag vs Element

**Tag** → Only the keyword inside brackets  
**Element** → The **entire structure,** including opening tag, content, and closing tag.

Example:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769889485624/6e270b84-be90-4d18-a271-7519177222ff.png align="center")

* `<p>` = Opening Tag
    
* `</p>` = Closing Tag
    
* `<p>Hello world</p>` = **Element**
    

So an element is a complete unit, while a tag is just a part of it.

In the real world analogy, imagine a box:

* Opening tag → opening the box
    
* Content → items inside the box
    
* Closing tag → closing the box
    
* Entire box → element
    

## Self-Closing (Void) Elements

Some HTML elements do not wrap any content, so they do not need closing tags.

Examples:

```css
<img src="photo.jpg">
<br>
<hr>
<input type="text">
```

These are called Void Elements.

### Why They Exist

They perform single actions, such as:

* Displaying an image
    
* Creating a line break
    
* Drawing a horizontal line
    
* Creating an input field
    

These tags do not have content to wrap, that’s why there is no requirement of closing tag.

## Block-Level vs Inline Elements

HTML elements are mainly divided into two layout categories.

### Block-Level Elements

Characteristics of block-level elements:

* Take the full width of the screen
    
* Always start on a new line
    
* Used to build a structure
    

Examples:

```xml
<div></div>
<p></p>
<h1></h1>
<section></section>
```

Visually, it will look like this:

```css
[Heading          ]
[Paragraph        ]
[Another Paragraph]
```

Even if the content is small, block elements occupy the entire row.

### Inline Elements

Characteristics:

* Take only the required width
    
* Do not start on a new line
    
* Used inside text
    

Examples:

```xml
<span></span>
<a></a>
<strong></strong>
<em></em>
```

Visually, it will look like this:

```css
This is a [link] inside a sentence.
```

Inline elements flow within text, like words in a paragraph.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769891087968/e26eb2e8-36aa-4d52-8cb3-9cc4aa6f1142.png align="center")

## Commonly Used HTML Tags

Here are the tags beginners should learn first:

### Headings

Used for titles and structure.  
`h1` is the largest, `h6` is the smallest.

```xml
<h1>Main Title</h1>
<h2>Sub Title</h2>
```

### Paragraph

Used for writing a paragraph. Denoted by `p`

```xml
<p>This is a paragraph.</p>
```

### Link

Also known as an anchor tag.  
It has href attribute that specifies the URL to navigate when clicked.  
It also has a target attribute used for opening the page in the same browser tab or another tab. It accepts:

* `_blank` → for a new tab
    
* `_self` → for the same tab
    

```xml
<a href="https://example.com" target="_blank">Visit Site</a>
```

Creates clickable links.

### Image

Use to display images. It has attributes:

* src → source path of the image
    
* alt → until the image gets loaded, it will show the alt text. Useful for accessibility readers
    
* width → for providing a fixed width to the image
    
* height → for providing a fixed height of the image
    

```xml
<img src="photo.jpg" alt="A photo">
```

### Div (Container)

It is used to wrap any content/tag inside it. It is also known as a wrapper. It is also used to group sections.

```xml
<div>Content</div>
```

### Span (Inline Container)

It is used to render the text, but not like `p` tag. It doesn’t take full space and also not create a new link for the elements.

```xml
<span>Highlighted text</span>
```

### Lists

As the name suggests, it is used to display the lists.

1. **Ordered lists:** This is used when the order of the items should be displayed. It is done for the semantic purpose. `ol` tag is used to display an ordered list.
    
    `li` means list item.
    

```xml
<ol>
  <li>Item 1</li>
  <li>Item 2</li>
</ol>

Output:

1. Item 1
2. Item 2
```

2. Unordered list: This is used when the order of the items doesn’t matter. `ul` tag is used to display an ordered list.
    

```xml
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>

Output:

* Item 1
* Item 2
```

### Line Break

This is a self-closing tag used to create a new line. Syntax define as `<br>`

```xml
<span>Text 1</span>
<br>
<span>Text 1</span>

Output:

Text 1

Text 2
```

### Horizontal Rule

This is a self-closing tag used to separate the two contents by displaying a horizontal line. Syntax define as `<hr>`

```xml
<p>Text 1</p>
<hr>
<p>Text 1</p>

Output:

Text 1
-----------------------------------------------------------------
Text 2
```

## Inspect HTML

One of the best ways to learn HTML is to see it in real websites.

### How to Inspect

1. Open any webpage
    
2. Right-click → Inspect
    
3. Go to the Elements tab
    
4. You’ll see live HTML
    

You can even:

* Edit text
    
* Change colors
    
* Delete elements temporarily
    

This helps you to understand structure visually.

##   
Final Thoughts

HTML is not programming, it is markup.  
You are not telling the computer how to think, you are telling the browser how to structure content.

Once HTML is clear, learning CSS and JavaScript becomes much easier because you already understand the foundation of the webpage.
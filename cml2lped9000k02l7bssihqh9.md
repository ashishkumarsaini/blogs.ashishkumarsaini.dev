---
title: "How a Browser Works: A Beginner-Friendly Guide"
seoTitle: "How a Browser Works: A Beginner-Friendly Guide"
seoDescription: "A beginner-friendly guide that explains how browsers turn HTML and CSS into pixels. Learn about DOM, CSSOM, layout, painting, and rendering in simple way."
datePublished: 2026-01-31T17:43:48.477Z
cuid: cml2lped9000k02l7bssihqh9
slug: beginners-guide-to-browser
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1769881413519/b8cdb85f-981b-4586-bc5b-70206cd9e6a0.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1769881420057/d8e0bfed-9469-4c4e-a3d0-d0668d20404e.jpeg
tags: browser, css, html, html-parsing, cssom-tree, browser-rendering

---

You have surely worked with the browser every day to access web content but have you ever wonder how the browser works internally?

* You type website domain/url in the address bar
    
* You hit enter
    
* and boom, a webpage is displayed
    

In less than a second, a browser has perform a dozens of tasks to display a single webpage.

Assume browser like a factory, when you just told what I need and there are multiple factory workers/machine working together and create a product for you.  
Browser works the same.

### What happen you type a URL and press Enter?

When Enter is pressed:

1. Checks in cache:
    
    Browser checks if it already access this site earlier. This check is just to get the IP address of the hosted server
    
2. DNS lookup:
    
    If the IP is not available in cache, it request to DNS to get the IP.
    
3. TCP connection:
    
    Once the DNS provide the IP, browser start establishing a connection with the server.
    
4. Server responds with files.
    
5. Browser does its calculations and display the webpage content which comes from the server.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769854280019/c14efe1e-6b24-4417-8562-f8257ca90839.png align="center")

In this blog, we mainly focus on the calculations done by the browser from getting data from the server to display page to the viewer.

## Main parts of a browser (high-level overview)

Browser is not a single program but a team of mini programs working together. Let’s first understand the overview of browser components.

* **User Interface:**
    
    It belongs to the component of browser which is visible directly for the interaction with the browser. It include everything expect where the website is displayed. Examples:
    
    * Address bar
        
    * Back/forward buttons
        
    * Bookmark menu
        
    * Settings
        
    * Tabs
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769853123219/2aab32fe-c904-489b-9e1f-6ed81b192725.png align="center")
        
* **Browser Engine**
    
    The browser engine is also called the brain/core of the browser. It act as a middleman between the User Interface and the Rendering Engine.
    
    It receives commands from the browser User Interface and give instructions to the Rendering Engine to do some operations.
    
* **Rendering Engine**
    
    It is responsible for displaying the requested content on the screen. It parses the HTML (Hypertext Markup Language) and CSS (Cascading Style Sheet), and combine them to build. We will discuss more about this in details in further sections
    
* **Networking Layer**
    
    This component handles all network communications and HTTP requests. It manages DNS lookups (translating URL to IP addresses), handles TCP/IP connections, and fetches resources (HTML, images, CSS) from servers
    
* **JavaScript Interpreter**
    
    It is a engine that parses and executes JavaScript code. It interprets, compiles, and runs JavaScript to add interactivity to web pages
    
* **Disk API**
    
    As name suggests, it is used to store data in storage which a browser/web page needed. There are multiple components in browser data storage such as Cookies, LocalStorage, SessionStorage, IndexDB, and file system access.
    

### Browser Engine vs Rendering Engine

| **Browser Engine** | **Rendering Engine** |
| --- | --- |
| Handlers actions between the UI and the rendering engine. | Parse the request HTML and CSS content and display on the screen |
| Manage task like networking, security and overall rendering process | Manage creating DOM, CSSOM, frame tree, repaints and painting process |
| Examples: Chromium, Servo | Example: Blink (Chrome), Webkit (Safari) |

## How browser download HTML, CSS and JS files?

1. The process begins with when a user enters the URL in address bar and press Enter.
    
2. Browser perform a DNS look to find the servers IP’s address.
    
3. Once browser get the IP, it sends a HTTP GET request to the server.
    
4. Browser Networking Layer create a connection for the data transfer.
    
5. Now, the browser start receiving the HTML data, the browser engine instructs rendering engine to start parsing the HTML data and build the DOM (Document Object Model)
    
6. As it parses the HTML, it founds the tag referencing to the external JS/CSS file links such as `<link>` or `<script>`
    
7. Browser again sends the HTTP request to the corresponding servers of the link for the CSS and JS.
    
    * Once the CSS file is downloaded, the rendering engine starts parsing the CSS and generate a CSSOM (CSS Object Model). Until the CSSOM is created, browser stops rendering the HTML, to avoid rendering the page incorrectly and repaint.
        
    * Once JS file is downloaded, the JS Interpreter start compiling the JS downloaded and execute it. By default, the browser stops the parsing of HTML and CSS, but you can change the behaviour by using `async/defer` attribute in the `script` tag.
        
        If you want not to block the CSS and HTML parsing until the JS file get download, use `defer` otherwise use `async`
        
8. Now when all the necessary files has been downloaded, the rendering engine combines the DOM and CSSOM and with all other processing like frame constructor and reflow, it paints and display the web content on the browser.
    

### Structural flow of Rendering Engine

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769858244412/b579f579-9802-4d41-9367-9ccefe6125a0.png align="center")

## Parsing

### HTML parsing (HTML → DOM creation)

When the browser receives an HTML file, it first understand the structure instead of directly jump into displaying the content on screen.

Let’s first understand what parsing is?

**Parsing** is a way of reading the code, understanding the structure and breaking it into pieces.

In real world analogy, it is same like reading an english sentence from a book, understanding and separating the noun, pronoun, verb and adjectives. A HTML is look like this:

```xml
<body>
    <div>
        <h1>This is a heading</h1>
        <p>This is a text</p>
    </div>
    <strong>Hey, It's me</strong>
</body>
```

Here, `body` and `div` is a container for `h1` and `p` tag.

After parsing, the browser creates a tree like structure called Document Object Model (DOM).

```plaintext
      body
      / \
 strong  div
          / \
         h1  p
```

It cannot be visualise but in the browser backend, the structure is almost like the above.

### CSS Parsing (CSSOM creating)

While the HTML builds structure, CSS builds the rules for styling.

Example CSS:

```css
h1 { color: blue; }
p { font-size: 16px; }
```

The browser parse CSS by breaking it into the selectors and properties.

This become another tree like structure which called as CSSOM, but instead of elements it stores styling instructions.

### DOM + CSSOM → Render Tree

Now the browser rendering engine has

* Structure (DOM)
    
* Style rules (CSSOM)
    

It combines them into a render tree. Render tree is something which contains only visible elements and their final styles.

So, in case if the element has `display: none`, it will not appear in the render tree.

## Frame Tree / Reflow

Now the browser figures out where everything goes.

It calculates:

* Width
    
* Height
    
* Position
    
* Margins
    
* Padding
    
* Screen size responsiveness
    

This step is called Layout or Reflow.

Layout changes when window resizes, font load, DOM changes

## Painting

After layout, the browser starts adding visuals:

* Colors
    
* Fonts
    
* Borders
    
* Shadows
    
* Images
    

At this stage, elements become visually rich but still exist in layers.

## Display

At this step the user actually sees the content on the page.

* Layers are merged
    
* Pixels are sent to the screen
    

## Conslusion

* HTML → DOM (Structure)
    
* CSS → CSSOM (Style Rules)
    
* DOM + CSSOM → Render Tree (Visible Elements)
    
* Render Tree → Layout (Measure & Position)
    
* Layout → Paint (Add Colors & Fonts)
    
* Paint → Display (Pixels on Screen)
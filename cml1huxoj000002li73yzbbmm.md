---
title: "Getting Started with cURL"
seoTitle: "What Is cURL? A Beginner’s Guide to HTTP Requests, APIs, and Servers"
seoDescription: "Learn what cURL is, why developers use it, and how it talks to servers using HTTP. A beginner-friendly guide with simple examples and diagrams."
datePublished: 2026-01-30T23:08:22.147Z
cuid: cml1huxoj000002li73yzbbmm
slug: getting-started-with-curl
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1769814405138/d8f3013c-08e8-4806-bdfb-3a649b818f0b.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1769814472643/ee1a31da-a1a4-4ecf-a8e6-5baf580d2577.png
tags: curl, networking, curl-command, curl-for-beginner

---

To understand cURL, we should first take a look at what a server is. A server is a powerful computer, software, or virtual machine designed to store, manage, and deliver data, services, or resources to other computers—known as clients—over a network. A server will

* stays online 24/7
    
* listens on a port
    
* waits for requests
    
* sends back responses
    

In a real-world analogy, a server is like a shop counter:

* You (client) ask something from the shopkeeper
    
* The shopkeeper checks
    
* The shopkeeper gives you the thing that you have requested
    

The internet is just millions of such conversations happening per second.

## Problems before cURL existed

To connect to the server, you really need some heavy software like Postman, browsers or you have to write a program.

But what if you just want to:

* Check if a server is alive
    
* see raw response
    
* debug quickly
    

Then cURL came into the picture to solve the problem of displaying raw data on terminals.

## What is cURL?

cURL is a tool that allows you to talk to the servers directly from the terminal.

It sends a request to the server same like a browser. The only difference is it doesn’t have any formatting, no UI and no hiddings.

* Browser → need buttons/ui to connect to servers
    
* cURL → uses terminal commands to connect to the servers
    

It shows raw responses from the servers.

### Why programmers need cURL

Both frontend and backend developers need cURL for various purposes:

Backend developers use cURL to:

* Test endpoints before the frontend exists
    
* Debug production APIs
    
* Validate request/response format
    
* Reproduce bugs
    
* Check authentication
    

cURL sits **between you and the server**:

* Frontend devs use it to test APIs
    
* Backend devs use it to debug endpoints
    
* DevOps uses it to check server health
    

## Your first request — what actually happens

Let’s understand what happens when someone sends a request to a server using cURL:

This **looks simple**, but a LOT happens behind the scenes.

### Step-by-step breakdown

1. DNS lookup
    
    * abc.com → IP address
        
2. Connection
    
    * TCP connection to the server
        
3. TLS handshake (for HTTPS)
    
    * secure channel established
        
4. HTTP request sent to the server.
    
5. Server responds
    
6. cURL prints the response from the server
    

Same happen for the Browser in the backend.

## Understanding request and response (core idea)

Whenever cURL talks to a server, two things happen:

### Request (You → Server)

* What do you want?
    
* Where do you want it from?
    
* How do you want it?
    

### Response (Server → You)

* Status (success or error)
    
* Data (HTML, JSON, text, etc.)
    

## Understanding HTTP Request and Response

An HTTP request is a text-based message sent by a client to a server, such as loading a webpage (GET) or submitting a form (POST).

### Key Components of an HTTP Request

* **Request Method**: Defines the action type
    
    1. GET to retrieve
        
    2. POST to send
        
    3. PUT to update
        
    4. DELETE to remove.
        
* **Uniform Resource Identifier (URI)**: The path or address of the resource on the server.
    
* **HTTP Version**: (e.g., HTTP/1.1 or HTTP/2).
    
* **Headers**: Key-value pairs providing information about the client, content type, or cookies.
    
* **Body**: Optional content sent with the request (e.g., form data).
    

An HTTP response is the data a server sends back to a client after receiving a request containing content like HTML, JS, CSS, images, etc.

### Key Components of an HTTP Response

* **Status Code**: A 3-digit code indicating the success/failures.
    
* **Response Headers**: Metadata providing details about the content, content type (e.g., `Content-Type: text/html`).
    
* **Message Body**: The actual content requested by the client, such as HTML code, an image file, or JSON data.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769813929762/c2131acb-ee2b-4b62-8506-942f4fa0e6db.png align="center")

### HTTP response status codes:

| **Status codes** | **What it means** | Example |
| --- | --- | --- |
| **1xx** | Informational, Request received | 101: used in switching protocols |
| **2xx** | Success, Action received and accepted | 201: user created successfully |
| **3xx** | Redirection, Further action is needed to complete the request | 307: temporary redirects |
| **4xx** | Client Error: Request contains bad syntax or cannot be fulfilled | 401: Unauthorized request from client |
| **5xx** | Server Error, Server failed to fulfill a valid request | 503: Service unavailable |

## GET vs POST requests

* **Use GET for:**
    
    * Fetching information, such as viewing a webpage, product data, or search data, etc.
        
    * Operations that are "safe" and do not alter the server's state.
        
    * Scenarios where users might want to bookmark or share the URL.
        
* **Use POST for:**
    
    * Submitting sensitive data like passwords, login credentials, or personal information.
        
    * Creating or modifying data on the server, such as posting a comment, registering a new user, or adding an item to a shopping cart.
        
    * Uploading files.
        
    * Sending a large amount of data.
        

## Using cURL with APIs (what APIs really are)

An API **is just a server** that:

* doesn’t return UI
    
* returns structured data (usually JSON)
    

So when you do:

```powershell
curl --request GET \
  --url 'https://api.freeapi.app/api/v1/public/randomjokes?limit=1&query=sciencepage=1' \
  --header 'accept: application/json'
```

You are:

* calling a server endpoint
    
* using HTTP GET request
    
* getting raw data
    

```powershell
{"statusCode":200,"data":{"page":1,"limit":1,"totalPages":0,"previousPage":false,
"nextPage":false,"totalItems":0,"currentPageItems":0,"data":[]},
"message":"Random jokes fetched successfully","success":true}
```

No frontend involved.
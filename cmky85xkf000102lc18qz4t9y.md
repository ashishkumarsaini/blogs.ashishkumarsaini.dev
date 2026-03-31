---
title: "TCP vs UDP: When to Use What, and How TCP Relates to HTTP"
seoTitle: "TCP vs UDP Explained Simply (With Real Examples)"
seoDescription: "Learn the difference between TCP and UDP with simple explanations, diagrams, and real-world examples."
datePublished: 2026-01-28T16:13:40.527Z
cuid: cmky85xkf000102lc18qz4t9y
slug: tcp-vs-udp
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1769616778028/abf02f07-7898-4230-b4a4-e9250fd1fca3.png
tags: https, tcp, udp, tcp-vs-udp, tcp-with-https

---

Lets first understand why internet need the rules to transport data from one computer to another.

When you open a website an watch some live video or sending a text message to another computer (or we can say client). But the internet have so many problems exists:

* Unreliable (cannot be trustable)
    
* Distributed
    
* Congested (full of traffic)
    
* So many devices connected
    

To solve this problems, we need some rules which can solve “how to send the data”, “how to receive the data”, “how to know if the data is lost” and “how to identify and recover the lost data”. Those rules are called protocols.

There are two protocols in networking transport:

* TCP - Transmission Control Protocol
    
* UDP - User Datagram Protocol
    

Both have some advantage and disadvantage. Let’s deep dive into these protocols.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769610405103/802e5985-6f4e-49c6-8eec-3a9de4ded130.png align="center")

## TCP (Transmission Control Protocol)

TCP is reliable, ordered and works on three way handshake process which is the guaranteed way to send data.

It have following characteristics:

* Trustable
    
* Less data loss
    
* Fast data transfer
    
* Congestion control
    
* Slightly slower
    

TCP ensure that:

* Data Arrives
    
* Data Arrives in correct order
    
* Lost data can be recovered
    
* Sender and Receiver should be connected.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769613202648/e9ce564c-a3ce-479f-8029-dd04e8cec27c.png align="center")

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">Sending a registered courier which requires the signature of the receiver and it has been sent back to the the sender of the courier is a real world example of TCP. It ensure and guarantees that the receiver has received the courier.</div>
</div>

## UDP (User Datagram Protocol)

UDP is a protocol which is used to send data fast and works based on send and forgot process without an acknowledgement.

It has following characteristics:

* Connectionless
    
* Unreliable
    
* Fast
    
* No delivery or order guarantee
    

UDP cannot ensures:

* Does the data arrives
    
* Does the order of data in correct order
    
* Does not maintain data
    
* Does not maintain the connection between the sender and receiver
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769613634656/26ca0507-33cd-4f69-ac56-e0b80cbd6773.png align="center")

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">UDP is like shouting the announcement on the loudspeaker. Some might receive, some will miss.</div>
</div>

## When to use which protocol?

Use TCP, when there is a need of

* no data loss
    
* order must be preserved
    
* Accuracy is more important than the speed.
    

Examples: Email, Website content (HTTP/HTTPS), File downloads, Payments related, Authentications. Messaging.

Use UDP, when there is a need of

* Speed is important more than the accuracy
    
* Minor data loss can be acceptable
    

Examples: Online games, Video streaming, Voice calls, Broadcasts.

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">If you really miss the live score of the world cup (UDP), it might not be frustrating instead if someone transfers you some amount to you bank account and you receives less amount (TCP).</div>
</div>

## What is HTTP?

HTTP stands for Hypertext Transfer Protocol. It is an application level protocol. It defines the request and response format, request headers, and methods for the request (GET, PUT, POST, etc.).

It decides what to send (Application Layer) instead of how to send (Transport Layer).

```plaintext
Application Layer:   HTTP
Transport Layer:     TCP / UDP
Network Layer:       IP
```

### Relation between HTTP and TCP?

HTTP uses the TCP to actually transfers the data. Flow when you open a website:

1. When a website is requested, browser create an HTTP request.
    
2. HTTP gives it to the TCP
    
3. TCP break it into packets and send them safely
    
4. Server receives and respond back via TCP
    
5. Browser receives and rebuilds HTTP response
    

## Conclusion

Mental Model:

* TCP → Safe and efficiently data transfer system
    
* UDP → Fast data transfer system
    
* HTTP → Data with some set of rules
    

The internet does not just send the data, it actually gives a choice to use different type of rules to transfer the data based on the system requirements.
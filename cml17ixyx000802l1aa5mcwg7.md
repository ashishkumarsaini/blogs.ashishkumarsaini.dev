---
title: "TCP Working: 3-Way Handshake & Reliable Communication"
seoTitle: "TCP Explained Simply: Handshake, Data Transfer, and Connection Closing"
seoDescription: "Learn how TCP works step by step, including the 3-way handshake, sequence numbers, acknowledgements, reliable data transfer, and connection closing."
datePublished: 2026-01-30T18:19:06.489Z
cuid: cml17ixyx000802l1aa5mcwg7
slug: tcp-working
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1769797007391/336bd330-db20-4acc-bf9c-0c43d39d24e5.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1769797053751/8a2a4190-5878-4ecf-a8c9-14454a5b30c0.png
tags: networking, tcp, tcp-handshake

---

When you send some data to another person using the internet, the data won’t be transmitted at once. It transfers in chunks called packets, not the whole data at once.

Now, without the specific rules anyone can send data through any methods or we can say rules.

* Data can get lost
    
* Data can arrive out of order
    
* Data can be duplicated
    
* Data can get damaged
    
* Your friend won’t know when the complete data is received
    

Now, TCP came in picture.

## What is TCP and why is it needed?

TCP stands for Transmission Control Protocol. It is a data transmission protocol in the Transport Layer of the OSI Model.

TCP makes sure that the data is

* Delivered
    
* Delivered in the correct order
    
* Delivered without any duplicates
    
* Delivered without any corruption
    

That’s why TCP is known for reliable data transfer protocol. Before establishing a connection and sending the data, it builds the connection.

TCP is connection-oriented. The connection orientation approach means that the connection establishment is required to be set up before starting to transfer the data. This protocol uses three way handshaking approach and ensures that the other party is ready to accept and receive the data.

Let’s take an example of a client and a server.

* The Client should first send a message to the server asking, “Are you ready?”
    
* Server responds “Yes, I’m ready“ and sends it back to the client.
    
* Client responds, “Let’s start”.
    

This process is known as 3-way handshaking.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769639326800/2d45fe84-ab43-49ea-a61d-2bfba20985e6.png align="center")

## Problems TCP can solve

| **Problem** | **What TCP Does** |
| --- | --- |
| Packet loss | Retransmits missing data |
| Out-of-order packets | Reorders them |
| Duplicates | Removes duplicates |
| Network speed mismatch | Uses flow control |
| Network congestion | Slows down sending |
| Data corruption | Detects & resends |

Let’s understand the complete process of connection building, data transferring and then connection closing in detail:

### Establishing connection

Before sending the data, TCP builds the connections first. TCP uses a process called three-way handshaking, which means it asks for the receiver, waits for the acknowledgement and then sends the data.

Imagine a conversation between two people on a mobile phone:

First: hey! Am I audible?  
Second: Yes, you are audible. Am I audible too?  
First: yes, you too. Let’s start.

Only after this, the real conversation will start. So,

Step 1 →

* Sender sends the sequence number as 0 and the ack number as 0.
    
* The Sender says, I want to start a connection.
    

Step 2 → Receiver sends

* Ack number as 1 (*denotes receiver is ready to start the connection*)
    
* Sequence number as 0 (*means send me data from the start*)
    

Now the receiver acknowledges and is ready to start the connection.

Step 3 → Sender sends

* Ack number as 1 (*connection is established*)
    
* Sequence number as 1 (*let’s start from the first order of the data segment*)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769789590752/dde19cc9-18b2-4215-87b0-cf257b2214fc.png align="center")

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">Sequence number → a flag with aunique number that defines the order of the segment of data should be sent by the sender. Ack number → a flag with a unique number that defines the acknowledgement of the data received and the next order of the data segment.</div>
</div>

### Transfering Data

Let’s assume the connection has been established.

1. **Sender → Receiver** (segment 1)
    
    * Sequence Number: 1
        
    * Acknowledge number: 1
        
    * Length: 100 bytes (data bytes from 1 to 100)
        
    
    Sender says, “Here are bytes 1 to 100”.
    
2. **Receiver → Sender**: The receiver accepts the data and returns:
    
    * Sequence Number: 1
        
    * Acknowledge number: 101
        
    
    The receiver says, “I got the data till 101 bytes”.
    
3. **Sender → Reciever** (segment 2)
    
    * Sequence Number: 101
        
    * Acknowledge number: 201
        
    * Length: 100 bytes (data bytes from 101 to 201)
        
    
    Sender says, “Here are bytes 101 to 200”.
    
4. **Receiver → Sender**: The receiver accepts the data and returns:
    
    * Sequence Number: 101
        
    * Acknowledge number: 201
        
    
    The receiver says, “I got the data till 201 bytes”.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769791340900/06b90d4e-ded1-4bd8-96d6-e4678e042f11.png align="center")

And the process goes on…

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">When the receiver sends the acknowledgement, the Ack number will always be the order of the next segment of data (Sequence + Length)</div>
</div>

### Closing Connection

1. **Sender → Receiver**
    
    * Sequence Number: 301
        
    * Acknowledge number: 401 (but not really required)
        
    * FIN: 1
        
    
    Sender says, “Here are bytes 301 to 401. I have sent all my data and this is the last set of bytes”.
    
2. **Receiver → Sender**: The receiver accepts the data and returns:
    
    * Acknowledge number: 401
        
    
    The receiver says, “I got all the data till 401 bytes”.
    
3. **Receiver → Sender**:
    
    * FIN: 1
        
    * Acknowledge number: 0
        
    
    The receiver says, “I’m also closing the connection form my side”.
    
4. **Sender → Receiver**: The receiver accepts the data and returns:
    
    * FIN: 1
        
    * Acknowledge number: 1
        
    
    The receiver says, “Thanks! Acknowledged”.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769796117184/22160c1d-bdda-46b4-a97b-f9eeab6302e6.png align="center")

##   
Packet loss and retransmission flow

Now lets break the packet transferring process.

Sender sends:

* Segment X → Seq: 2000, Length: 500
    
* Segment Y → Seq: 2500, Length: 500
    

But assume that B reaches first, or A has not received, in any case. Receiver checks:

* I have received 2500 - 2999
    
* But 2000 - 2499 is missing
    
* I’m still waiting for byte 2000.
    

The receiver continuously sends ACK = 200 until it receives the data from 2000 - 2499.

## Conclusion

The data transmission in TCP is programmed in such a way that there is very less posibility of data loss. Whether it is on the connection building, data transfer or closing the connection, it asks for the acknowledgment which helps to identify if the data has not been missed by the receiver. This acknowledgement is something that makes it slower than UDP.

That’s why TCP is the protocol that turns an unreliable network into a reliable, ordered, and safe data stream.
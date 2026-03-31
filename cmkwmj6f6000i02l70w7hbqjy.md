---
title: "DNS Record Types Explained"
seoTitle: "DNS Record Types Explained"
seoDescription: "This explains the workaround of how the DNS works and what happen when the browser reaches to the server on which website is hosted."
datePublished: 2026-01-27T13:20:20.802Z
cuid: cmkwmj6f6000i02l70w7hbqjy
slug: dns-record-types-explained
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1769520192577/5cad581f-7eb4-4ebb-bc38-e7605ccd26af.png
tags: dns, browsers, dns-records, dns-resolver

---

When you type google.com in the browser, your computer somehow find the server among the millions of servers and display the right website. But computer doesn’t understand what “`google.com`“ is. Computer only understand the IP addresses `17.122.31.1`.

So how the “`google.com`” changed to the IP address, the answer is DNS.

## DNS

DNS is defined as Domain Name System. DNS is something also known as phone-book / address-book of internet.

Let’s take a example: You have to call your friend. Do you learn the mobile number of each of your friend. No, right? You just save the mobile number once and then when ever you have to call a person, you just search for their name and call them.

Lets take an example: If we talk about someone full address, it will contain the street name, city and country. In order to have addresses of multiple peoples, you need to have an address-book which can contain the address mapped for each person. So that, it will be easy to manage and search for specific person address.

Similarly:

* Computer can understand the IP addresses
    
* Humans understand the domain names (`google.com`)
    
* DNS connects those two
    

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">DNS is the address-book for the internet.</div>
</div>

## Type of DNS Records

* **NS Records**
    
    NS records (Name Server Records) is a type of record which tells which authoritative server will contain the NS record for the actual request domain. NS records decide **where DNS lives for your domain**.
    
    The NS record is default configured by the domain provider, when the domain has been purchased. You can also configure the NS records for other domain providers.
    
* **A Record**
    
    A Record is also known as Address Record. This is the most important NS record for the domain which client has requested from DNS. This is the final record which DNS resolver returns to the client.
    
    ```plaintext
    abc.com -> 192.35.73.10
    ```
    
* **AAAA Record**
    
    This is nothing but the late
    
* **CNAME Record**
    
    It is defined as Canonical Name Record. This is useful to handle the alias of the domain. It is basically pointing one domain to another domain. The authoritative server returns the subdomain NS record confirming that it is the subdomain of the root domain.
    
    In you domain provider panel (hostinger, godaddy, etc.) you have a section to add CNAME with the pointing domain. When you request NS record for [blog.ashishkumarsaini.dev](https://blog.ashishkumarsaini.dev/) with alias having configured CNAME, your won’t get the IP address instead you get the pointing domain.
    
    In real world:
    
    <div data-node-type="callout">
    <div data-node-type="callout-emoji">💡</div>
    <div data-node-type="callout-text">If you changed your old house (<a target="_self" rel="noopener noreferrer nofollow" href="https://blog.ashishkumarsaini.dev/" style="pointer-events: none">https://blog.ashishkumarsaini.dev/</a>) to new house (hashnode.com), you have to register your forwarding address as the new address to the post office. Now, if you have to change your house again to another address (medium.com), You just have to change the forwarding address.</div>
    </div>
    
* **MX Record**
    
    This record is used to configure the email. It stands for Mail Exchange Record. So when someone sends a email, the internet asks for what email server handles this request. The answer comes from the MX record.  
    Without MX record, your domain won’t able to receive emails.
    
    <div data-node-type="callout">
    <div data-node-type="callout-emoji">💡</div>
    <div data-node-type="callout-text">MX record is like your area post office. You only receive the letters because of the post office knows the address of your locality/area.</div>
    </div>
    
* **TXT Record**
    
    It is also known as Text Information Record. These records are often used for domain verification, like confirming you own a domain or for security settings like SPF (Sender Policy Framework) to protect against email spam.
    
    TXT records don’t control traffic. They store proof & instructions.
    

## Why DNS records are needed

DNS records are the individual records present on the Authoritative Servers which will be returned by the DNS resolver to the browser / client. Those are the essential information which helps in mapping the requested domain name with the IP addresses. As we know computer can only understands the number (`IP addresses`), browser won’t able to understand what `google.com` is.

* It is used to make a domain work. We can’t access the website without a domain name system record.
    
* Translating human readable Domain Name to machine readable IP config (A/AAAA records) receive from Authoritative Servers based on older (IPv4) / newer (IPv6) IP addresses.
    
* Ensure the transferring of emails to the right destination by providing the MX records for the email server on which the mail should receive.
    
* Helps in routing the traffic to root domain or sub domain based on the CNAME records.
    
* Useful to prove the domain ownership by using TXT records.
    

So DNS stores **multiple instructions** for a domain. These instructions are called DNS Records.Each record solves **one specific problem**.

In real world analogy:

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">DNS record is a single address in your address-book.</div>
</div>

## How all DNS records work together

Now, you might wonder how all these records help browser to find the actual location of your hosted website. Each time your enter a domain, there is a process how the DNS will return the IP address of the server where the website has been hosted.

Lets assume you want to access a website on domain `abc.dev`.

Whenever a request have been initiated from the browser to DNS resolver, here what happen:

1. DNS Resolver first check the Root Cache, if we already have the DNS record of `abc.dev`.
    
2. If DNS record is not cached, it asks from the root server “Who handles the .dev domains?”  
    Root server replies “I does not know but you can ask the .dev TLD Server” and provide the NS Record (*.dev in this case*).
    
    <div data-node-type="callout">
    <div data-node-type="callout-emoji">💡</div>
    <div data-node-type="callout-text">There are 13 <em>logical</em> root server identities, but thousands of physical servers running them.</div>
    </div>
    
3. The DNS resolver reaches to the TLD Server, and ask for “Where do I find the DNS for `abc.dev`?”. TLD replies “I don’t have the DNS record of `abc.dev` but I can give you NS record of someone who knows (*cloudflare Authoritative Name Server in this case*)”.
    
4. The DNS resolver check the NS record and reaches to the Authoritative Name Server. It provides the actual IP address of the server where the Website has been deployed (*vercel in this case*).
    
5. Once the browser gets the server IP address, it connect to the hosted server for the page content.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769519856515/df1f3237-a04e-4a5f-b057-985714c8177a.png align="center")
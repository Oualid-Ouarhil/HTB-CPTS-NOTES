# 🌐 Domain Name System (DNS) — Simple Explanation

## What is DNS?

**DNS is the internet’s phonebook.**

- Humans use **names** → `www.google.com`
    
- Computers use **numbers** → `142.250.185.46`
    

DNS translates **domain names into IP addresses**, so computers know where to connect.

👉 Without DNS, we would have to remember IP addresses for every website.

---

## Domain Name vs IP Address

|Term|Meaning|
|---|---|
|**Domain Name**|Human-friendly name (e.g. `www.example.com`)|
|**IP Address**|Computer-friendly number (e.g. `93.184.216.34`)|

DNS connects the two.

---

## DNS Structure (Hierarchy)

DNS works like a **tree**, from general → specific.

### Example: `www.example.com`

|Part|What it is|
|---|---|
|`.`|Root (top of DNS)|
|`.com`|Top-Level Domain (TLD)|
|`example`|Second-Level Domain|
|`www`|Subdomain / hostname|

---

### Common TLDs

- `.com`
    
- `.org`
    
- `.net`
    
- `.edu`
    
- Country codes: `.ma`, `.uk`, `.fr`
    

---

## URL Breakdown (Simple)

Example:

`https://www.example.com/page.html`

|Part|Meaning|
|---|---|
|`https`|Protocol (scheme)|
|`www`|Subdomain|
|`example`|Domain name|
|`.com`|TLD|
|`/page.html`|Page/resource|

---

## DNS Resolution (How a Domain Becomes an IP)

This is also called **DNS resolution**.

### What happens when you type a website?

#### Example: `www.example.com`

### Step-by-step (simple):

1️⃣ You type `www.example.com` in your browser  
2️⃣ Your computer checks **local cache** (memory)  
3️⃣ If not found → asks a **Recursive DNS server** (ISP / Google DNS)  
4️⃣ Recursive server asks a **Root server**  
5️⃣ Root server points to the **TLD server** (`.com`)  
6️⃣ TLD server points to the **Authoritative DNS server** for `example.com`  
7️⃣ Authoritative server returns the **IP address**  
8️⃣ Your browser connects to the IP

⏱ All of this happens in **milliseconds**.

---

## DNS Servers (Easy Meaning)

|Server Type|Role|
|---|---|
|**Recursive DNS**|Does the searching for you|
|**Root Server**|Knows where TLDs are|
|**TLD Server**|Knows where domains are|
|**Authoritative Server**|Knows the final IP|

---

## Why DNS Matters in Pentesting / CTFs

🔍 DNS can reveal:

- **Subdomains** (admin, dev, test)
    
- **Internal services**
    
- **Attack surface expansion**
    

Common techniques:

- DNS enumeration
    
- Subdomain brute-forcing
    
- Zone transfers (misconfigurations)
    

---

## One-Line Summary (Exam-Ready)

> **DNS translates domain names into IP addresses by querying multiple DNS servers in a hierarchical order.**
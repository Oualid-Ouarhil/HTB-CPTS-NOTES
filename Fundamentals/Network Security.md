# 🔐 Network Security — Simple Explanation

## What is Network Security?

**Network security** means protecting:

- Data
    
- Devices
    
- Applications
    
- Networks
    

from **unauthorized access**, **damage**, or **attacks**

pasted

The main goal is to protect the **CIA Triad**.

---

## 🧠 CIA Triad (Very Important)

|Principle|Simple Meaning|
|---|---|
|**Confidentiality**|Only allowed people can see the data|
|**Integrity**|Data is not changed or corrupted|
|**Availability**|Systems are accessible when needed|

📌 If one of these fails → security fails.

---

## 🔥 Firewalls

### What is a Firewall?

A **firewall** is like a **security guard** for your network.

It:

- Checks incoming and outgoing traffic
    
- Allows or blocks traffic based on rules
    

If traffic **matches the rules → allowed**  
If not → **blocked**

pasted

---

### 🔎 What Do Firewalls Check?

Firewalls usually look at:

- IP address
    
- Port number
    
- Protocol (TCP, UDP, ICMP)
    

This process is called **traffic filtering**.

---

## 🧱 Types of Firewalls (Simplified)

### 1️⃣ Packet Filtering Firewall

- Checks **IP, port, protocol**
    
- Fast but simple
    
- No understanding of context
    

📌 Example:

> Allow ports 80 & 443, block everything else

---

### 2️⃣ Stateful Firewall

- Tracks **connections**
    
- Smarter than packet filtering
    

📌 Example:

> Only allow incoming traffic if you requested it first

---

### 3️⃣ Application Layer Firewall (Proxy)

- Looks at **actual content**
    
- Works at **application level (HTTP, FTP)**
    

📌 Example:

> Block malicious HTTP requests

---

### 4️⃣ Next-Generation Firewall (NGFW)

- Very advanced
    
- Combines:
    
    - Stateful inspection
        
    - Deep packet inspection
        
    - IDS/IPS
        
    - Application control
        

📌 Used in modern enterprises

---

## 🏠 Where Firewalls Are Placed

- **Home network** → built into router
    
- **Companies** → separate device between internet & internal network
    

All traffic must pass through it

pasted

---

## 🚨 IDS vs IPS

### IDS (Intrusion Detection System)

- **Detects attacks**
    
- Sends alerts
    
- ❌ Does NOT block
    

📌 Think: _Security camera_

---

### IPS (Intrusion Prevention System)

- **Detects + blocks attacks**
    
- Stops malicious traffic in real time
    

📌 Think: _Security guard who intervenes_

---

### 🔍 Detection Methods

|Method|Meaning|
|---|---|
|**Signature-based**|Match known attacks|
|**Anomaly-based**|Detect unusual behavior|

---

## 🧠 IDS / IPS Types

### 1️⃣ Network-Based (NIDS / NIPS)

- Monitors network traffic
    
- Placed at strategic points
    

📌 Example:

> Sensor connected to switch

---

### 2️⃣ Host-Based (HIDS / HIPS)

- Runs on individual machines
    
- Monitors logs & activity
    

📌 Example:

> Antivirus on a server

---

## 📍 Where IDS/IPS Are Placed

Common locations:

- **Behind firewall**
    
- **DMZ** (public servers)
    
- **Directly on hosts**
    

This improves visibility and protection

pasted

---

## ✅ Network Security Best Practices (Easy)

|Practice|Simple Meaning|
|---|---|
|**Least privilege**|Only allow what’s necessary|
|**Regular updates**|Patch systems & signatures|
|**Monitoring**|Review logs and alerts|
|**Defense in depth**|Multiple security layers|
|**Penetration testing**|Test security with real attacks|

---

## 🧠 One-Line Exam Summary

> **Network security protects systems and data using firewalls and IDS/IPS to maintain confidentiality, integrity, and availability.**
# 🌐 Data Flow Example — Super Simple

## Scenario

You open your laptop and type:

`www.example.com`

Let’s see what happens **from your laptop to the website and back**.

---

## 1️⃣ Connecting to Wi-Fi (WLAN)

Before anything else, your laptop must be online.

What happens:

- Laptop finds the **Wi-Fi name (SSID)**
    
- You enter the **Wi-Fi password** (WPA2/WPA3)
    
- Connection is successful
    
- **DHCP starts working**
    

📌 Result: You are connected to your home network.

---

## 2️⃣ Getting an IP Address (DHCP)

Your laptop needs an **IP address** to talk on the network.

Steps:

- Laptop asks the router: _“Can I get an IP?”_
    
- Router replies with:
    
    - Private IP (e.g. `192.168.1.10`)
        
    - Subnet mask
        
    - Default gateway (router)
        
    - DNS server
        

📌 This IP works **only inside your home network**.

---

## 3️⃣ Finding the Website’s IP (DNS)

Computers don’t understand names — only IPs.

Steps:

- Laptop asks DNS:  
    _“What is the IP of www.example.com?”_
    
- DNS replies:
    

`93.184.216.34`

📌 Now your laptop knows **where** the website is.

---

## 4️⃣ Preparing the Data (Encapsulation)

Your request is wrapped step-by-step (like packing a box).

### OSI/TCP-IP Simplified:

1. **Application layer**
    
    - Browser creates HTTP/HTTPS request
        
2. **Transport layer**
    
    - Wrapped in TCP
        
    - Uses:
        
        - Port 80 (HTTP)
            
        - Port 443 (HTTPS)
            
3. **Internet layer**
    
    - Adds IP addresses:
        
        - Source: `192.168.1.10`
            
        - Destination: `93.184.216.34`
            
4. **Link layer**
    
    - Adds MAC addresses
        
    - Uses **ARP** to find router’s MAC
        

📌 Packet is now ready to leave your laptop.

---

## 5️⃣ NAT Happens at the Router

Your router receives the packet.

What NAT does:

- Replaces **private IP** → **public IP**
    

`192.168.1.10  →  203.0.113.45`

Why?

- Private IPs don’t work on the internet.
    

📌 Router sends the packet across the internet.

---

## 6️⃣ Server Receives & Responds

At the website server:

- Firewall checks:
    
    - Is port 80 / 443 allowed?
        
- Web server (Apache/Nginx/IIS):
    
    - Processes request
        
    - Sends back:
        
        - HTML
            
        - CSS
            
        - Images
            
        - JavaScript
            

📌 Response starts traveling **back to you**.

---

## 7️⃣ Return Trip + Decapsulation

- Packet arrives at your router
    
- NAT maps it back to:
    

`203.0.113.45 → 192.168.1.10`

Laptop receives data and:

- Removes Ethernet/Wi-Fi layer
    
- Removes IP header
    
- Removes TCP header
    
- Browser reads the content
    

📌 Website appears on your screen 🎉

---

## 🧠 One-Page Memory Trick

### “Type → Resolve → Send → Translate → Receive → Display”

|Step|Key Concept|
|---|---|
|Connect|Wi-Fi + DHCP|
|Resolve|DNS|
|Send|Encapsulation|
|Translate|NAT|
|Receive|Server response|
|Display|Decapsulation|

---

## 🧠 One-Line Exam Answer

> **When accessing a website, the client connects to the network, resolves the domain via DNS, encapsulates the request, uses NAT to reach the internet, and receives the response which is decapsulated and displayed.**
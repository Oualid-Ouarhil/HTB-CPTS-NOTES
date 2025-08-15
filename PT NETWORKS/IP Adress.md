Tags:[[Networks]][[PRE- SECURITY]]

Devices on a network are very similar to humans in the fact that we have two ways of being identified:

Our Name
Our Fingerprints
Now we can change our name through deed poll, but we can't, however, change our fingerprints. Every human has an individual set of fingerprints which means that even if they change their name, there is still an identity behind it. Devices have the same thing: two means of identification, with one being permeable. These are:

An IP Address
A Media Access Control (MAC) Address -- think of this as being similar to a serial number.

https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/a0de0d68641982ddf1a8c5a9f1984c4c.png

IP Addresses
Briefly, an IP address (or Internet Protocol) address can be used as a way of identifying a host on a network for a period of time, where that IP address can then be associated with another device without the IP address changing. First, let's split up precisely what an IP address is in the diagram below:



Device Name	IP Address	IP Address Type
DESKTOP-KJE57FD	192.168.1.77	Private
DESKTOP-KJE57FD	86.157.52.21	Public
CMNatic-PC	192.168.1.74	Private
CMNatic-PC	86.157.52.21	Public

These two devices will be able to use their private IP addresses to communicate with each other. However, any data sent to the Internet from either of these devices will be identified by the same public IP address. Public IP addresses are given by your Internet Service Provider (or ISP) at a monthly fee (your bill!)

https://assets.tryhackme.com/additional/cmn-aoc2020/day-8/1.png

IPv6 is a new iteration of the Internet Protocol addressing scheme to help tackle this issue. Although it is seemingly more daunting, it boasts a few benefits:

Supports up to 2^128 of IP addresses (340 trillion-plus), resolving the issues faced with IPv4
More efficient due to new methodologies
The screenshot below compares both an IPv6 and IPv4 address.

https://assets.tryhackme.com/additional/networking-fundamentals/intro-to-networking/ipv6.png

MAC Addresses

Devices on a network will all have a physical network interface, which is a microchip board found on the device's motherboard. This network interface is assigned a unique address at the factory it was built at, called a MAC (Media Access Control ) address. The MAC address is a twelve-character hexadecimal number (a base sixteen numbering system used in computing to represent numbers) split into two's and separated by a colon. These colons are considered separators. For example, a4:c3:f0:85:ac:2d. The first six characters represent the company that made the network interface, and the last six is a unique number.

https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/394caee97fb1b9f7b5a5f7a7ea0a9f71.png

### **1. IP Address Basics**

- Each device in a network has a **MAC address** for local identification.
    
- For communication across networks, **IPv4** (32-bit) or **IPv6** (128-bit) addresses are used.
    
- **IPv4** is represented in **dotted-decimal notation** (e.g., `192.168.1.1`).
    
- **MAC** addresses act like apartment numbers, while **IP addresses** act like postal addresses.
    

### **2. IPv4 Structure**

- **Consists of 4 octets** (8-bit groups), each ranging from 0-255.
    
- **Divided into network & host portions**; assigned by **IANA** globally.
    
- Supports **4.29 billion unique addresses**.
    

### **3. IPv4 Address Classes**

| **Class** | **Network Address**             | **Subnet Mask** | **CIDR** | **IPs**     |
| --------- | ------------------------------- | --------------- | -------- | ----------- |
| A         | `1.0.0.0` - `127.255.255.255`   | `255.0.0.0`     | `/8`     | 16 million+ |
| B         | `128.0.0.0` - `191.255.255.255` | `255.255.0.0`   | `/16`    | 65,534      |
| C         | `192.0.0.0` - `223.255.255.255` | `255.255.255.0` | `/24`    | 254         |
| D         | `224.0.0.0` - `239.255.255.255` | **Multicast**   | -        | -           |
| E         | `240.0.0.0` - `255.255.255.255` | **Reserved**    | -        | -           |

### **4. Subnet Mask & CIDR**

- A **Subnet Mask** determines the network/host portions of an IP (e.g., `255.255.255.0`).
    
- **CIDR (Classless Inter-Domain Routing)** notation represents subnets (`/24` means 24 bits for the network).
    
- Example: `192.168.10.39/24` → First **24 bits** belong to the network.
    

### **5. Network & Gateway Addresses**

- **Network Address:** First IP in a subnet (e.g., `192.168.1.0`).
    
- **Broadcast Address:** Last IP used to send messages to all devices (`192.168.1.255`).
    
- **Default Gateway:** Router’s IP, usually first (`192.168.1.1`) or last (`192.168.1.254`).
    

### **6. Binary & Decimal Conversion**

- IPs are **stored in binary** (e.g., `192.168.10.39` → `11000000.10101000.00001010.00100111`).
    
- Subnet mask follows a similar binary structure (e.g., `255.255.255.0` → `11111111.11111111.11111111.00000000`).
    

This summary captures the essentials—let me know if you need any refinements! 🚀
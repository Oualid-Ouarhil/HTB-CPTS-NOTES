
# 🖥️ System Information (Simple & Practical)

When you get access to a Linux machine (via SSH or a shell), your **first job** is to understand:

- **Who you are**
    
- **What system you’re on**
    
- **What access you have**
    
- **What might be exploitable**
    

---

## 🧠 Why This Matters (Pentesting Mindset)

After getting a shell, always ask:

1. **What user am I?**
    
2. **Do I have special privileges?**
    
3. **What OS & kernel is this?**
    
4. **What services & network info exist?**
    

These answers guide **privilege escalation**.

---

## 🔐 Logging in with SSH

SSH lets you remotely control a machine using the terminal.

`ssh username@IP`

- No GUI
    
- Fast
    
- Secure
    
- Standard in Linux servers
    

Used **everywhere** in labs and real environments

pasted

---

## 👤 Who Am I?

### `whoami`

`whoami`

➡️ Shows **current user**

📌 First command after getting a shell.

---

### `id`

`id`

➡️ Shows:

- User ID (uid)
    
- Group ID (gid)
    
- Groups you belong to
    

📌 **Important groups**:

- `sudo` → can run commands as root
    
- `adm` → can read logs
    
- Custom groups → possible misconfigs
    

🔥 Very important for privilege escalation.

---

## 🖥️ System Identity

### `hostname`

`hostname`

➡️ Name of the machine

📌 Useful for:

- Orientation
    
- Pivoting
    
- Multi-host environments
    

---

## 🧬 OS & Kernel Info

### `uname`

`uname -a`

➡️ Shows:

- OS type
    
- Kernel version
    
- Architecture
    

📌 Used to search for **kernel exploits**

---

### Kernel Only (Very Important)

`uname -r`

➡️ Example:

`4.15.0-99-generic`

🔥 You can Google:

`4.15.0-99-generic exploit`

---

## 📁 Where Am I?

### `pwd`

`pwd`

➡️ Shows current directory

---

## 🌐 Network Information

### `ip`

`ip a`

➡️ Network interfaces & IP addresses

📌 Preferred over `ifconfig` (modern).

---

### `netstat` / `ss`

`netstat -tulnp ss -tulnp`

➡️ Shows:

- Listening ports
    
- Services
    
- Internal services (gold for attackers)
    

---

## ⚙️ Processes & Users

### `ps`

`ps aux`

➡️ Running processes

📌 Look for:

- Root processes
    
- Misconfigured services
    

---

### `who`

`who`

➡️ Who is logged in

---

## 🌱 Environment Info

### `env`

`env`

➡️ Environment variables

📌 Sometimes leaks:

- Paths
    
- Tokens
    
- Credentials
    

---

## 🧱 Hardware & Devices (Less Common, Still Useful)

|Command|Purpose|
|---|---|
|`lsblk`|Disks|
|`lsusb`|USB devices|
|`lspci`|PCI devices|
|`lsof`|Open files|

---

## 📘 Help Is Always There

If you forget something:

`command -h command --help man command`

📌 **Man pages = hidden knowledge**

---

## 🧠 Learning Mindset (Important)

Feeling confused = **good sign**.

- Confusion means learning
    
- Exercises are meant to push you
    
- You don’t need to know everything
    
- You need to **keep trying**
    

This is normal in:

- Linux
    
- Cybersecurity
    
- Pentesting
    
    pasted
    

---

## 🧠 OSCP / CPTS First-Minute Checklist

After shell access, run:

`whoami id hostname uname -a uname -r ip a ss -tulnp`

---

## 🧠 One-Line Exam Summary

> **System information commands help identify users, privileges, OS details, and potential attack vectors after gaining shell access.**
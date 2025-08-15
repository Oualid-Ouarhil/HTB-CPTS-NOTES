Tags: [[ENUMERATION]]


---

# 🧰 Web Enumeration Tools for OSCP & CTFs

---

## 🔍 Gobuster

**Gobuster** is a brute-force tool used for enumerating:

- **Directories** and files on web servers (port 80/443)
    
- **DNS subdomains**
    
- **Virtual hosts**
    
- **Open AWS S3 buckets**
    

### 🔧 Alternatives

- [`ffuf`](https://github.com/ffuf/ffuf) – Fast web fuzzer
    
- [`hydra`](https://github.com/vanhauser-thc/thc-hydra) – Brute-force login credentials
    

---

### 📂 Directory Enumeration

```bash
gobuster dir -u http://<IP> -w <wordlist_path>
```

**Flags:**

- `-u` – Target URL
    
- `-w` – Wordlist path
    

**🔎 Example:**

```bash
gobuster dir -u http://10.10.10.121/ -w /usr/share/seclists/Discovery/Web-Content/common.txt
```

**Output Sample:**

```
/.hta (403)
/.htpasswd (403)
/.htaccess (403)
/index.php (200)
/server-status (403)
/wordpress (301)
```

### 📚 HTTP Status Codes Quick Reference

|Code|Meaning|
|---|---|
|200|OK – Found|
|301|Moved Permanently|
|403|Forbidden|
|404|Not Found|

👉 [Learn more](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)

---

### 🌐 DNS Subdomain Enumeration

```bash
gobuster dns -d <domain> -w <wordlist>
```

**Example:**

```bash
gobuster dns -d inlanefreight.com -w /usr/share/seclists/Discovery/DNS/namelist.txt
```

**Sample Output:**

```
Found: blog.inlanefreight.com
Found: customer.inlanefreight.com
Found: my.inlanefreight.com
```

---

## 📦 SecLists

A massive collection of wordlists used for:

- Brute-force
    
- Web fuzzing
    
- Subdomain discovery
    
- Payload injection
    

### 📥 Installation

```bash
sudo apt install seclists -y
# OR
git clone https://github.com/danielmiessler/SecLists
```

---

## 🌐 cURL

**cURL** is a command-line tool to interact with URLs.

### 📥 View Server Headers

```bash
curl -IL https://www.inlanefreight.com
```

**Sample Output:**

```
HTTP/1.1 200 OK
Server: Apache/2.4.29 (Ubuntu)
Content-Type: text/html; charset=UTF-8
```

---

## 🔎 WhatWeb

**WhatWeb** identifies technologies used on websites (web server, frameworks, CMS, etc.).

### 🔍 Scan a single host

```bash
whatweb 10.10.10.121
```

### 🌐 Scan a network range

```bash
whatweb --no-errors 10.10.10.0/24
```

**Sample Output:**

```
http://10.10.10.121 [200 OK] Apache[2.4.41], Ubuntu, Title[PHP 7.4.3 - phpinfo()]
```

---

## 🔐 Web Recon Tips

✅ **Check `robots.txt`** – Hidden paths often disallowed  
✅ **Inspect Page Source (`Ctrl+U`)** – Look for comments or JS variables  
✅ **Try default credentials** – Especially for `/admin`, `/login`  
✅ **Analyze HTTP headers and cookies** – For tokens, versions, etc.

---

Would you like me to help format your notes into a Markdown file or Notion/Obsidian structure for easier studying?
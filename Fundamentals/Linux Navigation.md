# 📂 Linux Navigation — Super Simple

Think of Linux like a **big folder system**.  
Navigation means:

- Knowing **where you are**
    
- Seeing **what’s inside folders**
    
- Moving **between folders easily**
    

Just like using folders in Windows — but with commands.

---

## 📍 Where Am I?

### `pwd`

`pwd`

➡️ Shows your **current directory**

📌 First command to orient yourself.

Example output:

`/home/user`

---

## 📄 What’s Inside This Folder?

### `ls`

`ls`

➡️ Lists files and folders in the current directory.

---

### `ls -l` (Detailed view)

`ls -l`

Shows:

- Permissions
    
- Owner
    
- Group
    
- Size
    
- Date
    
- Name
    

📌 Useful for:

- Permission checks
    
- Privilege escalation clues
    

---

### `ls -la` (Show hidden files)

`ls -la`

➡️ Shows **everything**, including hidden files:

`.bashrc .bash_history`

🔥 Hidden files often contain **credentials or config info**.

---

## 📁 Listing Another Directory (Without Going There)

`ls /var`

➡️ Lists contents of `/var` without changing directories.

📌 Very useful during enumeration.

---

## 🚶 Moving Between Directories

### `cd`

`cd /path/to/folder`

➡️ Moves you to a directory.

Example:

`cd /dev/shm`

---

### Go Back to Previous Directory

`cd -`

➡️ Instantly jumps back.

---

### Go to Parent Directory

`cd ..`

➡️ Moves **one level up**.

📌 `.` = current directory  
📌 `..` = parent directory

---

## ⚡ Auto-Completion (Huge Time Saver)

Press:

`TAB`

Example:

`cd /dev/s[TAB]`

➡️ Shell auto-completes paths.

🔥 Saves time & prevents typos.

---

## 🧹 Clearing the Terminal

### Command way:

`clear`

### Shortcut:

`Ctrl + L`

---

## ⬆️ Command History (Very Important)

- **↑ / ↓** → previous commands
    
- **Ctrl + R** → search command history
    

Example:

`Ctrl + R → type "ssh"`

🔥 Extremely useful during pentests.

---

## 🧠 Quick Mental Map

|Command|What It Does|
|---|---|
|`pwd`|Where am I|
|`ls`|What’s here|
|`ls -la`|Show everything|
|`cd dir`|Move|
|`cd ..`|Go up|
|`cd -`|Go back|
|`TAB`|Auto-complete|
|`Ctrl + R`|Search history|

---

## 🧠 OSCP / CPTS Tip

During enumeration:

- Always check **hidden files**
    
- Always explore directories like:
    
    - `/home`
        
    - `/var`
        
    - `/tmp`
        
    - `/dev/shm`
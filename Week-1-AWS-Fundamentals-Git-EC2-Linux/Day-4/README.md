# Day 04 – Linux Command Practice (Files, Permissions, Processes, Networking) 🐧

## 📌 Objective

Practice essential Linux commands required for server management and DevOps workflows.

This task includes practicing:

* **File and directory operations**
* **File permissions and ownership**
* **Process management**
* **Networking commands**
* **Package management**

All commands were executed on **Amazon Linux EC2 instance**.

---

# Step 1: File and Directory Operations

Check current directory:

```bash
pwd
# prints the current working directory
```

List files and directories:

```bash
ls
# lists files in the current directory
```

Detailed list:

```bash
ls -l
# shows permissions, owner, size, and date
```

Create a directory:

```bash
mkdir devops-practice
# creates a new directory
```

Create a file:

```bash
touch notes.txt
# creates an empty file
```

Copy a file:

```bash
cp notes.txt backup.txt
# copies notes.txt to backup.txt
```

Move or rename file:

```bash
mv notes.txt devops-notes.txt
# renames or moves the file
```

Delete file:

```bash
rm backup.txt
# removes file
```

Delete directory:

```bash
rm -r devops-practice
# removes directory recursively
```

---

# Step 2: File Viewing Commands

View file content:

```bash
cat devops-notes.txt
# prints file content
```

View file page by page:

```bash
less devops-notes.txt
# scrollable file viewer
```

Display first lines:

```bash
head devops-notes.txt
# shows first 10 lines
```

Display last lines:

```bash
tail devops-notes.txt
# shows last 10 lines
```

---

# Step 3: File Permissions

Check permissions:

```bash
ls -l
# displays file permissions
```

Example output:

```bash
-rw-r--r-- 1 ec2-user ec2-user file.txt
```

Permission format:

```text
Owner | Group | Others
```

Change file permission:

```bash
chmod 755 script.sh
# gives execute permission to owner, group, others
```

Make file executable:

```bash
chmod +x script.sh
# adds execute permission
```

Change file owner:

```bash
sudo chown ec2-user file.txt
# changes ownership of the file
```

---

# Step 4: Process Management

View running processes:

```bash
ps
# shows current shell processes
```

Detailed process list:

```bash
ps aux
# shows all running processes
```

Monitor processes live:

```bash
top
# real-time system process monitoring
```

Kill a process:

```bash
kill <PID>
# terminates process using process id
```

Force kill:

```bash
kill -9 <PID>
# forcefully stops the process
```

Find process ID:

```bash
pidof java
# returns process id of running program
```

---

# Step 5: Networking Commands

Check IP address:

```bash
ip a
# shows network interfaces and IP addresses
```

Test internet connectivity:

```bash
ping google.com
# sends packets to check connectivity
```

Check open ports:

```bash
netstat -tulnp
# lists active ports and services
```

Test remote server connectivity:

```bash
curl google.com
# sends request to web server
```

Download file from internet:

```bash
wget https://example.com/file.zip
# downloads file from URL
```

---

# Step 6: Package Management

Amazon Linux uses **yum** package manager.

Update packages:

```bash
sudo yum update -y
# updates installed packages
```

Install a package:

```bash
sudo yum install git -y
# installs git package
```

Search for package:

```bash
yum search docker
# searches package repository
```

Check installed packages:

```bash
yum list installed
# lists installed software packages
```

Remove package:

```bash
sudo yum remove git
# removes installed package
```

---

# Useful Linux Shortcuts

Clear terminal:

```bash
clear
# clears terminal screen
```

Command history:

```bash
history
# shows previously executed commands
```

Find command location:

```bash
which java
# displays path of command
```

---

# Key Learnings

* Linux **file and directory operations**
* Understanding **file permissions**
* Monitoring and managing **system processes**
* Checking **network connectivity**
* Installing and managing **software packages**

These commands are essential for **system administration and DevOps tasks on cloud servers**.

---

# Final Outcome

By completing **Day 04**, I successfully:

* Practiced **Linux file operations**
* Managed **file permissions and ownership**
* Monitored **system processes**
* Tested **network connectivity**
* Installed and managed **Linux packages**

This improves the ability to **manage cloud-based Linux servers efficiently.**

---

# Next Step

**Day 05**
    
✅ Install and configure Nginx on EC2    
✅ Host a basic HTML site

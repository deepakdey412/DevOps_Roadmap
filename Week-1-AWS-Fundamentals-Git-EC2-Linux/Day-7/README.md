# Day 07 – Weekly Review & Hands-on Practice 🔁

## 📌 Objective

Review everything learned during the week and strengthen understanding through **hands-on practice, troubleshooting, and documentation**.

This task includes:

* Reviewing **Linux, EC2, Nginx, and Git concepts**
* Practicing previously used **commands and configurations**
* Troubleshooting common issues
* Refactoring scripts and improving structure
* Updating project **documentation**

---

# Step 1: Review the Week's Learning

Topics covered during this week:

* AWS **EC2 instance setup**
* **SSH connection** to Linux servers
* Linux **file operations and permissions**
* Linux **process and networking commands**
* Installing and configuring **Nginx**
* Hosting a **static HTML website**
* Using **Git and GitHub for version control**

This review helps reinforce the **core DevOps fundamentals**.

---

# Step 2: Hands-on Practice

Re-practice the most important commands.

### File Operations

```bash
pwd
ls
mkdir test-folder
touch sample.txt
cp sample.txt backup.txt
mv sample.txt new-sample.txt
rm backup.txt
```

### Permission Commands

```bash
ls -l
chmod 755 script.sh
chmod +x script.sh
```

### Process Commands

```bash
ps
ps aux
top
pidof nginx
```

### Networking Commands

```bash
ip a
ping google.com
curl google.com
netstat -tulnp
```

Practicing these commands improves **Linux command-line confidence**.

---

# Step 3: Troubleshoot Common Issues

During practice, try to identify and fix common problems.

Examples:

### Nginx Not Running

Check service status:

```bash
sudo systemctl status nginx
```

Start service if stopped:

```bash
sudo systemctl start nginx
```

---

### Website Not Loading

Check:

* Security group **port 80 open**
* Nginx service **running**
* HTML file located in

```
/usr/share/nginx/html
```

---

### Permission Errors

If permission denied occurs:

```bash
sudo chmod -R 755 /usr/share/nginx/html
```

---

# Step 4: Refactor Scripts and Commands

Improve scripts created during the week.

Example: Basic deployment script.

```bash
#!/bin/bash

echo "Updating system..."
sudo yum update -y

echo "Installing Nginx..."
sudo amazon-linux-extras install nginx1 -y

echo "Starting Nginx..."
sudo systemctl start nginx
sudo systemctl enable nginx

echo "Deployment completed!"
```

Make script executable:

```bash
chmod +x deploy.sh
```

Run script:

```bash
./deploy.sh
```

---

# Step 5: Update Documentation

Improve project documentation in **GitHub repository**.

Add:

* Clear **README.md**
* Folder structure explanation
* Commands used in each day
* Screenshots of output

Example repository structure:

```
DevOps-Roadmap
│
├── Week-1-AWS-Fundamentals-Git-EC2-Linux
│
├── Day-1
├── Day-2
├── Day-3
├── Day-4
├── Day-5
├── Day-6
└── Day-7
```

Documentation helps track **learning progress and project history**.

---

# Key Learnings

* Importance of **review and repetition**
* Troubleshooting **real server issues**
* Writing **reusable scripts**
* Maintaining proper **documentation**

These practices are essential for **professional DevOps engineers**.

---

# Final Outcome

By completing **Day 07**, I successfully:

* Reviewed all concepts learned this week
* Practiced essential Linux and AWS commands
* Troubleshot server configuration issues
* Improved scripts and documentation

This strengthens the **foundation for upcoming DevOps tools like Docker and Kubernetes**.

---

# Next Step

**Week 2**

⚙️ Week 2: Infrastructure as Code – Terraform + Ansible
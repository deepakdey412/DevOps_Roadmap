# Day 03 – Launch EC2 Instance & Connect via SSH ☁️

## 📌 Objective

Learn how to launch a cloud server on AWS and connect to it securely.

This task includes:

* Launching an **EC2 Instance (Amazon Linux)**
* Downloading the **PEM key pair**
* Configuring **Security Groups**
* Connecting to the server using **SSH**
* Installing **essential packages (Java, updates, utilities)**

---

# Step 1: Launch EC2 Instance

Navigate to **AWS Console → EC2 → Launch Instance**

Configuration used:

| Setting       | Value                |
| ------------- | -------------------- |
| Instance Name | DevOps-Lab-Server    |
| AMI           | Amazon Linux         |
| Instance Type | t2.micro (Free Tier) |
| Key Pair      | Create new key pair  |
| Network       | Default VPC          |

Create the instance and launch it.

Screenshot Evidence
`EC2_Instance_Create.png`
Tag: **EC2 Server Creation**

---

# Step 2: Download Key Pair (.pem)

While creating the instance, AWS asks to **create or select a key pair**.

Choose:

```
Create new key pair
```

Download the file:

```
devops-key.pem
```

Screenshot Evidence
`EC2_KeyPair_Download.png`
Tag: **PEM File Download**

### Why PEM File is Required

The **.pem key file is used for SSH authentication**.

Instead of passwords, AWS uses **public-key cryptography**:

* AWS stores **public key**
* You receive the **private key (.pem)**

When connecting to EC2:

```
SSH client → sends authentication request
AWS → verifies using the public key
```

Without the `.pem` file **you cannot access the instance**.

---

# Step 3: Configure Security Group

Security Groups act as a **virtual firewall** controlling inbound and outbound traffic.

Configuration used:

| Type | Protocol | Port | Source |
| ---- | -------- | ---- | ------ |
| SSH  | TCP      | 22   | My IP  |

Screenshot Evidence
`EC2_Security_Group.png`
Tag: **Security Group Configuration**

### Why Security Groups Can Be Reused

A single security group can be used across **multiple EC2 instances** because:

* It defines **network access rules**
* It is **independent of the instance**
* Allows **centralized security control**

Example:

```
SecurityGroup-DevOps
   ├── EC2-AppServer
   ├── EC2-TestServer
   └── EC2-Database
```

This makes **security management easier and consistent**.

---

# Step 4: Verify Instance Running

After launching:

Check instance state:

```
Running
```

Copy:

```
Public IPv4 Address
```

Example:

```
3.110.xx.xx
```

Screenshot Evidence
`EC2_Instance_Running.png`
Tag: **EC2 Instance Running**

---

# Step 5: Set PEM File Permissions

Before connecting, set secure permissions.

```bash
chmod 400 devops-key.pem
# Restricts file permission so only the owner can read it
```

---

# Step 6: Connect to EC2 via SSH

Use the public IP and PEM key.

```bash
ssh -i devops-key.pem ec2-user@<Public-IP>
# Connect to the EC2 instance securely using SSH
```

Example:

```bash
ssh -i devops-key.pem ec2-user@3.110.xx.xx
# Establish SSH connection to Amazon Linux server
```

Screenshot Evidence
`EC2_SSH_Connection.png`
Tag: **SSH Command Connection**

After successful login you will see:

```
[ec2-user@ip-172-31-xx-xx ~]$
```

This indicates you are inside the **remote cloud server**.

---

# Step 7: Update System Packages

Always update packages after launching a new server.

```bash
sudo yum update -y
# Updates all installed packages to the latest versions
```

---

# Step 8: Install Essential Packages

Install Java and useful utilities.

Install Java:

```bash
sudo yum install java-17-amazon-corretto -y
# Installs Amazon Corretto Java runtime
```

Verify installation:

```bash
java -version
# Displays installed Java version
```

Install additional utilities:

```bash
sudo yum install git -y
# Installs Git for version control
```

```bash
sudo yum install wget -y
# Utility for downloading files
```

```bash
sudo yum install unzip -y
# Extract compressed files
```

Screenshot Evidence
`EC2_Java_Install.png`
Tag: **Java Installation**

---

# Basic EC2 Commands

Check system info:

```bash
uname -a
# Displays system kernel information
```

Check disk usage:

```bash
df -h
# Shows disk usage in human readable format
```

Check memory:

```bash
free -m
# Displays memory usage
```

---

# Key Learnings

* Launching **EC2 virtual servers**
* Understanding **key pair authentication**
* Configuring **security groups**
* Connecting to instances using **SSH**
* Installing **Java and essential packages**
* Managing **cloud-based Linux servers**

---

# Final Outcome

By completing **Day 03**, I successfully:

* Launched an **EC2 instance (Amazon Linux)**
* Downloaded and configured **PEM key pair**
* Created and applied **Security Group rules**
* Connected to the server via **SSH**
* Installed **Java and essential packages**

This establishes the **foundation for deploying applications on cloud servers.**

---

# Next Step

**Day 04**
   
✅ Practice Linux commands: file ops, permissions, processes, networking, package mgmt


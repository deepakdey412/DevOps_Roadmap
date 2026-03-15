# Day 05 – Install & Configure Nginx on EC2 🌐

## 📌 Objective

Learn how to install and configure **Nginx web server** on an EC2 instance and host a basic HTML website.

This task includes:

* Installing **Nginx on Amazon Linux**
* Starting and enabling the web server
* Configuring **Security Group for HTTP**
* Hosting a **basic HTML website**
* Accessing the website using **EC2 Public IP**

All commands were executed on **Amazon Linux EC2 instance**.

---

# Step 1: Connect to EC2 Instance

Connect to the server using SSH.

```bash
ssh -i devops-key.pem ec2-user@<Public-IP>
# connects to EC2 instance using SSH key
```

Example:

```bash
ssh -i devops-key.pem ec2-user@3.110.xx.xx
# establishes remote connection to server
```

Image Placeholder
`EC2_SSH_Login.png`
Tag: **SSH Connection**

---

# Step 2: Update System Packages

Before installing software, update the system packages.

```bash
sudo yum update -y
# updates all installed packages to latest version
```

---

# Step 3: Install Nginx

Install the Nginx web server using the package manager.

```bash
sudo amazon-linux-extras install nginx1 -y
# installs nginx package on Amazon Linux
```

Verify installation:

```bash
nginx -v
# displays installed nginx version
```

Image Placeholder
`Nginx_Installation.png`
Tag: **Nginx Installation**

---

# Step 4: Start Nginx Service

Start the Nginx server.

```bash
sudo systemctl start nginx
# starts nginx service
```

Enable Nginx on system boot:

```bash
sudo systemctl enable nginx
# ensures nginx starts automatically after reboot
```

Check service status:

```bash
sudo systemctl status nginx
# displays nginx service status
```

---

# Step 5: Configure Security Group for HTTP

To access the website from the browser, allow **HTTP traffic (port 80)**.

Add inbound rule:

| Type | Protocol | Port | Source    |
| ---- | -------- | ---- | --------- |
| HTTP | TCP      | 80   | 0.0.0.0/0 |

This allows external users to access the web server.

Image Placeholder
`Security_Group_HTTP.png`
Tag: **HTTP Security Group Rule**

---

# Step 6: Verify Nginx Default Page

Open browser and enter:

```
http://<Public-IP>
```

Example:

```
http://3.110.xx.xx
```

If Nginx is running correctly, the **default Nginx welcome page** will appear.

Image Placeholder
`Nginx_Default_Page.png`
Tag: **Nginx Default Page**

---

# Step 7: Host a Basic HTML Website

Nginx serves files from the directory:

```
/usr/share/nginx/html
```

Navigate to the directory:

```bash
cd /usr/share/nginx/html
# nginx default web root
```

Create a simple HTML file:

```bash
sudo nano index.html
# create and edit website homepage
```

Example HTML content:

```html
<!DOCTYPE html>
<html>
<head>
<title>DevOps Practice</title>
</head>
<body>

<h1>Hello from EC2 🚀</h1>
<p>This website is hosted using Nginx on AWS EC2.</p>

</body>
</html>
```

Save the file and exit the editor.

Image Placeholder
`HTML_Website_Create.png`
Tag: **HTML Website Creation**

---

# Step 8: Restart Nginx

Reload the server to apply changes.

```bash
sudo systemctl restart nginx
# restarts nginx service
```

Open the browser again:

```
http://<Public-IP>
```

Now the **custom HTML website** will appear.

Image Placeholder
`Website_Live.png`
Tag: **Website Hosted on EC2**

---

# Useful Nginx Commands

Check nginx status:

```bash
sudo systemctl status nginx
# displays nginx service state
```

Restart nginx:

```bash
sudo systemctl restart nginx
# restarts nginx server
```

Stop nginx:

```bash
sudo systemctl stop nginx
# stops nginx service
```

Test nginx configuration:

```bash
sudo nginx -t
# checks nginx configuration syntax
```

---

# Key Learnings

* Installing **Nginx web server**
* Managing services using **systemctl**
* Configuring **HTTP access using security groups**
* Hosting **static websites on EC2**
* Accessing web applications via **public IP**

---

# Final Outcome

By completing **Day 05**, I successfully:

* Installed and configured **Nginx on EC2**
* Enabled **HTTP access through security group**
* Hosted a **basic HTML website**
* Accessed the website using **public IP**

This demonstrates how cloud servers can be used to **host web applications and websites.**

---

# Next Step

**Day 06**
    
✅ Push HTML/Nginx config/scripts to GitHub    
✅ Organize repo and add README.md


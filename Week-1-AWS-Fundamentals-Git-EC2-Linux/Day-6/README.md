# Day 06 – Push Nginx Website Code to GitHub & Organize Repository 📦

## 📌 Objective

Learn how to version-control infrastructure files and website code using **Git and GitHub**.

This task includes:

* Uploading **HTML website files**
* Uploading **Nginx configuration**
* Uploading **deployment scripts**
* Organizing repository structure
* Creating a proper **README.md**

This helps maintain **project history, collaboration, and reproducibility**.

---

# Step 1: Prepare Project Files

Create a local project folder.

```bash
mkdir nginx-ec2-website
# create project directory
```

Move into the project folder.

```bash
cd nginx-ec2-website
# navigate to project directory
```

Example files included:

```
index.html
nginx.conf
deploy.sh
README.md
```

---

# Step 2: Initialize Git Repository

Initialize git inside the project folder.

```bash
git init
# initializes local git repository
```

Check repository status.

```bash
git status
# shows current tracked and untracked files
```

---

# Step 3: Add Website HTML File

Example HTML file:

```html
<!DOCTYPE html>
<html>
<head>
<title>DevOps Practice</title>
</head>
<body>

<h1>Hello from EC2 🚀</h1>
<p>Website hosted using Nginx on AWS EC2.</p>

</body>
</html>
```

Save as:

```
index.html
```

---

# Step 4: Add Nginx Configuration File

Example configuration file:

```nginx
server {
    listen 80;
    server_name localhost;

    location / {
        root /usr/share/nginx/html;
        index index.html;
    }
}
```

Save as:

```
nginx.conf
```

---

# Step 5: Create Deployment Script

A small script to deploy the website on EC2.

```bash
#!/bin/bash

# copy website files
sudo cp index.html /usr/share/nginx/html/

# restart nginx server
sudo systemctl restart nginx
```

Save as:

```
deploy.sh
```

Make it executable.

```bash
chmod +x deploy.sh
# allows script execution
```

---

# Step 6: Stage Files for Commit

Add all files to staging.

```bash
git add .
# stage all project files
```

Verify staged files.

```bash
git status
# shows staged files ready for commit
```

---

# Step 7: Commit Files

Create a commit snapshot.

```bash
git commit -m "Add Nginx website, config, and deployment script"
# saves project state to repository
```

Check commit history.

```bash
git log
# displays commit history
```

---

# Step 8: Create GitHub Repository

On GitHub:

1. Click **New Repository**
2. Repository name:

```
nginx-ec2-website
```

3. Do **not initialize with README**
4. Copy repository URL.

Example:

```
https://github.com/username/nginx-ec2-website.git
```

---

# Step 9: Connect Local Repository to GitHub

Add remote repository.

```bash
git remote add origin https://github.com/username/nginx-ec2-website.git
# links local repo with GitHub
```

Verify remote connection.

```bash
git remote -v
# shows remote repository URLs
```

---

# Step 10: Push Code to GitHub

Push local commits to GitHub.

```bash
git push -u origin main
# uploads project files to GitHub
```

After this step the repository will contain:

* HTML website
* Nginx configuration
* Deployment script
* README documentation

---

# Step 11: Organize Repository Structure

Recommended project structure:

```
nginx-ec2-website
│
├── website
│   └── index.html
│
├── nginx
│   └── nginx.conf
│
├── scripts
│   └── deploy.sh
│
└── README.md
```

Organized repositories are easier to maintain and scale.

---

# Key Learnings

* Version control using **Git**
* Hosting code on **GitHub**
* Organizing repository structure
* Tracking infrastructure files
* Writing proper project documentation

---

# Final Outcome

By completing **Day 06**, I successfully:

* Uploaded **HTML website files**
* Stored **Nginx configuration**
* Added **deployment scripts**
* Organized repository structure
* Created **project documentation**

This ensures the project is **version controlled and reproducible for future deployments**.

---

# Next Step

**Day 07**

✅ Weekly review & hands-on practice    
✅ Troubleshoot, refactor scripts, and document
# Day 01 – AWS Account Setup & IAM Basics ☁️

## 📌 Objective

Set up an AWS environment for learning cloud and DevOps fundamentals.

This task includes:

* Creating a **new AWS Free Tier account**
* Understanding and configuring **IAM (Identity and Access Management)**
* Creating **IAM Users, Groups, and Roles**
* Securing the account using **MFA**
* Setting up **Billing Alerts**
* Installing and configuring **AWS CLI**

---

# Step 1: Create AWS Free Tier Account

Follow the official AWS guide:
https://aws.amazon.com/resources/create-account/

### Steps Performed

1. Open the AWS account creation page.
2. Click **Create an AWS Account**.
3. Enter the following details:

   * Email Address
   * Password
   * AWS Account Name
4. Choose **Personal Account**.
5. Provide required personal information.
6. Add **Debit/Credit Card for verification**.
7. Verify phone number using OTP.
8. Select **Basic Support Plan (Free)**.
9. Complete account activation.

### Screenshot Evidence

`Account01.png`
Tag: **Account01 ss**

---

# Step 2: Understanding IAM

## What is IAM?

**IAM (Identity and Access Management)** is an AWS service that allows you to securely control access to AWS services and resources.

Using IAM you can:

* Create **users**
* Create **groups**
* Assign **permissions**
* Control **who can access what**

### Why IAM is Important

Using the **root account directly is not recommended** for daily operations.
Instead, AWS best practice is to:

1. Use the root account only for initial setup.
2. Create IAM users for normal usage.

---

# Step 3: Create IAM User

### Steps

1. Go to **AWS Console**
2. Search for **IAM**
3. Open **IAM Dashboard**
4. Click **Users**
5. Click **Create User**
6. Enter username (example: `dev-user`)
7. Select access type:

   * AWS Management Console access
8. Set password

### Screenshot Evidence

`Account02.png`
Tag: **IAM User Creation**

---

# Step 4: Create IAM Group

### What is an IAM Group?

A **Group** is a collection of users that share the same permissions.

Example:

| Group      | Permissions |
| ---------- | ----------- |
| Developers | EC2, S3     |
| Admins     | Full Access |

### Steps

1. Go to **IAM → User Groups**
2. Click **Create Group**
3. Group name: `Developers`
4. Attach policies:

   * `AdministratorAccess` (for learning environment)

### Screenshot Evidence

`Account03.png`

---

# Step 5: Add User to Group

### Steps

1. Open IAM **Users**
2. Select the created user
3. Click **Add to Group**
4. Choose **Developers Group**

This allows the user to inherit group permissions.

---

# Step 6: IAM Roles (Concept)

### What is an IAM Role?

An **IAM Role** allows services to access AWS resources securely without using permanent credentials.

Example:

| Role        | Usage                     |
| ----------- | ------------------------- |
| EC2 Role    | EC2 instance accessing S3 |
| Lambda Role | Lambda accessing DynamoDB |

Roles are commonly used for **service-to-service authentication**.

---

# Step 7: Enable Multi-Factor Authentication (MFA)

### Why MFA?

MFA adds an extra layer of security by requiring:

* Password
* One-time verification code

### Steps

1. Go to **IAM**
2. Select **Users**
3. Choose the user
4. Click **Security Credentials**
5. Enable **MFA**
6. Use **Google Authenticator** or **Microsoft Authenticator**

### Screenshot Evidence

`Account04.png`

---

# Step 8: Configure Billing Alerts

To avoid unexpected charges.

### Steps

1. Open **Billing Dashboard**
2. Go to **Billing Preferences**
3. Enable:

   * Receive Billing Alerts
4. Open **CloudWatch**
5. Create **Billing Alarm**
6. Set threshold (example: **$1**)

### Screenshot Evidence

`Account05.png`

---

# Step 9: Install AWS CLI

### What is AWS CLI?

AWS CLI allows you to interact with AWS services using the command line.

### Install AWS CLI

Official Guide:
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html

### Verify Installation

```bash
aws --version
```

### Configure CLI

```bash
aws configure
```

Enter:

```
Access Key
Secret Key
Region
Output Format
```

---

# Key Learnings

* AWS account setup process
* IAM fundamentals
* Best practice: **Avoid using root account**
* Creating IAM users and groups
* Implementing security with **MFA**
* Setting **billing alerts**
* Using **AWS CLI**

---

# Final Outcome

By completing **Day 01**, I successfully:

* Created an **AWS Free Tier Account**
* Configured **IAM Users and Groups**
* Enabled **MFA Security**
* Set up **Billing Alerts**
* Installed and configured **AWS CLI**

This establishes the **foundation for working with AWS cloud services in future DevOps tasks.**

---

# Next Step

**Day 02**
    
✅ Learn Git basics: init, clone, commit, push    
✅ Branching, pull requests, GitHub protection rules

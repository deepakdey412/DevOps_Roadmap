# Day 09 – Terraform: Create EC2 & Security Groups, Use Variables & user_data 🚀

## 📌 Objective

Use **Terraform** to create an **AWS EC2 instance** along with **security groups**, and automatically install **Nginx** using `user_data`. Learn to use **variables** for dynamic configuration.

This task includes:

* Creating EC2 instances via Terraform
* Creating Security Groups for HTTP/SSH access
* Using Terraform variables for flexibility
* Using `user_data` to auto-install Nginx

---

# Step 1: Create Project Folder & Files

```bash id="projfolder"
mkdir terraform-ec2-nginx
cd terraform-ec2-nginx
```

Create Terraform files:

```bash id="tfcreate"
touch main.tf variables.tf outputs.tf
```

---

# Step 2: Define Variables

**variables.tf**

```hcl id="varsdef"
variable "region" {
  default = "ap-south-1"
}

variable "instance_type" {
  default = "t2.micro"
}

variable "ami_id" {
  default = "ami-0abcdef1234567890"
}

variable "key_name" {
  description = "SSH key name"
  default     = "devops-key"
}
```

---

# Step 3: Define Security Group

**main.tf**

```hcl id="sgdef"
resource "aws_security_group" "web_sg" {
  name        = "web-sg"
  description = "Allow SSH and HTTP"

  ingress {
    description = "SSH"
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  ingress {
    description = "HTTP"
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}
```

---

# Step 4: Create EC2 Instance with user_data

```hcl id="ec2def"
resource "aws_instance" "web" {
  ami                    = var.ami_id
  instance_type           = var.instance_type
  key_name                = var.key_name
  security_groups         = [aws_security_group.web_sg.name]

  user_data = <<-EOF
              #!/bin/bash
              sudo amazon-linux-extras install nginx1 -y
              sudo systemctl start nginx
              sudo systemctl enable nginx
              EOF

  tags = {
    Name = "Terraform-Nginx-EC2"
  }
}
```

> `user_data` runs scripts on **first boot** to install and start Nginx automatically.

---

# Step 5: Define Outputs

**outputs.tf**

```hcl id="outputsdef"
output "ec2_public_ip" {
  value = aws_instance.web.public_ip
  description = "Public IP of EC2 instance"
}
```

---

# Step 6: Terraform Workflow

### Initialize Terraform

```bash id="initcmd"
terraform init
```

### Plan Infrastructure

```bash id="plancmd"
terraform plan
```

### Apply Configuration

```bash id="applycmd"
terraform apply
# type 'yes' to confirm
```

---

# Step 7: Verify EC2 and Nginx

1. Check outputs:

```bash id="outputcmd"
terraform output ec2_public_ip
```

2. Open in browser:

```
http://<Public-IP>
```

You should see the **Nginx default page**.

---

# Step 8: Destroy Infrastructure

Clean up resources:

```bash id="destroycmd"
terraform destroy
# confirm with 'yes'
```

---

# Key Learnings

* Creating **EC2 and Security Groups** via Terraform
* Using **variables** for dynamic configuration
* Automating setup using **user_data**
* Terraform workflow: **init → plan → apply → destroy**
* Accessing outputs and verifying deployed resources

---

# Final Outcome

By completing **Day 09**, I successfully:

* Created EC2 instance and security group using Terraform
* Used **variables** to parameterize configuration
* Auto-installed Nginx using **user_data**
* Accessed the instance via **public IP**
* Learned best practices for **IaC automation**

---

# Next Step

**Day 10**
✅ Configure remote backend with S3 & DynamoDB for state mgmt

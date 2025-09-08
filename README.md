
# 🚀 Packer AMI Build Guide

This repository contains Packer templates to build custom AWS AMIs with Ubuntu, Nginx, Git, and Docker.

---

## 📌 Prerequisites

Before you begin, ensure you have:

- **Ubuntu 24.04 (Noble) or later**
- **AWS Account** with programmatic access
- **AWS CLI** installed and configured (`aws configure`)
- **Git** installed
- **Visual Studio Code** (optional)

---

## 🔧 Install HashiCorp Packer on Ubuntu

```bash
# Add HashiCorp GPG key
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg

# Add the repository
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com noble main" | sudo tee /etc/apt/sources.list.d/hashicorp.list

# Update package index and install Packer
sudo apt update
sudo apt install packer -y

Verify installation:

packer --version

📂 Project Setup

# Clean workspace
clear
ls -la

# Navigate to your workspace
cd devops-world/

# Create a project directory
mkdir packer-ubuntu
code .

Clone this repository:
git clone https://github.com/sheakimran/packer.git
cd packer
ls -la
code .


✅ Validate and Build with Packer

Validate the Packer template:

packer validate packer.json


Install the Amazon plugin:

packer plugins install github.com/hashicorp/amazon


Validate again:

packer validate packer.json


Build the AMI:

packer build -var-file=packer-vars.json packer.json

🎉 Done!

After a successful run, Packer will output the AMI ID of your newly created image.
You can now use this AMI to launch EC2 instances with your pre-installed stack.

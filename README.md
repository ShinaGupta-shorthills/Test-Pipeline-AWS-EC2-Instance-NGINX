# 🚀 GitHub Actions CI Pipeline to Provision AWS EC2 (Ubuntu) and Install NGINX

This project demonstrates how to use **GitHub Actions** to automatically launch an **Ubuntu EC2 instance on AWS** and install **NGINX** using a cloud-init script.

---

## 📦 What This Project Does

- ✅ Spins up an Ubuntu EC2 instance using GitHub Actions
- ✅ Installs and starts NGINX web server via user-data script
- ✅ Outputs the public IP of the instance so you can view the NGINX welcome page
- ✅ (Optional) Automatically terminates the EC2 instance after setup to avoid charges

---

## 🧰 Prerequisites

- AWS Account
- IAM User with `AmazonEC2FullAccess`
- A key pair created in AWS (for SSH access)
- GitHub repository with:
  - `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` stored as **repository secrets**

---

## 🔐 How to Set Up Secrets

Go to your GitHub repo:

1. Navigate to `Settings > Secrets and variables > Actions`
2. Click `New repository secret` and add:
   - `AWS_ACCESS_KEY_ID`
   - `AWS_SECRET_ACCESS_KEY`

---

## 📁 Project Structure
## 🚦 How to Run

1. Click on the **"Actions"** tab in your GitHub repo
2. Select the workflow: `Launch Ubuntu EC2 and Install NGINX`
3. Click **"Run workflow"**
4. After a few minutes, you'll get the **public IP** of the EC2 instance in the logs
5. Visit `http://<public-ip>` in your browser to see the **NGINX Welcome Page**

---

## 📝 Notes

- Ensure your **default security group** allows **inbound HTTP (port 80)** traffic.
- The EC2 instance type used is `t2.micro` (free tier eligible).
- You can optionally include a cleanup step to **terminate the instance** after provisioning.

---

## 📸 Sample Output

```bash
Your EC2 instance is ready. Access NGINX at: http://18.222.123.45


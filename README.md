🌐 Terraform VPC Project – AWS Infrastructure Deployment

This project demonstrates how to use Terraform to provision a complete VPC network architecture on AWS, including public & private subnets, NAT gateway, route tables, internet gateway, security groups, and an EC2 instance running Apache HTTP server.

This is a great beginner-friendly DevOps project for understanding Infrastructure as Code (IaC) using Terraform.

🚀 What This Project Deploys

Using Terraform, this project automatically creates:

🔹 Networking Setup

A custom VPC (10.0.0.0/16)

Public subnet (10.0.1.0/24)

Private subnet (10.0.2.0/24)

Internet Gateway for internet access

Public route table (with IGW route)

Private route table (with NAT Gateway route)

Elastic IP for NAT

NAT Gateway for private subnet internet access

🔹 Security

EC2 Security Group allowing:

Port 22 (SSH)

Port 80 (HTTP)

🔹 Compute

EC2 instance (Amazon Linux 2)

Automatically installs Apache Web Server

Hosts a sample website: “Hello Terraform!”

🧱 Terraform File Structure
terraform-vpc-project/
│── main.tf
│── providers.tf
│── variables.tf
│── outputs.tf
│── terraform.tfvars   (optional)
│── README.md

⚙️ How to Use This Project
1️⃣ Clone the Repository
git clone https://github.com/paulxatanu/terraform-vpc-project.git
cd terraform-vpc-project

2️⃣ Initialize Terraform
terraform init

3️⃣ Validate
terraform validate

4️⃣ See the Deployment Plan
terraform plan

5️⃣ Deploy Infrastructure
terraform apply


Type yes when prompted.

6️⃣ Get the EC2 Public IP
terraform output

7️⃣ SSH into the Server
ssh -i YOUR_KEY.pem ec2-user@YOUR_PUBLIC_IP

8️⃣ Destroy Infrastructure (Optional)
terraform destroy

📸 Architecture Diagram
             ┌───────────────────────────────┐
             │             VPC                │
             │          (10.0.0.0/16)         │
             │                                 │
 ┌──────────────┐                       ┌──────────────┐
 │ Public Subnet │                       │ Private Subnet│
 │ (10.0.1.0/24) │                       │ (10.0.2.0/24) │
 └───────┬────────┘                       └──────┬───────┘
         │                                        │
   ┌────────────┐                         ┌──────────────┐
   │  EC2 (Web) │ ←───── SG Allow 22,80 ──│ NAT Gateway  │
   └────────────┘                         └──────────────┘
         │                                        │
   ┌──────────────┐                         ┌──────────────┐
   │ Internet GW  │                         │ Elastic IP   │
   └──────────────┘                         └──────────────┘

🛠️ Technologies Used

Terraform

AWS VPC, Subnets, IGW, NAT GW

Amazon EC2

Security Groups

Apache Web Server (httpd)

📌 Why This Project Is Useful

Teaches real-world Infrastructure as Code (IaC)

Helps build DevOps foundation

Demonstrates complete AWS VPC architecture

Good for resume, portfolio, and interview preparation

👨‍💻 Author

Atanu Paul
🌐 GitHub: https://github.com/paulxatanu

# Create-a-VPC-with-Public-Private-Subnets

# AWS VPC — Public & Private Subnets

**Short description:**  
A simple, hands-on AWS networking project that demonstrates creation of a custom VPC with one public subnet and one private subnet. The public subnet has an Internet Gateway for inbound/outbound internet access; the private subnet routes outbound traffic through a NAT Gateway (keeps instances private). Includes optional steps to launch EC2 instances to validate connectivity.

---

## 🔍 Project Objectives
- Create a custom VPC (`10.0.0.0/16`)
- Create a Public Subnet (`10.0.1.0/24`) and a Private Subnet (`10.0.2.0/24`)
- Attach an Internet Gateway (IGW) to the VPC and route public subnet traffic to IGW
- Create a NAT Gateway (with Elastic IP) in the public subnet for private subnet outbound access
- Create separate Route Tables for public and private subnets and associate them correctly
- (Optional) Launch EC2 instances in both subnets to validate behavior

---

## 🧰 Services Used
- VPC
- Subnet
- Internet Gateway (IGW)
- Route Tables
- NAT Gateway
- Elastic IP
- EC2
- Security Groups

---

## 📝 Prerequisites
- An AWS account with permission to create VPCs, EC2, Elastic IPs, NAT Gateways, and Route Tables
- AWS CLI configured (optional, for CLI steps)
- Basic knowledge of networking (CIDR, routing)

---

## ⚙️ Architecture Diagram (text)
MyVPC (10.0.0.0/16)
├── PublicSubnet (10.0.1.0/24) -> RouteTable: PublicRT -> 0.0.0.0/0 -> InternetGateway
│ └── NAT Gateway + Elastic IP
└── PrivateSubnet (10.0.2.0/24) -> RouteTable: PrivateRT -> 0.0.0.0/0 -> NAT Gateway

# AWS-Secure-Architecture-Project
AWS 2-Tier Architecture: A secure, high-availability VPC network isolating RDS workloads in private subnets with tiered Security Groups
# Secure 2-Tier AWS Architecture (Manual Build)

## 📌 Project Overview
I designed and manually configured a secure 2-tier network on AWS. The goal was to isolate the database layer from the public internet while allowing the application layer to handle web traffic.

## 🛠️ Infrastructure Components
- **VPC:** 10.0.0.0/16 custom network.
- **Public Subnets:** Hosted EC2 web servers.
- **Private Subnets:** Isolated RDS database instances.
- **Security:** Used Security Group Referencing (DB only accepts traffic from App SG).

## 📊 Network Diagram
![Network Diagram](./images/APPFLOW.png)


## 🛡️ Security Implementation
- **Isolation:** The DB has no Route Table entry for the Internet Gateway.
- **NACLs:** Configured as a secondary firewall layer at the subnet level.
- **Access Control:** Verified that SSH is only allowed from my specific IP.

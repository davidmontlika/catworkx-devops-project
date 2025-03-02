# catworkx-devops-project
Hands-on DevOps project for catworkx interview preparation.

# catworkx-devops-project

This repository documents the hands-on DevOps lab project designed for preparing for a DevOps position at catworkx (EverIT). The project focuses on building a small but production-like AWS environment with a strong focus on networking, security, and essential AWS services.

---

## 🏗️ Project Scope

- Build a **VPC** with public and private subnets.
- Deploy a **Management EC2 instance** in the public subnet.
- Deploy an **RDS PostgreSQL** database in the private subnet.
- Use **AWS SSM Session Manager** for secure access — no open SSH port.
- Document all steps, configurations, and decisions for future reference.

---

## 🌐 Architecture Overview

![VPC Design](architecture/vpc-design.png)

### Key Components
| Component | Description |
|---|---|
| VPC | 10.0.0.0/22 |
| Public Subnet | EC2 Management Server (Debian) |
| Private Subnet | RDS PostgreSQL (private only) |
| Internet Access | Public Subnet only (IGW) |
| Security | Strict SG rules, no public access to DB |

---

## 📜 Documentation Structure

| File/Folder | Description |
|---|---|
| `README.md` | Project summary and key information |
| `architecture/` | Diagrams and architecture-related docs |
| `terraform/` | Infrastructure as Code (optional future step) |
| `scripts/` | Automation scripts (SSM install, etc.) |
| `docs/` | Detailed explanations (e.g., subnet, SG) |

---

## 🚀 Current State

- [x] VPC created
- [x] Public and private subnets created
- [x] Internet Gateway attached
- [x] Public Route Table configured
- [x] Private Route Table configured
- [x] Security Groups for EC2 and RDS created
- [x] SSM installation script ready

---

## 📖 Key Learnings

- **Network segregation:** Public vs Private subnet, why it's important
- **Zero trust principle:** No open ports unless strictly needed
- **SSM best practice:** No SSH, only Session Manager
- **Private DB:** RDS reachable only from the Management Server
- **AWS Console mastery:** VPC, EC2, RDS hands-on

---

## 📚 Next Steps

- Deploy EC2 with SSM user data
- Deploy RDS with proper security group
- Test DB connection from EC2
- Document ECS + ECR setup for the next phase

---

## 💬 Why This Project Matters

This project is designed to:
- Prove hands-on AWS and DevOps skills
- Showcase understanding of **secure AWS networking**
- Demonstrate ability to **document infrastructure** (critical for teamwork)
- Be a **real-world mini reference architecture**, reusable later for production

---

## 📝 Notes

This is **a personal learning project** and is not officially affiliated with catworkx or EverIT. It serves as a demonstration of DevOps skills required for similar roles.


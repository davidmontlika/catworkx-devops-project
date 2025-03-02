# Architecture Details

## VPC

- CIDR: 10.0.0.0/22
- Divided into:
    - Public Subnet (10.0.0.0/24)
    - Private Subnet (10.0.1.0/24)

## Public Subnet

- Contains: EC2 Management Server (Debian)
- Security Group:
    - Inbound: SSM only (no SSH)
    - Outbound: all open (to allow apt updates, ECR push)

## Private Subnet

- Contains: RDS PostgreSQL
- Security Group:
    - Inbound: PostgreSQL (5432) only from Management Server SG
    - Outbound: all open (default)

## Connectivity

| Source | Destination | Protocol | Notes |
|---|---|---|---|
| Management Server | RDS | PostgreSQL (5432) | Internal DB connection |
| Management Server | Internet | HTTPS | Package updates, Docker push |
| Local Workstation | Management Server | SSM | Secure admin access |

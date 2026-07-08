# Cloud Native Media Streaming Platform Architecture

A cloud-native backend architecture design for a YouTube-like media streaming platform built using AWS services and enterprise cloud design principles.

## Project Overview

This project demonstrates the design of a scalable, highly available, and fault-tolerant backend architecture for a large-scale video streaming platform.

The architecture is designed to handle:

- Large numbers of concurrent users
- High traffic spikes caused by viral content
- Secure backend communication
- Automatic scaling based on demand
- High availability across multiple Availability Zones

## Architecture Components

### Networking

- Amazon VPC
- Public and Private Subnets
- Internet Gateway
- NAT Gateway

### Compute

- Amazon EC2
- Auto Scaling Group
- Bastion Host

### Load Balancing

- Application Load Balancer (ALB)

### Storage

- Amazon S3 for video storage
- Amazon RDS PostgreSQL for metadata storage

### Monitoring

- Amazon CloudWatch
- CloudWatch Alarms

## Architecture Flow

1. Users access the platform through the internet.
2. Traffic enters through the Internet Gateway.
3. The Application Load Balancer distributes requests to backend EC2 instances.
4. Backend services retrieve metadata from Amazon RDS.
5. Video files are served directly from Amazon S3.
6. CloudWatch continuously monitors infrastructure health and performance.

## High Availability Features

- Multi-Availability Zone deployment
- Load balancing across EC2 instances
- Automatic replacement of unhealthy instances
- Auto Scaling based on CPU utilization
- Multi-AZ database deployment

## Auto Scaling Strategy

### Scale Out

- **Trigger:** CPU Utilization > 70%
- **Action:** Launch additional EC2 instances

### Scale In

- **Trigger:** CPU Utilization < 30%
- **Action:** Terminate unused EC2 instances

## Security Design

- Backend services run inside private subnets.
- Databases are inaccessible from the public internet.
- Administrative access is provided through a Bastion Host.
- NAT Gateways allow outbound internet access for private resources.

## Estimated Monthly Cost

### Normal Traffic

**Estimated Cost:** $386.99/month

### High Traffic

**Estimated Cost:** $1,379.96/month

## Technologies Used

- AWS EC2
- AWS VPC
- AWS RDS PostgreSQL
- AWS S3
- AWS CloudWatch
- Application Load Balancer
- Auto Scaling Group

## Learning Outcomes

This project strengthened understanding of:

- Cloud-native architecture
- AWS networking
- High availability design
- Auto Scaling strategies
- Cost optimization
- Enterprise application architecture

## Repository Structure

```text
.
├── architecture-diagram/
├── cost-analysis/
├── documentation/
├── screenshots/
└── README.md
```

## Members
- Thiri Htet
- Swan Htet Aung
- Thant Zin Min

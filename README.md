# Cloud-Engineering-Fundamentals-II

**AWS Well-Architected Framework (WAF) Compliant Architecture**


**Overview**
This repository contains a production-ready AWS architecture diagram designed according to AWS Well-Architected Framework (WAF) and Cloud Adoption Framework (CAF) best practices. The architecture addresses all five WAF pillars while maintaining simplicity and clarity.

**Design Approach**
1. Multi-Tier Architecture
Public Subnet: Houses internet-facing components (ALB with AWS WAF, NAT Gateway)

Private Subnets (Multi-AZ): Contains application servers with Auto Scaling for resilience

Data Subnets (Multi-AZ): Hosts RDS database with Multi-AZ deployment for high availability

**2. Security-First Design**
AWS WAF: Protects against web exploits at the edge

Network Segmentation: Strict separation between public, private, and data layers

IAM & KMS: Identity management and encryption at rest/in-transit

GuardDuty: Continuous security monitoring

**3. High Availability & Reliability**
Multi-AZ Deployment: Application and database tiers span multiple Availability Zones

Auto Scaling Groups: Self-healing compute capacity

RDS Multi-AZ: Synchronous database replication for failover

**4. Performance Optimization**
Application Load Balancer: Distributes traffic efficiently

Auto Scaling: Right-sizes compute resources based on demand

Read Replicas: Optional scaling for read-heavy workloads

**5. Cost Optimization**
Reserved Instances: Significant savings for predictable workloads

Budgets & Cost Explorer: Continuous cost monitoring and optimization

S3 Lifecycle Policies: Automated storage tier management

**WAF Pillars Implementation**
Pillar	Implementation	Key Services
Operational Excellence	Monitoring, Logging, Automation	CloudWatch, CloudTrail, AWS Config
Security	Defense-in-depth, Encryption	IAM, KMS, WAF, GuardDuty, Security Hub
Reliability	Multi-AZ, Auto-healing	Auto Scaling, RDS Multi-AZ, ALB Health Checks
Performance Efficiency	Load Distribution, Scaling	ALB, Auto Scaling, RDS Read Replicas
Cost Optimization	Cost Control, Resource Optimization	Reserved Instances, Budgets, S3 Lifecycle
Deployment Flow
User Request → AWS WAF (Security Filtering)

AWS WAF → Application Load Balancer (Traffic Distribution)

ALB → App Servers (Auto-scaled across AZs)

App Servers → RDS Multi-AZ (Database Tier)

Private Resources → NAT Gateway (Outbound Internet)

Validation
This architecture can be validated using the AWS Well-Architected Tool in the AWS Console, answering questions across all five pillars to ensure compliance with AWS best practices.

Usage
Cloud Architects: Reference for WAF-compliant designs

Developers: Understand infrastructure dependencies

Security Teams: Review security controls and boundaries

Operations: Plan monitoring and maintenance procedures


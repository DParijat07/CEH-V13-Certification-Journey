# Module 19 – Cloud Computing

## Part 1 – Cloud Computing Fundamentals

---

# Overview

Cloud Computing is the on-demand delivery of computing resources such as servers, storage, databases, networking, software, analytics, and security services over the Internet.

Instead of purchasing and maintaining physical infrastructure, organizations can use cloud services on a pay-as-you-go basis, enabling greater flexibility, scalability, and cost efficiency.

Cloud computing has transformed how businesses build, deploy, and manage applications, making it one of the most important technologies in modern cybersecurity.

---

# What is Cloud Computing?

Cloud Computing is a model that provides convenient, on-demand network access to a shared pool of configurable computing resources.

These resources include:

- Compute (Virtual Machines)
- Storage
- Databases
- Networking
- Applications
- Security Services
- Artificial Intelligence Services
- Analytics Platforms

Resources can be rapidly provisioned and released with minimal management effort.

---

# Evolution of Cloud Computing

Cloud computing evolved from earlier computing models.

### Main Evolution Stages

1. Mainframe Computing
2. Client-Server Computing
3. Grid Computing
4. Utility Computing
5. Virtualization
6. Cloud Computing
7. Edge Computing

Each stage improved resource sharing, scalability, and accessibility.

---

# Essential Characteristics of Cloud Computing

According to the NIST definition, cloud computing has five essential characteristics.

## 1. On-Demand Self-Service

Users can provision computing resources automatically without interacting directly with the service provider.

Examples:

- Launching a virtual machine
- Creating cloud storage
- Deploying databases

---

## 2. Broad Network Access

Cloud services are accessible through standard network technologies using devices such as:

- Computers
- Smartphones
- Tablets
- Thin clients

---

## 3. Resource Pooling

Cloud providers pool computing resources to serve multiple customers using a multi-tenant architecture.

Resources include:

- Servers
- Storage
- Memory
- Networking
- Processing power

---

## 4. Rapid Elasticity

Resources can automatically scale up or down based on demand.

Benefits include:

- High availability
- Improved performance
- Cost optimization

---

## 5. Measured Service

Cloud usage is monitored and billed based on actual consumption.

Common billing metrics include:

- CPU usage
- Storage
- Network bandwidth
- Memory
- API requests

---

# Benefits of Cloud Computing

Organizations adopt cloud computing because it offers:

- Scalability
- High availability
- Cost savings
- Business agility
- Global accessibility
- Automatic updates
- Disaster recovery capabilities
- Faster application deployment
- Reduced infrastructure management
- Improved collaboration

---

# Challenges of Cloud Computing

Despite its advantages, cloud computing introduces several challenges.

Common challenges include:

- Data privacy concerns
- Regulatory compliance
- Vendor lock-in
- Misconfiguration
- Identity management complexity
- Shared responsibility
- Internet dependency
- Security monitoring
- Multi-cloud management

---

# Cloud Terminology

Common cloud-related terms include:

### Tenant

A customer using cloud services.

### Multi-Tenancy

Multiple customers securely share the same cloud infrastructure.

### Region

A geographic location containing cloud data centers.

### Availability Zone (AZ)

An isolated data center within a cloud region designed to improve resilience.

### Instance

A virtual machine or compute resource running in the cloud.

### Workload

An application or service executing on cloud resources.

---

# Virtualization

## Overview

Virtualization is the technology that enables multiple virtual systems to run on a single physical computer.

Instead of dedicating one server to one operating system, virtualization allows several isolated virtual machines to share the same hardware.

### Advantages

- Better hardware utilization
- Lower infrastructure costs
- Faster provisioning
- Improved scalability
- Easier disaster recovery
- Simplified testing environments

Virtualization is one of the core technologies that enables cloud computing.

---

# Hypervisors

## Overview

A hypervisor is software that creates and manages virtual machines (VMs).

It allocates hardware resources such as CPU, memory, storage, and networking to each VM while keeping them isolated.

---

## Type 1 Hypervisor (Bare Metal)

Runs directly on physical hardware.

Examples include:

- VMware ESXi
- Microsoft Hyper-V
- Xen
- KVM

Advantages:

- High performance
- Better security
- Enterprise deployments

---

## Type 2 Hypervisor (Hosted)

Runs on top of a host operating system.

Examples include:

- VMware Workstation
- Oracle VirtualBox
- VMware Fusion

Advantages:

- Easy installation
- Suitable for testing
- Common in home labs

---

# Virtual Machines (VMs)

A Virtual Machine is an isolated software-based computer running its own operating system.

Each VM includes:

- Virtual CPU
- Virtual Memory
- Virtual Storage
- Virtual Network Interface
- Guest Operating System

Multiple VMs can run simultaneously on a single physical server.

---

# Containers

## Overview

Containers package applications together with their dependencies while sharing the host operating system kernel.

Unlike virtual machines, containers do not require separate guest operating systems.

Popular container technologies include:

- Docker
- Podman
- containerd

### Advantages

- Lightweight
- Fast startup
- Efficient resource utilization
- Easy deployment
- Portability

Containers are widely used in DevOps and cloud-native applications.

---

# Container Orchestration

When organizations deploy hundreds or thousands of containers, orchestration platforms manage them automatically.

Common orchestration platforms include:

- Kubernetes
- OpenShift
- Docker Swarm

Responsibilities include:

- Scheduling
- Scaling
- Load balancing
- Self-healing
- Service discovery

---

# Serverless Computing

## Overview

Serverless Computing allows developers to run application code without managing servers.

The cloud provider automatically handles:

- Infrastructure
- Scaling
- Availability
- Patching
- Resource allocation

Common serverless platforms include:

- AWS Lambda
- Azure Functions
- Google Cloud Functions

Benefits include:

- Reduced operational overhead
- Automatic scaling
- Pay-per-execution pricing
- Faster development

---

# Cloud Providers

Major cloud service providers include:

- Amazon Web Services (AWS)
- Microsoft Azure
- Google Cloud Platform (GCP)
- Oracle Cloud Infrastructure (OCI)
- IBM Cloud
- Alibaba Cloud

Each provider offers compute, storage, networking, databases, security services, and AI capabilities.

---

# CEH Exam Tips

Remember:

- Cloud computing provides on-demand computing resources over the Internet.
- NIST defines five essential cloud characteristics.
- Virtualization enables multiple VMs on one physical system.
- Hypervisors create and manage virtual machines.
- Containers share the host OS kernel and are lighter than VMs.
- Kubernetes is a popular container orchestration platform.
- Serverless computing allows code execution without managing servers.
- Cloud services are billed using a measured service model.

---

# Key Takeaways

- Cloud computing delivers scalable, on-demand computing resources while reducing infrastructure management.
- Virtualization, containers, and serverless computing are foundational technologies that power modern cloud environments.
- Understanding cloud fundamentals is essential for securing cloud workloads and preparing for CEH, SOC, and cloud security roles.

# Module 19 – Cloud Computing

## Part 2 – Cloud Architecture

---

# Overview

Cloud architecture defines how cloud services, infrastructure, networking, storage, and applications work together to deliver scalable and reliable computing services.

A well-designed cloud architecture provides high availability, security, fault tolerance, and efficient resource utilization.

Understanding cloud architecture is essential for cybersecurity professionals because security controls must be implemented across every layer of the cloud environment.

---

# Cloud Architecture

Cloud architecture consists of interconnected components that provide computing services over the Internet.

Major architectural components include:

- Frontend
- Backend
- Compute Resources
- Storage
- Networking
- Identity Services
- Management Services
- Security Services

These components work together to deliver cloud applications securely and efficiently.

---

# Frontend

The frontend is the part of the cloud environment that users interact with.

Examples include:

- Web browsers
- Mobile applications
- Desktop applications
- APIs
- Command Line Interfaces (CLI)

Responsibilities:

- User interaction
- Authentication requests
- Application access
- Data presentation

---

# Backend

The backend consists of cloud infrastructure and services responsible for processing user requests.

Components include:

- Virtual machines
- Databases
- Storage systems
- Networking infrastructure
- Identity services
- Monitoring systems

Responsibilities:

- Resource allocation
- Data processing
- Application execution
- Security enforcement

---

# Compute Services

Compute services provide processing power for applications.

Examples include:

- Virtual Machines (VMs)
- Containers
- Serverless Functions
- Bare Metal Instances

Compute resources can scale automatically based on demand.

---

# Storage Services

Cloud providers offer different storage options depending on application requirements.

### Object Storage

Stores files as objects.

Examples:

- Images
- Videos
- Backups
- Documents

---

### Block Storage

Provides storage volumes for virtual machines.

Common uses:

- Operating systems
- Databases
- Enterprise applications

---

### File Storage

Provides shared file systems accessible by multiple systems simultaneously.

Typical use cases include:

- Shared folders
- Application storage
- Team collaboration

---

# Networking Services

Networking connects cloud resources securely.

Common networking components include:

- Virtual Networks
- Virtual Private Cloud (VPC)
- Subnets
- Routers
- Gateways
- Load Balancers
- Firewalls
- DNS

Networking enables communication between cloud services and users.

---

# Virtual Private Cloud (VPC)

A Virtual Private Cloud is an isolated virtual network within a public cloud.

Benefits include:

- Network isolation
- Custom IP addressing
- Security policy enforcement
- Controlled routing

Most cloud deployments begin with a VPC.

---

# Subnets

Subnets divide a VPC into smaller network segments.

Common subnet types:

### Public Subnet

Contains systems accessible from the Internet.

Examples:

- Web servers
- Reverse proxies
- Load balancers

---

### Private Subnet

Contains systems that should not be directly accessible from the Internet.

Examples:

- Databases
- Application servers
- Internal services

Private subnets improve security by reducing external exposure.

---

# Load Balancers

Load balancers distribute incoming traffic across multiple servers.

Benefits include:

- High availability
- Fault tolerance
- Improved performance
- Automatic traffic distribution

---

# Domain Name System (DNS)

DNS translates domain names into IP addresses.

Example:

```
example.com
        ↓
203.0.113.15
```

Cloud providers offer managed DNS services for improved scalability and reliability.

---

# Identity and Access Management (IAM)

## Overview

Identity and Access Management (IAM) controls who can access cloud resources and what actions they are permitted to perform.

IAM is one of the most important security services in cloud environments.

---

# IAM Components

Typical IAM components include:

- Users
- Groups
- Roles
- Policies
- Permissions

---

## Users

Represents an individual identity.

Examples:

- Administrator
- Developer
- Security Analyst

---

## Groups

A collection of users with similar responsibilities.

Example:

```
Security Team
 ├── Alice
 ├── Bob
 └── Charlie
```

Permissions are assigned to the group instead of individual users.

---

## Roles

Roles provide temporary permissions to users, services, or applications.

Examples:

- EC2 Instance Role
- Backup Service Role
- Monitoring Role

Roles reduce the need for long-term credentials.

---

## Policies

Policies define what actions are allowed or denied.

Example permissions:

- Read storage
- Launch virtual machines
- Delete databases
- Manage users

Organizations should follow the Principle of Least Privilege.

---

# Principle of Least Privilege

Users should receive only the minimum permissions required to perform their job.

Benefits include:

- Reduced attack surface
- Lower insider risk
- Improved compliance
- Better access control

---

# Shared Responsibility Model

Cloud security responsibilities are shared between the cloud provider and the customer.

### Cloud Provider Responsibilities

Typically includes:

- Physical security
- Data centers
- Networking infrastructure
- Hardware
- Hypervisors

---

### Customer Responsibilities

Typically includes:

- User accounts
- IAM policies
- Operating systems (IaaS)
- Applications
- Data protection
- Encryption
- Configuration management

The exact responsibilities depend on the cloud service model being used.

---

# Cloud Data Flow

A simplified cloud request follows this path:

```
User
   ↓
DNS
   ↓
Load Balancer
   ↓
Web Server
   ↓
Application Server
   ↓
Database
   ↓
Storage
```

Security controls should be applied throughout the entire data flow.

---

# Cloud Security Layers

Cloud environments should implement security across multiple layers:

- Identity
- Network
- Compute
- Storage
- Applications
- Data
- Monitoring

This layered approach supports Defense-in-Depth.

---

# High Availability

Cloud providers improve availability using:

- Multiple Availability Zones
- Load balancing
- Automatic failover
- Data replication
- Redundant networking

High availability minimizes service interruptions.

---

# Scalability

Cloud platforms support:

### Vertical Scaling

Increase CPU, memory, or storage of an existing system.

### Horizontal Scaling

Add additional servers or instances.

Horizontal scaling is commonly used in cloud-native environments.

---

# Fault Tolerance

Fault tolerance allows services to continue operating despite failures.

Techniques include:

- Redundant infrastructure
- Automatic failover
- Data replication
- Backup systems

---

# CEH Exam Tips

Remember:

- Frontend interacts with users.
- Backend processes requests.
- VPC provides network isolation.
- Public subnets host Internet-facing systems.
- Private subnets host internal systems.
- IAM controls access to cloud resources.
- Users, Groups, Roles, and Policies form the foundation of IAM.
- Least Privilege reduces security risks.
- The Shared Responsibility Model divides security responsibilities between provider and customer.
- High availability uses redundancy and load balancing.

---

# Key Takeaways

- Cloud architecture combines networking, compute, storage, identity, and security services to deliver scalable applications.
- IAM, network segmentation, and the Shared Responsibility Model are essential concepts for securing cloud environments.
- Understanding cloud architecture enables cybersecurity professionals to design, monitor, and defend cloud workloads effectively.

# Module 19 – Cloud Computing

## Part 3 – Cloud Service Models and Deployment Models

---

# Overview

Cloud providers deliver computing resources through standardized service models and deployment models.

Service models define **what type of cloud service is provided**, while deployment models define **where and how the cloud infrastructure is deployed**.

Understanding these models is essential for cloud security because security responsibilities vary depending on the selected model.

---

# Cloud Service Models

The four primary cloud service models are:

- Infrastructure as a Service (IaaS)
- Platform as a Service (PaaS)
- Software as a Service (SaaS)
- Function as a Service (FaaS)

---

# Infrastructure as a Service (IaaS)

## Overview

Infrastructure as a Service (IaaS) provides virtualized computing infrastructure over the Internet.

Customers rent computing resources instead of purchasing physical hardware.

Typical resources include:

- Virtual Machines
- Storage
- Networking
- Firewalls
- Load Balancers

### Customer Responsibilities

Customers manage:

- Operating Systems
- Applications
- Data
- User Accounts
- Network Configuration
- Security Configuration

### Cloud Provider Responsibilities

The provider manages:

- Physical servers
- Storage hardware
- Networking hardware
- Hypervisors
- Data centers

### Advantages

- High flexibility
- Full operating system control
- Scalable infrastructure
- Pay-as-you-go pricing

### Examples

- Amazon EC2
- Microsoft Azure Virtual Machines
- Google Compute Engine

---

# Platform as a Service (PaaS)

## Overview

Platform as a Service provides a managed platform for developing and deploying applications.

Developers focus on application development while the provider manages the underlying infrastructure.

### Customer Responsibilities

Customers manage:

- Applications
- Application code
- Data
- User access

### Cloud Provider Responsibilities

The provider manages:

- Operating system
- Middleware
- Runtime environment
- Infrastructure
- Networking

### Advantages

- Faster development
- Simplified deployment
- Reduced infrastructure management
- Automatic updates

### Examples

- Google App Engine
- Azure App Service
- AWS Elastic Beanstalk

---

# Software as a Service (SaaS)

## Overview

Software as a Service delivers complete software applications through a web browser or mobile application.

Users simply access the software without managing infrastructure.

### Customer Responsibilities

Customers manage:

- User accounts
- Access permissions
- Data entered into the application

### Cloud Provider Responsibilities

The provider manages:

- Infrastructure
- Operating systems
- Applications
- Updates
- Security patches
- Availability

### Advantages

- No installation required
- Automatic updates
- Low maintenance
- Rapid deployment

### Examples

- Microsoft 365
- Google Workspace
- Salesforce
- Dropbox

---

# Function as a Service (FaaS)

## Overview

Function as a Service (FaaS), also known as Serverless Computing, allows developers to execute code without managing servers.

Applications run only when triggered by events.

### Advantages

- Automatic scaling
- Pay-per-execution
- Reduced operational overhead
- Fast deployment

### Examples

- AWS Lambda
- Azure Functions
- Google Cloud Functions

---

# Comparison of Cloud Service Models

| Feature | IaaS | PaaS | SaaS | FaaS |
|----------|------|------|------|------|
| Infrastructure Management | Customer | Provider | Provider | Provider |
| Operating System Management | Customer | Provider | Provider | Provider |
| Application Management | Customer | Customer | Provider | Customer |
| Scalability | High | High | High | Automatic |
| Administrative Control | Highest | Moderate | Lowest | Limited |

---

# Shared Responsibility by Service Model

As organizations move from IaaS to SaaS, more security responsibilities shift to the cloud provider.

### IaaS

Customer manages:

- Operating System
- Applications
- Data
- Identity
- Network configuration

---

### PaaS

Customer manages:

- Applications
- Data
- Identity

---

### SaaS

Customer primarily manages:

- User identities
- Access permissions
- Data governance

---

### FaaS

Customer manages:

- Application code
- Function permissions
- Sensitive data

---

# Cloud Deployment Models

Cloud deployment models determine where cloud resources are hosted and who owns the infrastructure.

The main deployment models are:

- Public Cloud
- Private Cloud
- Hybrid Cloud
- Community Cloud
- Multi-Cloud

---

# Public Cloud

## Overview

Public cloud infrastructure is owned and managed by a third-party cloud provider.

Resources are shared among multiple customers using multi-tenancy.

### Advantages

- Cost-effective
- Highly scalable
- Rapid deployment
- Global availability

### Challenges

- Shared infrastructure
- Regulatory considerations
- Vendor dependency

---

# Private Cloud

## Overview

Private cloud infrastructure is dedicated to a single organization.

It may be hosted:

- On-premises
- By a third-party provider

### Advantages

- Greater control
- Improved customization
- Enhanced privacy
- Better regulatory compliance

### Challenges

- Higher cost
- Increased management responsibility

---

# Hybrid Cloud

## Overview

Hybrid cloud combines public cloud and private cloud environments.

Organizations decide which workloads remain private and which are hosted in the public cloud.

### Benefits

- Flexibility
- Disaster recovery
- Cost optimization
- Regulatory compliance

Hybrid cloud is common in enterprise environments.

---

# Community Cloud

## Overview

Community cloud infrastructure is shared by organizations with similar requirements.

Examples include:

- Government agencies
- Healthcare organizations
- Educational institutions

Benefits include:

- Shared costs
- Common security policies
- Regulatory alignment

---

# Multi-Cloud

## Overview

Multi-cloud refers to the use of cloud services from multiple providers.

Example:

- AWS
- Microsoft Azure
- Google Cloud Platform

### Benefits

- Vendor diversity
- Improved resilience
- Reduced vendor lock-in
- Service optimization

### Challenges

- Complex management
- Identity integration
- Monitoring consistency

---

# Cloud Adoption Considerations

Organizations evaluate several factors before migrating to the cloud.

Common considerations include:

- Security
- Compliance
- Cost
- Performance
- Availability
- Scalability
- Business continuity
- Vendor support
- Data residency
- Disaster recovery

---

# Common Cloud Use Cases

Cloud computing supports:

- Web hosting
- Application development
- Big data analytics
- Artificial Intelligence
- Backup and recovery
- Disaster recovery
- Remote collaboration
- DevOps
- Machine learning
- Content delivery

---

# CEH Exam Tips

Remember:

- IaaS provides virtual infrastructure.
- PaaS provides a development platform.
- SaaS delivers complete software applications.
- FaaS executes code without server management.
- Public cloud uses shared infrastructure.
- Private cloud is dedicated to one organization.
- Hybrid cloud combines public and private environments.
- Multi-cloud uses multiple cloud providers.
- Security responsibilities vary depending on the selected service model.

---

# Key Takeaways

- Cloud service models determine how computing resources are delivered, while deployment models determine where those resources are hosted.
- Understanding the Shared Responsibility Model is critical because customer security obligations change across IaaS, PaaS, SaaS, and FaaS.
- Selecting the appropriate deployment model depends on business, security, compliance, and operational requirements.

# Module 19 – Cloud Computing

## Part 4 – Cloud Security Threats

---

# Overview

Cloud computing introduces a shared and scalable environment, but it also creates new security challenges. Misconfigurations, weak identity management, insecure APIs, exposed storage, and credential theft are among the most common causes of cloud security incidents.

Understanding these threats helps security professionals implement effective preventive, detective, and corrective controls.

---

# Cloud Misconfiguration

## Overview

Cloud misconfiguration occurs when cloud resources are deployed with insecure or incorrect settings.

Examples include:

- Publicly accessible storage buckets
- Open security groups
- Excessive IAM permissions
- Disabled logging
- Default configurations

### Risks

- Data exposure
- Unauthorized access
- Compliance violations
- Service compromise

### Defensive Controls

- Configuration reviews
- CSPM (Cloud Security Posture Management)
- Least Privilege
- Continuous monitoring

---

# Weak Identity and Access Management (IAM)

IAM protects cloud identities and permissions.

Common weaknesses include:

- Overprivileged accounts
- Shared administrator accounts
- Weak passwords
- Missing MFA
- Poor role separation

### Defensive Controls

- Multi-Factor Authentication (MFA)
- Role-Based Access Control (RBAC)
- Principle of Least Privilege
- Regular access reviews

---

# Credential Theft

Cloud accounts are valuable targets for attackers.

Methods include:

- Phishing
- Password reuse
- Malware
- Keylogging
- Credential stuffing

### Defensive Controls

- MFA
- Password managers
- Strong password policies
- Login monitoring
- Identity analytics

---

# Account Hijacking

Account hijacking occurs when attackers obtain unauthorized control of cloud accounts.

Potential impacts include:

- Resource deletion
- Data theft
- Cryptojacking
- Privilege escalation
- Service disruption

### Defensive Controls

- MFA
- Conditional access
- Session monitoring
- Login alerts
- Risk-based authentication

---

# Data Breaches

Cloud data breaches may expose sensitive information due to:

- Misconfigured storage
- Weak access control
- Credential compromise
- Insider threats
- Insecure APIs

### Defensive Controls

- Encryption
- Access control
- Data classification
- Monitoring
- Data Loss Prevention (DLP)

---

# Insecure APIs

Cloud platforms rely heavily on APIs.

Weak APIs may suffer from:

- Poor authentication
- Missing authorization
- Injection attacks
- Excessive permissions
- Information disclosure

### Defensive Controls

- API authentication
- Authorization checks
- TLS encryption
- Input validation
- Rate limiting

---

# Insider Threats

Insiders may intentionally or accidentally compromise cloud environments.

Examples include:

- Accidental data exposure
- Misconfiguration
- Credential misuse
- Unauthorized downloads

### Defensive Controls

- Least Privilege
- Logging
- User behavior monitoring
- Separation of duties
- Security awareness

---

# Shadow IT

Shadow IT refers to cloud services used without organizational approval.

Examples include:

- Personal cloud storage
- Unauthorized SaaS applications
- Personal collaboration platforms

### Risks

- Data leakage
- Compliance violations
- Poor visibility
- Unmanaged identities

### Defensive Controls

- CASB
- Cloud governance
- Asset discovery
- User awareness

---

# Malware

Cloud workloads may be affected by malware through:

- Infected virtual machines
- Malicious files
- Compromised applications
- Supply chain attacks

### Defensive Controls

- Endpoint protection
- Anti-malware
- EDR/XDR
- Continuous monitoring

---

# Ransomware

Cloud ransomware may encrypt:

- Virtual machines
- Cloud storage
- Databases
- Backups

### Defensive Controls

- Offline backups
- Immutable storage
- Backup testing
- MFA
- Incident response planning

---

# Cryptojacking

Cryptojacking uses cloud resources to mine cryptocurrency without authorization.

Indicators include:

- High CPU usage
- Increased cloud costs
- Unexpected workloads
- Resource exhaustion

### Defensive Controls

- Cost monitoring
- Workload monitoring
- IAM security
- Resource usage alerts

---

# Container Security Risks

Containers introduce risks such as:

- Vulnerable images
- Misconfigured Kubernetes clusters
- Privileged containers
- Secret exposure
- Insecure registries

### Defensive Controls

- Image scanning
- Signed images
- Runtime monitoring
- Kubernetes hardening
- Least privilege

---

# Supply Chain Attacks

Cloud environments often depend on third-party components.

Potential targets include:

- Software libraries
- CI/CD pipelines
- Container images
- Package repositories

### Defensive Controls

- Vendor assessment
- Software Bill of Materials (SBOM)
- Code signing
- Dependency scanning

---

# Metadata Service Attacks

Cloud instances often expose metadata services used to retrieve instance information.

Improperly secured applications may allow attackers to access sensitive metadata.

### Defensive Controls

- Restrict metadata access
- Use secure metadata service versions
- Validate application inputs
- Monitor unusual metadata requests

---

# Denial-of-Service (DoS) and Distributed Denial-of-Service (DDoS)

Attackers may attempt to exhaust cloud resources by generating excessive traffic.

Potential impacts include:

- Service outages
- Increased operational costs
- Application downtime

### Defensive Controls

- Auto scaling
- Web Application Firewalls (WAF)
- DDoS protection services
- Rate limiting
- Load balancing

---

# Common Cloud Attack Surface

Typical attack surfaces include:

- IAM
- APIs
- Storage services
- Virtual machines
- Containers
- Serverless functions
- Kubernetes clusters
- CI/CD pipelines
- DNS
- Public IP addresses

---

# Blue Team Detection Opportunities

Security teams should monitor for:

- Impossible travel logins
- Excessive failed logins
- Privilege changes
- New administrator accounts
- Public storage exposure
- API abuse
- Unusual data transfers
- Unexpected virtual machine creation
- Cryptomining indicators
- Unauthorized container deployments

---

# Security Monitoring Checklist

Regularly review:

- IAM policies
- MFA status
- Security groups
- Firewall rules
- Storage permissions
- API logs
- Cloud activity logs
- Billing anomalies
- Resource inventory
- Vulnerability reports

---

# CEH Exam Tips

Remember:

- Misconfiguration is one of the leading causes of cloud breaches.
- IAM is the foundation of cloud security.
- MFA significantly reduces account compromise.
- APIs are common attack targets.
- Containers require image and runtime security.
- Cryptojacking consumes cloud resources for unauthorized cryptocurrency mining.
- Shadow IT introduces unmanaged cloud risks.
- Continuous monitoring is essential for cloud security.

---

# Key Takeaways

- Cloud environments face threats including misconfiguration, weak IAM, credential theft, insecure APIs, ransomware, cryptojacking, insider threats, and supply chain attacks.
- Strong identity management, secure configurations, encryption, monitoring, and layered defenses help reduce cloud security risks.
- Blue Teams should continuously monitor cloud activity, enforce least privilege, and rapidly respond to abnormal behavior.

# Module 19 – Cloud Computing

## Part 5 – Cloud Security Defense and Best Practices

---

# Overview

Cloud security requires a combination of technical controls, governance, monitoring, and incident response. Since cloud environments operate under the Shared Responsibility Model, organizations must secure their identities, applications, data, and configurations while cloud providers secure the underlying infrastructure.

A layered security strategy improves resilience against modern cloud threats.

---

# Defense-in-Depth

## Overview

Defense-in-Depth is a layered security strategy that applies multiple independent security controls throughout a cloud environment.

Typical security layers include:

- Physical Security
- Identity Security
- Network Security
- Compute Security
- Application Security
- Data Security
- Monitoring
- Incident Response

Even if one security layer fails, additional layers continue providing protection.

---

# Zero Trust

## Overview

Zero Trust is based on the principle:

> **Never Trust, Always Verify**

Every request must be authenticated, authorized, and continuously validated regardless of where it originates.

### Core Principles

- Verify identity continuously
- Enforce least privilege
- Validate device posture
- Assume breach
- Monitor continuously

Zero Trust has become a core security model for modern cloud environments.

---

# Identity and Access Management (IAM) Best Practices

Organizations should:

- Enable Multi-Factor Authentication (MFA)
- Apply the Principle of Least Privilege
- Use Role-Based Access Control (RBAC)
- Regularly review permissions
- Remove unused accounts
- Rotate credentials
- Avoid shared administrator accounts

Strong IAM significantly reduces the risk of unauthorized access.

---

# Multi-Factor Authentication (MFA)

MFA requires users to provide two or more authentication factors.

Common factors include:

- Password (Something you know)
- Security token (Something you have)
- Biometric authentication (Something you are)

Benefits include:

- Reduced credential theft risk
- Protection against phishing
- Improved account security

---

# Encryption

Encryption protects sensitive information both while stored and while transmitted.

### Data at Rest

Examples include:

- Encrypted databases
- Encrypted object storage
- Encrypted virtual disks

### Data in Transit

Common technologies:

- TLS
- HTTPS
- VPN
- IPsec

Encryption supports confidentiality and integrity.

---

# Key Management Service (KMS)

A Key Management Service securely creates, stores, rotates, and manages cryptographic keys.

Benefits include:

- Centralized key management
- Secure encryption
- Key rotation
- Access control
- Compliance support

---

# Secrets Management

Applications often require sensitive credentials.

Examples include:

- API Keys
- Database passwords
- Access tokens
- Certificates

Secrets should never be hardcoded into applications.

Organizations should use centralized secrets management solutions.

---

# Network Security

Cloud network security includes:

- Virtual Private Clouds (VPCs)
- Firewalls
- Security Groups
- Network Access Control Lists (ACLs)
- VPNs
- Private Endpoints

Network segmentation limits attack propagation.

---

# Web Application Firewall (WAF)

A WAF protects web applications from common web-based attacks.

Examples include:

- SQL Injection
- Cross-Site Scripting (XSS)
- Malicious HTTP requests
- Bot traffic

WAFs inspect HTTP and HTTPS traffic before it reaches applications.

---

# Cloud Access Security Broker (CASB)

CASB provides visibility and security for cloud service usage.

Capabilities include:

- Shadow IT detection
- Data Loss Prevention (DLP)
- Access control
- Threat protection
- Compliance monitoring

CASBs improve governance across SaaS applications.

---

# Cloud Security Posture Management (CSPM)

CSPM solutions continuously assess cloud configurations.

Typical capabilities include:

- Misconfiguration detection
- Compliance monitoring
- Risk assessment
- Policy enforcement
- Continuous compliance

CSPM helps identify insecure cloud settings before attackers can exploit them.

---

# Cloud Workload Protection Platform (CWPP)

CWPP protects cloud workloads such as:

- Virtual Machines
- Containers
- Kubernetes
- Serverless Functions

Features include:

- Vulnerability scanning
- Runtime protection
- Malware detection
- Integrity monitoring

---

# Logging and Monitoring

Continuous monitoring is essential for cloud security.

Common log sources include:

- Authentication logs
- API activity logs
- Firewall logs
- Network flow logs
- Database logs
- Storage access logs
- Container logs
- Kubernetes audit logs

Logs support threat detection, investigations, and compliance.

---

# Security Information and Event Management (SIEM)

SIEM platforms collect and correlate security events from multiple cloud services.

Typical functions include:

- Centralized logging
- Alert generation
- Threat detection
- Incident investigation
- Compliance reporting

Cloud-native logs are often integrated into enterprise SIEM platforms.

---

# Backup and Disaster Recovery

Organizations should maintain backups for:

- Virtual Machines
- Databases
- Storage
- Configuration files
- Critical business data

Best practices include:

- Automated backups
- Encryption
- Regular testing
- Geographic redundancy
- Defined Recovery Objectives

---

# Incident Response

A cloud incident response process typically includes:

1. Preparation
2. Detection
3. Analysis
4. Containment
5. Eradication
6. Recovery
7. Lessons Learned

Cloud logging and automation help accelerate response activities.

---

# MITRE ATT&CK in Cloud Environments

The MITRE ATT&CK Enterprise framework helps defenders understand attacker techniques used against cloud environments.

Security teams use ATT&CK to:

- Improve detections
- Guide threat hunting
- Build SIEM use cases
- Enhance incident response

---

# Cloud Security Best Practices

Organizations should:

- Enable MFA everywhere possible
- Enforce least privilege
- Encrypt sensitive data
- Use centralized logging
- Continuously monitor cloud activity
- Patch workloads regularly
- Scan container images
- Secure APIs
- Maintain asset inventories
- Test incident response plans
- Review cloud configurations regularly
- Implement Zero Trust

---

# CEH Exam Tips

Remember:

- Defense-in-Depth uses multiple security layers.
- Zero Trust requires continuous verification.
- IAM is the foundation of cloud security.
- MFA reduces account compromise.
- KMS manages encryption keys.
- CASB provides visibility into cloud usage.
- CSPM identifies cloud misconfigurations.
- CWPP protects workloads.
- SIEM centralizes security monitoring.
- Logging is critical for investigations.

---

# Module Summary

In this module you learned:

- Cloud computing fundamentals
- Cloud architecture
- Service models
- Deployment models
- Virtualization
- Containers
- Serverless computing
- Shared Responsibility Model
- IAM
- Cloud threats
- Cloud security controls
- Defense-in-Depth
- Zero Trust
- Encryption
- Cloud monitoring
- SIEM integration
- Backup and disaster recovery
- Incident response

These concepts provide the foundation required for securing modern cloud environments and are highly relevant for CEH, SOC, Blue Team, Cloud Security, and Security Operations roles.

---

# Key Takeaways

- Cloud security is based on shared responsibility between the provider and the customer.
- Strong identity management, secure configurations, encryption, continuous monitoring, and layered defenses are essential for protecting cloud environments.
- Cloud security professionals must understand both cloud technologies and modern cybersecurity practices to effectively defend cloud workloads and services.

# Cloud Fundamentals

## Overview

Cloud Computing is the on-demand delivery of computing resources such as servers, storage, databases, networking, software, and security services over the Internet. Instead of purchasing and maintaining physical infrastructure, organizations consume cloud resources as needed using a pay-as-you-go model.

Cloud computing enables businesses to rapidly deploy applications, improve scalability, reduce operational costs, and support digital transformation.

---

# What is Cloud Computing?

Cloud Computing is a model that provides convenient, on-demand access to a shared pool of configurable computing resources.

These resources include:

- Compute
- Storage
- Networking
- Databases
- Applications
- Security Services
- Analytics
- Artificial Intelligence Services

Resources can be rapidly provisioned and released with minimal management effort.

---

# Evolution of Cloud Computing

Cloud computing evolved from earlier computing models.

Major stages include:

- Mainframe Computing
- Client-Server Computing
- Grid Computing
- Utility Computing
- Virtualization
- Cloud Computing
- Edge Computing

Each stage improved scalability, resource sharing, and accessibility.

---

# Essential Characteristics

According to NIST, cloud computing has five essential characteristics.

## 1. On-Demand Self-Service

Users can provision computing resources automatically without interacting directly with the provider.

Examples:

- Launch virtual machines
- Create storage
- Deploy databases

---

## 2. Broad Network Access

Cloud services are accessible through standard network technologies using:

- Computers
- Smartphones
- Tablets
- Thin clients

---

## 3. Resource Pooling

Cloud providers pool computing resources to serve multiple customers through multi-tenancy.

Resources include:

- CPU
- Memory
- Storage
- Networking
- Processing power

---

## 4. Rapid Elasticity

Resources automatically scale based on demand.

Benefits include:

- High availability
- Better performance
- Cost optimization

---

## 5. Measured Service

Cloud providers monitor resource usage and charge customers based on consumption.

Typical billing metrics include:

- CPU usage
- Storage capacity
- Network bandwidth
- Memory usage
- API requests

---

# Benefits of Cloud Computing

Organizations adopt cloud computing because it offers:

- Scalability
- Elasticity
- High availability
- Cost efficiency
- Global accessibility
- Automatic updates
- Disaster recovery
- Faster deployment
- Business agility
- Improved collaboration

---

# Challenges of Cloud Computing

Common challenges include:

- Data privacy
- Compliance requirements
- Vendor lock-in
- Misconfiguration
- Identity management complexity
- Internet dependency
- Shared responsibility
- Multi-cloud management

---

# Cloud Terminology

## Tenant

A customer using cloud services.

---

## Multi-Tenancy

Multiple customers securely share the same cloud infrastructure.

---

## Region

A geographic location containing one or more cloud data centers.

---

## Availability Zone (AZ)

An isolated data center within a cloud region that improves availability and fault tolerance.

---

## Instance

A virtual machine or compute resource running in the cloud.

---

## Workload

An application, service, or process executing on cloud infrastructure.

---

# Virtualization

## Overview

Virtualization allows multiple virtual machines (VMs) to run on a single physical server.

Each virtual machine operates independently while sharing physical hardware.

### Advantages

- Better hardware utilization
- Lower infrastructure costs
- Faster provisioning
- Easier disaster recovery
- Improved scalability

Virtualization is a foundational technology for cloud computing.

---

# Hypervisors

A hypervisor creates and manages virtual machines.

## Type 1 Hypervisor (Bare Metal)

Runs directly on physical hardware.

Examples:

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

Examples:

- VMware Workstation
- Oracle VirtualBox
- VMware Fusion

Advantages:

- Easy installation
- Home labs
- Testing environments

---

# Virtual Machines (VMs)

A Virtual Machine is an isolated software-based computer.

Each VM includes:

- Virtual CPU
- Virtual Memory
- Virtual Storage
- Virtual Network Interface
- Guest Operating System

Multiple VMs can run simultaneously on one physical host.

---

# Containers

## Overview

Containers package applications and their dependencies while sharing the host operating system kernel.

Unlike virtual machines, containers do not require a separate guest operating system.

Popular technologies include:

- Docker
- Podman
- containerd

### Advantages

- Lightweight
- Fast startup
- Efficient resource utilization
- Portability
- Easy deployment

---

# Container Orchestration

Container orchestration platforms manage large-scale container deployments.

Popular platforms include:

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

Serverless Computing allows developers to execute code without managing servers.

The cloud provider automatically manages:

- Infrastructure
- Scaling
- Availability
- Patching
- Resource allocation

Examples include:

- AWS Lambda
- Azure Functions
- Google Cloud Functions

Benefits include:

- Automatic scaling
- Reduced operational overhead
- Pay-per-execution pricing
- Faster development

---

# Major Cloud Providers

Leading cloud providers include:

- Amazon Web Services (AWS)
- Microsoft Azure
- Google Cloud Platform (GCP)
- Oracle Cloud Infrastructure (OCI)
- IBM Cloud
- Alibaba Cloud

These providers offer compute, storage, networking, security, databases, AI, and analytics services.

---

# CEH Exam Tips

Remember:

- Cloud computing delivers on-demand computing resources over the Internet.
- NIST defines five essential cloud characteristics.
- Virtualization enables multiple virtual machines on one physical server.
- Hypervisors create and manage virtual machines.
- Containers share the host operating system kernel.
- Kubernetes is a leading container orchestration platform.
- Serverless computing executes code without server management.
- Cloud services typically use a pay-as-you-go billing model.

---

# Key Takeaways

- Cloud computing provides scalable, flexible, and cost-efficient access to computing resources.
- Virtualization, containers, and serverless computing form the technological foundation of modern cloud platforms.
- Understanding cloud fundamentals is essential for securing cloud environments and preparing for CEH, SOC, Blue Team, and cloud security roles.

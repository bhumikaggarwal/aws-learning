# Cloud Service Models (IaaS, PaaS & SaaS)

## What are Cloud Service Models?

Cloud Service Models define **how cloud resources are delivered** and **how responsibilities are shared** between the cloud provider (AWS, Azure, GCP) and the customer.

As we move from **IaaS → PaaS → SaaS**, the cloud provider manages more, while the customer manages less.

> **Remember:** More convenience = Less control.

---

# Shared Responsibility

| Managed By         | Responsibility                                                             |
| ------------------ | -------------------------------------------------------------------------- |
| **Cloud Provider** | Physical servers, networking, storage, virtualization, data centers        |
| **Customer**       | Applications, data, configurations, users (depending on the service model) |

The amount of customer responsibility changes based on the service model.

---

# 1. Infrastructure as a Service (IaaS)

## Definition

Infrastructure as a Service (IaaS) provides virtualized computing resources such as virtual machines, storage, and networking over the internet.

The cloud provider manages the physical infrastructure, while the customer manages everything running on top of it.

### What the Cloud Provider Manages

* Physical servers
* Storage hardware
* Networking
* Data centers
* Virtualization (Hypervisor)

### What the Customer Manages

* Operating System
* Security patches
* Installed software
* Runtime
* Applications
* Data
* User access

### AWS Examples

* Amazon EC2
* Amazon EBS
* Amazon VPC
* Elastic Load Balancer (ELB)

### Real-Life Example

Suppose you launch an Ubuntu EC2 instance.

AWS provides:

* A virtual machine
* CPU
* RAM
* Storage
* Networking

You are responsible for:

* Installing Ubuntu updates
* Installing Nginx
* Installing Docker
* Deploying your application
* Managing security updates

Example:

```bash
sudo apt update
sudo apt install nginx
```

AWS does **not** install Nginx for you.

### Advantages

* Full control over the server
* Highly customizable
* Suitable for DevOps and system administration

### Disadvantages

* Requires server management
* Responsible for updates and maintenance
* More operational effort

### Common Use Cases

* Hosting websites
* DevOps environments
* Kubernetes clusters
* Docker deployments
* Testing environments

---

# 2. Platform as a Service (PaaS)

## Definition

Platform as a Service (PaaS) provides a complete platform for developing, deploying, and managing applications.

The cloud provider manages the infrastructure, operating system, runtime, and scaling.

The customer only focuses on the application and its data.

### What the Cloud Provider Manages

* Infrastructure
* Networking
* Storage
* Operating System
* Runtime
* Middleware
* Scaling
* Security patches

### What the Customer Manages

* Application code
* Application configuration
* Data

### AWS Examples

* AWS Elastic Beanstalk
* AWS Lambda (Serverless)
* Amazon RDS (Managed Database)

### Real-Life Example

You have developed a Python Django application.

Instead of:

* Creating a server
* Installing Python
* Configuring Nginx
* Setting up Gunicorn

You simply upload your code to Elastic Beanstalk.

AWS automatically:

* Creates the server
* Installs required software
* Deploys your application
* Scales resources when needed

### Advantages

* Faster deployment
* No server management
* Automatic scaling
* Easier maintenance

### Disadvantages

* Less flexibility
* Limited customization
* Vendor-specific configurations

### Common Use Cases

* Web applications
* REST APIs
* Backend services
* Startup projects

---

# 3. Software as a Service (SaaS)

## Definition

Software as a Service (SaaS) delivers complete software applications over the internet.

The cloud provider manages everything, and users simply access the software through a browser or application.

### What the Cloud Provider Manages

* Infrastructure
* Operating System
* Application
* Security updates
* Maintenance
* Data storage
* Availability

### What the Customer Manages

* User account
* Personal data
* Application settings

### Examples

* Gmail
* Microsoft 365
* Salesforce
* Zoom
* Canva

### Real-Life Example

When using Gmail:

* You don't install Linux.
* You don't configure servers.
* You don't perform software updates.

You simply log in and send emails.

Google manages everything behind the scenes.

### Advantages

* No installation required
* Accessible from anywhere
* Automatic updates
* Minimal maintenance

### Disadvantages

* Limited customization
* Less control over the software
* Subscription-based pricing

### Common Use Cases

* Email services
* Video conferencing
* Office productivity tools
* CRM software
* Online collaboration tools

---

# Responsibility Comparison

| Component        | On-Premises | IaaS     | PaaS     | SaaS      |
| ---------------- | ----------- | -------- | -------- | --------- |
| Applications     | You         | You      | You      | Provider  |
| Data             | You         | You      | You      | Provider* |
| Runtime          | You         | You      | Provider | Provider  |
| Middleware       | You         | You      | Provider | Provider  |
| Operating System | You         | You      | Provider | Provider  |
| Virtualization   | You         | Provider | Provider | Provider  |
| Servers          | You         | Provider | Provider | Provider  |
| Storage          | You         | Provider | Provider | Provider  |
| Networking       | You         | Provider | Provider | Provider  |

> *In SaaS, the provider manages the application and infrastructure, while you remain responsible for the content and data you store or create within the application.

---

# Quick Comparison

| Feature           | IaaS                          | PaaS                  | SaaS                    |
| ----------------- | ----------------------------- | --------------------- | ----------------------- |
| Full Form         | Infrastructure as a Service   | Platform as a Service | Software as a Service   |
| Customer Controls | OS, Applications, Data        | Applications, Data    | Only usage and settings |
| Server Access     | Yes                           | Usually No            | No                      |
| Flexibility       | High                          | Medium                | Low                     |
| Maintenance       | High                          | Medium                | Very Low                |
| Best For          | DevOps, System Administrators | Developers            | End Users               |

---

# AWS Service Classification

| AWS Service       | Service Model           | Reason                                                                     |
| ----------------- | ----------------------- | -------------------------------------------------------------------------- |
| Amazon EC2        | IaaS                    | Customer manages the operating system and software.                        |
| Amazon EBS        | IaaS                    | Storage attached to virtual machines.                                      |
| Amazon VPC        | IaaS                    | Customer controls networking configuration.                                |
| Elastic Beanstalk | PaaS                    | Deploy applications without managing servers.                              |
| AWS Lambda        | PaaS (Serverless)       | Run code without provisioning servers.                                     |
| Amazon RDS        | PaaS                    | AWS manages the database infrastructure and patching.                      |
| Amazon S3         | Managed Storage Service | AWS manages storage infrastructure; customer manages data and permissions. |

---

# Easy Analogy

Imagine you want a meal.

### On-Premises

You buy groceries, cook, clean the kitchen, and maintain everything yourself.

### IaaS

You rent a fully equipped kitchen.
You bring the ingredients and cook the meal.

### PaaS

You receive a ready-to-cook meal kit.
You simply cook and serve it.

### SaaS

You visit a restaurant.
The restaurant prepares and serves the food.
You simply eat.

---

# Key Takeaways

* **IaaS** → You manage the Operating System, applications, and data.
* **PaaS** → You manage only the application and data.
* **SaaS** → You simply use the software; the provider manages everything else.

### Memory Trick

**IaaS → "I Manage the Server."**

**PaaS → "I Manage the Code."**

**SaaS → "I Just Use the Software."**

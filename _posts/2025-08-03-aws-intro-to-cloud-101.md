---
title: "AWS: Introduction to Cloud 101"
author: Kleiner
categories: [Amazon Web Service]
tags: [AWS, Amazon S3, Amazon EC2]
render_with_liquid: false
media_subpath: /images/aws/intro_to_cloud_101
image:
  path: aws_logo.png
---

[![AWS Educate Room Link](aws_edu.webp){: width="600" height="300" .shadow}](https://aws.amazon.com/education/awseducate/){: .center }

## Why Learn Cloud Computing?
With the growing demand for cloud solutions across industries, it's increasingly important for IT professionals to sharpen their skills in this area.

Cloud computing allows IT assets—such as storage, servers, and databases—to be treated as programmable resources. This enables rapid provisioning and deprovisioning of infrastructure, which isn't feasible with traditional on-premises systems.

One of the key advantages is scalability. Resources like database throughput or compute capacity can be scaled up or down as needed. A standout feature of cloud services is the pay-as-you-go model, which lets organizations experiment and run workloads without long-term commitments.

## What is Cloud Computing?
Cloud computing is the on-demand delivery of IT resources over the internet, charged based on usage.

This on-demand delivery (ODD) means that you can access the right amount of computing resources exactly when you need them, thus eliminating the need for costly upfront investments or over-provisioning.

## Understanding Cloud Model
Modern computing operates primarily on the client-server model.

- A client refers to applications like web browsers or desktop apps through which users interact with systems and send requests.

- A server processes those requests and delivers services. In cloud computing, servers can include services like Amazon Elastic Compute Cloud (Amazon EC2)—a virtual server hosted in the cloud.


## Cloud Service and Deployment Models
Cloud computing offers various service models and deployment strategies, each providing different levels of control, flexibility, and management:

### Service Models

  - Infrastructure as a Service (IaaS)
    - IaaS provides the foundational building blocks for cloud IT. This includes access to networking features, compute power (virtual or bare metal), and storage. It offers the highest level of flexibility and administrative control over your IT resources.
    - Examples: Amazon EC2, Amazon S3, Amazon RDS, Amazon Route 53

  - Platform as a Service (PaaS)
    - PaaS eliminates the need for organizations to manage the underlying infrastructure (hardware, operating systems, etc.). Instead, they can focus solely on deploying and managing their applications. This model improves developer productivity by abstracting resource provisioning, capacity planning, and system maintenance.
    - Example: AWS Elastic Beanstalk enables rapid deployment and scaling of web applications.

  - Software as a Service (SaaS)
    - SaaS delivers fully functional software applications over the internet. The cloud provider manages everything—servers, storage networking, updates—so users can simply access and use the application without worrying about the backend.
    - Examples: Email services, video conferencing platforms, file sharing tools, and messaging applications.

### Deployment Strategies

  - Cloud: Entirely hosted in the cloud with no on-premises infrastructure.
  - Hybrid: A mix of on-premises infrastructure and cloud services.
  - On-Premises: Traditional IT setup where all resources are hosted locally and managed by the organization.

#### Cloud-Based Deployment
In a cloud-based deployment, you can either:
  - Migrate existing applications to the cloud, or
  - Design and build new cloud-native applications from scratch.

These applications can be deployed on:
  - Low-level infrastructure services, which require your IT team to manage tasks such as networking, compute, and storage, or
  - Managed services, which reduce the burden of infrastructure management, scaling, and system architecture.
    - Example:
    - A company builds a cloud-native application composed of virtual servers, databases, and networking components, all fully deployed and managed in the cloud.

#### Hybrid Deployment
A hybrid deployment connects on-premises infrastructure with cloud-based resources. This model allows you to integrate modern cloud services with existing legacy systems.

Hybrid deployments are useful when:
  - Certain legacy applications are better maintained on-premises.
  - Regulatory requirements mandate local storage of specific data.
    - Example:
    - A company uses cloud services for automated data processing and analytics. However, due to compliance and architecture limitations, some older applications remain on-premises. A hybrid setup enables the company to benefit from cloud analytics while keeping essential legacy apps locally hosted.

## AWS Global Infrastructure
AWS has the concept of a REgion, which is a physical location around the world where data centers are clustered together.
A group of logical data centers is called an Availability Zone.
Each AWS Region consists of multiple, isolated and physically separate Availability ZOnes within a geographic area.

### Availability Zone
A zoned area within a Region that can harbor one or more data centers (typically three). These house all the hardware devies that AWS offers.

The Availability ZOnes are physically separated by a meaningful distance (up to 100km or 60 miles) from any other Availability Zone in the Region.

Availability Zones are interconnected with a high-bandwith, low-latency netowrking, to provide low-latency networking between zones that is sufficient to accomplish synchronous replication (same time replication).

### Edge Locations
Edge Locations are connected to the AWS Regions through the AWS network across the globe. They link with tens of thousands of networks for improved origin fetches and dynamic content acceleration.

Edge locations cache copies of the content for faster delivery to users at any location. They support AWS Services like Amazone Route 53 and Amazon Cloudfront.

AWS has over 200 edge locations that are placed in 90 cities, across 47 countries.

## Shared Responsibility 
Customers are responsible for the security of everything that they create and put IN the AWS Cloud. These requirements include which content to be stored on AWS, which AWS services to use, and who has access to that content by controlling how access rights are granted, managed and revoked. Examples are User Access, Encryption etc.

AWS manages the security OF the could, specifically the physical infrastructure that hosts the resources, including:
1. Physical security of data centers
2. Hardware and software infrastructure
3. Network infrastructure
4. Virtualization Infrastructure

## AWS Well Architected Framework
The AWS Well Architected Framework consists of 6 pillars:
1. Operation Excellence
2. Security
3. Reliability
4. Performance Efficiency
5. Cost Optimization
6. Sustainability

Operational Excellence
: Ability to run and monitor systems efficiently while improving processes over time.
Key practices: use code for operations, document clearly, plan for failure, and make safe, small changes.

Security
: Protect data, systems, and assets while maintaining business value.
- Automate security wherever possible
- Secure every layer
- Protect data in transit and at rest

Reliability
: Keep systems running and recover from failures.
- Handling disruptions
- Scaling resources dynamically
- Testing recovery
- Auto-recovery from failures

Performance Efficiency
: Use cloud resources effectively as demands evolve.
: Focus areas: experiment frequently, use serverless when possible, and design to scale globally.

Cost Optimization
: Deliver value at the lowest cost.
- Pay only for what you use
- Monitor and analyze spending
- Use managed services to lower ownership cost

Sustainability
: Minimize the environmental impact of your workloads.
: Key areas: shared responsibility, understanding impact, and optimizing usage to reduce resource waste.

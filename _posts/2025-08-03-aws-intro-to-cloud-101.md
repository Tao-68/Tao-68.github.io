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
    - A company builds a cloud-native application composed of virtual servers, databases, and networking components, all fully deployed and managed in the cloud.

#### Hybrid Deployment
A hybrid deployment connects on-premises infrastructure with cloud-based resources. This model allows you to integrate modern cloud services with existing legacy systems.

Hybrid deployments are useful when:
  - Certain legacy applications are better maintained on-premises.
  - Regulatory requirements mandate local storage of specific data.
    - A company uses cloud services for automated data processing and analytics. However, due to compliance and architecture limitations, some older applications remain on-premises. A hybrid setup enables the company to benefit from cloud analytics while keeping essential legacy apps locally hosted.

## AWS Global Infrastructure
### Region
AWS has the concept of a Region, which is a physical location around the world where data centers are clustered together.
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

## AWS Pricing Models
### Pay-as-you-go
You can use pay-as-you-go to quickly adjust to changing business needs without overcommitting budgets.
This model lets you scale based on actual demand—not forecasts—reducing the risk of overprovisioning or resource shortages.

### Save when you reserve
Savings Plans let you save on AWS compute, ML, and database services by committing to a specific usage ($/hour) over 1 or 3 years.
They offer lower rates compared to On-Demand pricing in exchange for this commitment.

### Pay less by using more
AWS offers volume-based discounts, meaning the more you use, the less you pay per unit.
For example, Amazon S3 uses tiered pricing—cost per GB decreases as usage increases.

## Short Demo of Amazon Web Services
### Introduction to Amazon Simple Storage Service (Amazon S3) 
1. In the AWS Console, search for S3 and click Create bucket.
2. Set a unique bucket name and choose a region.
3. Leave Object Ownership at default (ACLs disabled – recommended).
4. Block all public access (tick the checkbox).
5. Click the bucket name to open it.
6. Upload files/folders via the Upload button or drag & drop.
7. Confirm upload success via the message prompt.
8. Access files via Object URL in your browser.
- If access is denied:
  - Go to the Permissions tab.
  - Disable “Block public access” (Only if you define a policy)
  - Add a bucket policy and save changes.
  - Ensure ARNs match the bucket name.
- Once public access is enabled and policy set, the bucket will be marked as publicly accessible.

### Introduction to Amazon Elastic Compute Cloud (Amazon EC2)
1. In the AWS Management Console, search for **EC2** and open the dashboard.
2. Click **Launch instance** and select an instance type from the dropdown.
3. Provide a descriptive name for the instance.
4. Under **Amazon Machine Image (AMI)**, choose **Quick Start** and select your preferred OS (e.g., Amazon Linux).
5. Select an eligible image if using the Free Tier. An AMI is a pre-configured template containing the OS and app environment for your instance.
6. In the **Instance type** section, choose the desired configuration (CPU, memory, storage, and network).
7. If unsure, click **Compare instance types**. A common Free Tier option is `t2.micro`.

8. Create a **new Key Pair** with a descriptive name.
9. Choose between:
   - **RSA** (widely supported)
   - **ED25519** (not supported for Windows instances)
10. Select the **Private key file format**:
   - `.pem` for OpenSSH
   - `.ppk` for PuTTY
11. Download the private key and store it securely.
12. Use the default **VPC (Virtual Private Cloud)**, which defines your isolated network in AWS.
13. An **internet gateway** is already attached to the default VPC, enabling internet access.
14. Subnet preference is usually left as "No preference"; AWS auto-assigns the availability zone.
15. Ensure **Auto-assign public IP** is set to **Enabled** so your instance is reachable online.
16. Create a **new Security Group** with a descriptive name and brief description.
17. Configure inbound rules:
    - **SSH (port 22)**: Allow access from your personal IP only.
    - **HTTP (port 80)**: Allow access from anywhere if hosting a public website.
18. Configure the **root volume** or add additional volumes based on your needs.
19. Use the summary panel to review all configurations.
20. Click **Launch instance** once everything looks correct.
21. A confirmation page will confirm the instance is launching.
22. Scroll down and click **View all instances**.
23. Check the **Instance State**, **Public IP**, and **Public DNS** to confirm it's running.


### Introduction to Amazon Virtual Private Cloud (Amazon VPC)
1. In the AWS Management Console, search for **VPC**.
2. A default VPC will already exist. It allows quick deployment of services but includes settings not typically used in production environments.
4. Set a descriptive **name tag prefix**.
5. For **IPv4 CIDR block**, choose a range (e.g., up to 65,536 IPs). Default is “No IPv4 CIDR block”.
6. **Tenancy** is set to **Default**, which shares underlying hardware. Choose **Dedicated** for isolated resources (additional cost).
7. **VPC Endpoints** are set to default (S3 Gateway).
8. Enable both:
   - **DNS resolution**
   - **DNS hostnames**
9. Review the **architecture diagram** generated on the right panel.
10. Click **Create VPC** to finish setup.
11. Click **View VPC** to inspect the details.
12. You can now use the custom VPC for launching services (e.g., EC2), instead of relying on the default VPC.

### Introduction to Amazon Relational Database Service (Amazon RDS)
1. In the AWS Management Console, search for **RDS** and click **Create database**.
2. Choose a creation method:
   - **Standard Create**: Full control over settings (availability, security, backups, maintenance).
   - **Easy Create**: Uses recommended defaults. Limited settings can be changed post-creation.
3. Select a **database engine** (e.g., MySQL, PostgreSQL, Oracle).
4. Choose an **instance size**:
   - For Free Tier: `db.t3.micro` (2 vCPUs, 1 GiB RAM, 20 GiB storage).
5. Provide a **DB instance identifier** (descriptive name).
6. Leave the **master username** as `admin`.  
   - Set a **custom password** or allow AWS to auto-generate one.
7. After creating the db, the endpoint can now be integrated with applications where communication can be established.

### Introduction to AWS Identity and Access Management (IAM)
AWS IAM allows you to create identities (users, groups, and roles) and attach **policies** to define what services and resources they can access.
> It’s recommended to create a separate **Admin account** for managing IAM tasks.

1. In the AWS Console, search for **IAM**.
2. In the left navigation pane, click **Users**.
3. Click **Add users**.
4. Enter a **username**.
5. Enable **AWS Management Console access**.
6. Choose a **custom or auto-generated password**.
7. (Recommended) Select **"User must create a new password at next sign-in"**.
8. Click **Return to users list** to view the newly created user.

#### Creating a User Group with S3 Access

1. In the navigation pane, select **User groups** > **Create group**.
2. Enter a **group name**.
3. Under **Attach permissions policies**, choose appropriate policies (indicated with an orange cube for AWS-managed policies).
4. You may optionally create a **custom policy**.
5. To view or understand what a policy does, click the policy name to see details.


The `AmazonS3FullAccess` policy grants full access to all S3 actions and resources:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:*",
        "s3-object-lambda:*"
      ],
      "Resource": "*"
    }
  ]
}
```
- `s3:*` allows all S3 actions (e.g., create buckets, upload/download files, list contents).
- `Resource: "*"` grants access to all S3 buckets and objects.

6. Add the created user(s) to the newly defined user group.
7. Click Create User Group to complete setup.
   - To verify:
      1. Go to the User's **Security Credentials** tab.
      2. Copy the Console sign-in link.
      3. Open it in a new browser tab.
      4. Log in using the created user's credentials.
      5. Navigate to the service (e.g., S3) and ensure access works without error.

### Introduction to AWS Lambda
1. In the AWS Console, search for **Lambda** and click **Create function**.
2. Choose one of the following creation methods:
   - **Author from scratch**
   - **Use a blueprint** (prebuilt templates for common use cases)
   - **Container image** (deploy from a container registry)

3. Enter a **descriptive function name**.
4. For **Execution role**, allow Lambda to create a new IAM role with default permissions.
5. Review the default **Function code**.
6. Tick the **acknowledgment box** and click **Create function**.
> - After creation, click on the **Function URL** to launch the sample app in a new tab.
> - You can set up a **trigger** (e.g., HTTP request or AWS service) to invoke the function.
> - After adding a trigger, check its status in the **Configuration** tab.

### Introduction to Amazon CloudWatch
#### Creating a Billing Alarm
1. In the CloudWatch console, go to **Billing** in the left navigation pane.
2. Click **Create alarm**.
3. View the **current estimated cost** under Metrics.
- **Conditions**: Set the threshold value for triggering the alarm.
- **Notifications**:  
  - Choose an SNS topic:
    - Select an existing topic
    - Create a new one
    - Use a topic ARN to notify external accounts  
  - Provide a **unique topic name** and **recipient email address**.
4. Choose an **action** (optional):
   - Auto Scaling
   - EC2 Action
   - Systems Manager
   - Ticketing

5. Click **Next**, name your alarm, and review the settings.
6. Click **Create alarm**.

> Note: If the alarm shows **"Insufficient data"**, give it time to collect metrics.

#### Creating an Alarm for EC2 Metrics

1. In CloudWatch, go to **All Alarms** and click **Select metric**.
2. Select **EC2 > Per-Instance Metrics**.
3. Choose a metric such as **CPUUtilization**.
4. Adjust the **time period** and threshold type:
   - **Static**: Fixed threshold value
   - **Anomaly detection**: Dynamic threshold band

5. Ensure the threshold unit matches the metric graph.
6. Define the **Alarm trigger state**, SNS topic, and email.
7. Click **Next**, provide an alarm name, review the summary, and click **Create alarm**.

> When the threshold is breached, the alarm enters the **In alarm** state and sends a notification to the specified email.

## Quiz Questions
1. WHich type of EC2 instance would you use if you needed a computing resource that would be in use for at least one full year?
   - [x] Reserved Instance  
   - [ ] Lambda Instance
   - [ ] Spot Instance
   - [ ] On-demand
> **Reserved instances** are 70% cheaper than using On-Demand instances. To get a Reserved Instance, you need to commit to using the instance for 1 or 3 years.
> 
> On-Demand instances are ideally used for computing needs that are less than a year.
> 
> Spot instances are used for computing needs that need to run for low costs and can be interrupted.
> 
> Lamda instances do not exist. You can use AWS Lambda to process snippets of code, when a Lambda function is triggered.

2. You want to store data in an object storage service. WHich service is suitable?
   - [x] Amazon Simple Storage Service
   - [ ] Amazon Managed Blockchain
   - [ ] Amazon Elastic File System
   - [ ] Amazon Elastic Block Store
> Amazon Managed Blockchain is a service you can use to create and manage blockchain netowrks with open-source frameworks. Blockchain is a distributed ledger system that lets multiple parties run transactions and share data without a central authority.
> 
> Amazon ELastic File System is a scalable file system used with AWS Cloud services and on-premises resources.
> 
> Amazon Elastic Block Store is a service that provides block-level storage volumes that you can use with Amazon EC2 instances.

3. Which describes Amazon DynamoDB?
   - [x] A severless key-value database service
   - [ ] A service for running relational databases in AWS Cloud
   - [ ] A service to migrate databases
   - [ ] An enterprise-class relational database

> Amazon DynamoDB is serverless, meaning you do not have to provision, patch or manage servers.
>
> **Amazon Relational Database Service**: A service for running relational databases in AWS Cloud.
>
> **AWS Database Migration Service**: A service to migrate relational databases, nonrelational databases and other types of data stores.
>
> **Amazon Aurora**: An enterprise-class relational database.

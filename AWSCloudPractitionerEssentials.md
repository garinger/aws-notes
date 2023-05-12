# Table of contents

- [Module 1 - Introduction to Amazon Web Services](#module1)
- [Module 2 - Compute in the cloud](#module2)
- [Module 3 - Global infrastructure and reliability](#module3)
- [Module 4 - Networking](#module4)
- [Module 5 - Storage and databases](#module5)
- [Module 6 - Security](#module6)
- [Module 7 - Monitoring and analytics](#module7)
- [Module 8 - Pricing and support](#module8)
- [Module 9 - Migration and innovation](#module9)
- [Module 10 - The cloud journey](#module10)

<a name="module1"></a>

# Module 1 - Introduction to Amazon Web Services

### Three types of Deployment models for cloud computing

1. **Cloud-based Deployment**
   - Run everything on cloud
   - Move existing apps to cloud
   - Create new apps on cloud
2. **On-Premises Deployment**
   - Use virtualization and resource management tools on existing on-premises hardware
   - Typically legacy
3. **Hybrid Deployment**
   - Use cloud-based resources for on-premises hardware
   - Useful for legacy systems that need to be on-prem

### Benefits of cloud computing

- Pay as you go instead of huge upfront cost
- Don't have to guess capacity
- Don't have to maintain data centers
- Easier and faster scaling
- Easy global presense

### Module 1 Quiz

- What is cloud computing?
  - On-demand delivery of IT resources and applications through the internet with pay-as-you-go pricing
- What is another name for on-premises deployment?
  - Private cloud deployment
- How does the scale of cloud computing help you to save costs?
  - The aggregated cloud usage from a large number of customers results in lower pay-as-you-go prices.

<a name="module2"></a>

# Module 2 - Compute in the cloud

**Amazon Elastic Compute Cloud (Amazon EC2)**

### EC2 Instance Families

- **General Purpose**
  - Balanced resources
  - Good for webservers
- **Compute Optimized**
  - Good for compute intensive tasks
  - Gaming servers, High Performance Computing (HPC), Scientific modeling, etc.
- **Memory Optimized**
  - For memory intensive tasks
- **Accelerated Computing**
  - Utilize hardware accelerators
  - Good for floating point calculations, graphics processing, data pattern matching, etc.
- **Storage Optimized**
  - High performance for locally stored data

### EC2 Pricing

- **On-Demand**
- **Savings Plans**
  - Lower prices if you can commit to a 1 or 3 year term.
  - Savings up to 72%
- **Reserved Instances**
  - Suited for steady state workloads / predictable usage.
  - Savings up to 75%
  - 1 to 3 year term
  - Payment options include all up front, some up front, and no up front.
- **Spot instances**
  - Lets you use spare instances that AWS isn't using.
  - AWS can stop your instance at any time with a 2 minute warning.
  - Savings up to 90%.
- **Dedicated Hosts**
  - You get your own host
  - No Multitenancy

**Multitenancy** - Sharing underlying hardware between virtual machines.
**Vertical Scaling** - Giving an EC2 instance more or less CPU and RAM.

### EC2 Scaling

**Amazon EC2 Auto Scaling (Horizontal Scaling)**

- Automatically add or remove Amazon EC2 instances in response to changing application demand.
- Two approches (can use both together!):
  1.  **Dynamic** - Responds to changing demand.
  2.  **Predictive** - Schedules the right number of EC2 instances based on predicted demand.
- You can set the number of minimum instances, desired instances, and maximum instances.

**Elastic Load Balancing (ELB)** - Automatically distributes incoming application traffic across multiple resources, such as Amazon EC2 instances.

### Messaging and queuing

- **Amazon Simple Queue Service (Amazon SQS)**
  - Send, store, and receive messages between software components.
- **Amazon Simple Notification Service (Amazon SNS)**
  - Can also send, store, and receive messages.
  - Publish/Subscribe model.
  - Create topics that will send notifications to the subscribers.
  - Subscribers can be end points like AWS Lambda functions, HTTP hooks, etc.
  - Can send notifications to end users via push, SMS, email, etc.

### Serverless

**Serverless** - Cannot see or access the underlying infrastructure.

- **AWS Lambda**
  - A service that lets you run code without needing to provision or manage servers.
  - Charges apply only when your code is running.
- **Containers** - Containers provide you with a standard way to package your
  application's code and dependencies into a single object.
  - **Amazon Elastic Container Service (Amazon ECS)**
    - A highly scalable, high-performance container management system that enables
      you to run and scale containerized applications on AWS.
    - Uses Docker
  - **Amazon Elastic Kubernetes Service (Amazon EKS)**
    - A fully managed service that you can use to run Kubernetes on AWS.
    - Kubernetes is open-source software that enables you to deploy
      and manage containerized applications at scale.
  - **AWS Fargate**
    - A serverless compute engine for containers. It works with both Amazon ECS and Amazon EKS.
    - Don't need to provision or manage servers.

### Module 2 Quiz

- You want to use an Amazon EC2 instance for a batch processing workload. What would be the best Amazon EC2 instance type to use?
  - Compute optimized
- What are the contract length options for Amazon EC2 Reserved Instances?
  - 1 year or 3 years
- You have a workload that will run for a total of 6 months and can withstand interruptions. What would be the most cost-efficient Amazon EC2 purchasing option?
  - Spot Instance
- Which process is an example of Elastic Load Balancing?
  - Ensuring that no single Amazon EC2 instance has to carry the full workload on its own.
- You want to deploy and manage containerized applications. Which service should you use?
  - Amazon Elastic Kubernetes Service (Amazon EKS)

<a name="module3"></a>

# Module 3 - Global infrastructure and reliability

- Reasons for selecting a region
  - Compliance with data governance and legal requirements.
  - Proximity to customers
  - Available features
  - Pricing

Each region is comprised of multiple availability zones
**Availability Zone** - One or a group of data centers

- **Amazon Cloudfront**
  - Amazon's CDN
  - Uses edge locations to accelerate communication and content delivery with users
- **Edge locations**
  - A site that Amazon CloudFront uses to store cached copies of your content
    closer to your customers for faster delivery.
- **AWS Route 53 (DNS)**

  - Amazon's Domain Name Service

- **AWS Outposts**
  - Pretty much a mini region thats inside your own building.
- Ways to interact with AWS services:
  - **AWS Management console (website)**
  - **AWS Command Line Interface (CLI)**
  - **Software Development Kits (SDKs)**
- **AWS Elastic Beanstalk**

  - You provide code and configuration settings, and Elastic Beanstalk deploys theresources necessary to perform the following tasks
    - Adjust Capacity
    - Load balancing
    - Automatic scaling
    - Application health monitoring

- **AWS CloudFormation**
  - You can build an environment by writing lines of code instead of using the AWS Management Console to individually provision resources.

### Module 3 Quiz

- Which statement is TRUE for the AWS global infrastructure?
  - A Region consists of two or more Availability Zones.
- Which factors should be considered when selecting a Region?
  - Compliance with data governance and legal requirements
  - Proximity to your customers
- Which statement best describes Amazon CloudFront?
  - A global content delivery service
- Which site does Amazon CloudFront use to cache copies of content for
  faster delivery to users at any location?
  - Edge location
- Which action can you perform with AWS Outposts?
  - Extend AWS infrastructure and services to your on-premises data center.

<a name="module4"></a>

# Module 4 - Networking

**Amazon Virtual Private Cloud (VPC)** - Your own private network within AWS.

**Internet Gateway** - An internet gateway is a connection between a VPC and the internet.

**Virtual Private Network** - A virtual private gateway enables you to establish a virtual private network (VPN) connection between your VPC and a private network, such as an on-premises data center or internal corporate network. A virtual private gateway allows traffic into the VPC only if it is coming from an approved network.

**AWS Direct Connect** - A service that enables you to establish a dedicated private connection between your data center and a VPC (a physical fiber line).

**Subnets** - A section of a VPC in which you can group resources based on security or operational needs. Subnets can be **public** or **private**.

**Network access control lists (ACLs)** - A network access control list (ACL) is a virtual firewall that controls inbound and outbound traffic at the subnet level. ACLs check permissions both for entering and exiting packets. By default allow all traffic. ACLs are **stateless**.

**Security Groups** - A security group is a virtual firewall that controls inbound and outbound traffic for an Amazon EC2 instance. Security groups check permissions only for entering packets. By default deny all traffic. Security groups are **stateful**.

### Module 4 Quiz

- Your company has an application that uses Amazon EC2 instances to run the customer-facing website and Amazon RDS database instances to store customers’ personal information. How should the developer configure the VPC according to best practices?
  - Place the Amazon EC2 instances in a public subnet and the Amazon RDS database instances in a private subnet.
- Which component can be used to establish a private dedicated connection between your company’s data center and AWS?
  - AWS Direct Connect
- Which statement best describes security groups?
  - They are stateful and deny all inbound traffic by default.
- Which component is used to connect a VPC to the internet?
  - Internet gateway
- Which service is used to manage the DNS records for domain names?
  - Amazon Route 53

<a name="module5"></a>

# Module 5 - Storage and databases

**Block-level Storage** - Pretty much just hard drives.

**Instace Stores** - Temporary block-level storage for an EC2 instance. It is phyiscally attached to the host of your EC2 so data can be lost between startups the EC2 instance.

**Elastic Block Store (Amazon EBS)** - A service that provides block-level storage volumes that you can use with Amazon EC2 instances. EBSs aren't attached to EC2 hosts so data is presistant between stoping/starting EC2 instances. You can take backups of EBS by creating **EBS snapshots**.

- Sizes up to 16 TiB
- Solid state by default
- HDD options

**Amazon EBS snapshots** - An incremental backup of EBS data. For the first backup, all data is copied. For subsequent backups, only data that has changed is backed up.

**Object Storage** - Each object consists of data, metadata, and a key. Unlike block storage, the entire object is updated when it is modified.

**Amazon Simple Storage Service (Amazon S3)** - A service that provides object-level storage. Amazon S3 stores data as objects in buckets. You can set permissions to control visibility and access. Also includes a versioning feature to track changes to objects over time.

- Unlimited storage
- Individual objects up to 5 TB
- Write once/read many
- 99.999999999% durability

### Amazon S3 Storage Classes

- **Amazon S3 Standard**
  - Designed for frequently accessed data
  - Stores data in a minimum of three Availability Zones
  - General purpose
- **Amazon S3 Standard-Infrequent Access (S3 Standard-IA)**
  - Ideal for infrequently accessed data
  - Lower storage price but higher retrieval price
- **Amazon S3 One Zone-Infrequent Access (S3 One Zone-IA)**
  - Stores data in a single Availability Zone
  - Has a lower storage price than Amazon S3 Standard-IA
  - Pretty much just a cheaper version of S3 Standard-IA
- **Amazon S3 Intelligent-Tiering**
  - Ideal for data with unknown or changing access patterns
  - Requires a small monthly monitoring and automation fee per object
  - Data is stored in S3 Standard unless inactive for 30 consecutive days where it moves it to S3 Standard-IA
- **Amazon S3 Glacier Instant Retrieval**
  - Works well for **archived** data that requires immediate access
  - Can retrieve objects within a few milliseconds
- **Amazon S3 Glacier Flexible Retrieval**
  - Low-cost storage designed for data archiving
  - Able to retrieve objects within a few minutes to hours
- **Amazon S3 Glacier Deep Archive**
  - Lowest-cost object storage class ideal for archiving
  - Able to retrieve objects within 12 to 48 hours
  - Replication across at least three Availability Zones
- **Amazon S3 Outposts**
  - Creates S3 buckets on Amazon S3 Outposts
  - Makes it easier to retrieve, store, and access data on AWS Outposts
  - Designed to store data durably and redundantly across multiple devices and servers on your Outposts

**Amazon Elastic File System (Amazon EFS)** - A scalable file system used with AWS Cloud services and on-premises resources. As you add and remove files, Amazon EFS grows and shrinks automatically. It can scale on demand to petabytes without disrupting applications.

- Region level

### EBS vs EFS

- EBS is scoped to Availability Zones while EFS is scoped to Regions
- EFS automatically scales while EBS doesn't

**Amazon Relational Database Serivce (Amazon RDS)** - A service that enables you to run relational databases in the AWS Cloud. Amazon RDS automates the following tasks,

- Hardware provisioning
- Database setup
- Patching
- Backups

**Amazon RDS supported database engines**

- Amazon Aurora
- PostgreSQL
- MySQL
- MariaDB
- Oracle Database
- Microsoft SQL Server

**Amazon Aurora** - An enterprise-class relational database. It is compatible with MySQL and PostgreSQL relational databases. It is up to five times faster than standard MySQL databases and up to three times faster than standard PostgreSQL databases. Consider Amazon Aurora if your workloads require high availability. It replicates six copies of your data across three Availability Zones and continuously backs up your data to Amazon S3.

**Amazon DynamoDB** - A key-value database service. It delivers single-digit millisecond performance at any scale. **Pretty much Amazon's version of MongoDB**. Amazon DynamoDB has the following characteristics,

- Serverless
- Automatic scaling

**Amazon Redshift** - A data warehousing service that you can use for big data analytics. It offers the ability to collect data from many sources and helps you to understand relationships and trends across your data.

**AWS Database Migration Service (AWS DMS)** - Enables you to migrate relational databases, nonrelational databases, and other types of data stores. The source database and target database can be of the same type (MySQL to RDS MySQL) or a different type (PostgreSQL to DynamoDB). Other uses of AWS DMS include,

- Development and test database migrations
- Database consolidation
- Continuous replication

### Additional Database Services

**Amazon DocumentDB** - A document database service that supports MongoDB workloads.
**Amazon Neptune** - A graph database service. Good for things like social networks.
**Amazon Quantum Ledger Database (Amazon QLDB)** - A ledger database service.
**Amazon Managed Blockchain** - A service that you can use to create and manage blockchain networks with open-source frameworks.
**Amazon ElastiCache** - A service that adds caching layers on top of your databases to help improve the read times of common requests.
**Amazon DynamoDB Accelerator** - An in-memory cache for DynamoDB. It helps improve response times from single-digit milliseconds to microseconds.

### Module 5 Quiz

- Which Amazon S3 storage classes are optimized for archival data?
  - Amazon S3 Glacier Flexible Retrieval
  - Amazon S3 Glacier Deep Archive
- Which statement or statements are TRUE about Amazon EBS volumes and Amazon EFS file systems?
  -EBS volumes store data within a single Availability Zone. Amazon EFS file systems store data across multiple Availability Zones.
- You want to store data in an object storage service. Which AWS service is best for this type of storage?
  - Amazon Simple Storage Service (Amazon S3)
- Which statement best describes Amazon DynamoDB?
  - A serverless key-value database service
- Which service is used to query and analyze data across a data warehouse?
  - Amazon Redshift

<a name="module6"></a>

# Module 6 - Security

**Shared Responsibility Model** - The shared responsibility model divides into customer responsibilities (commonly referred to as “security in the cloud”) and AWS responsibilities (commonly referred to as “security of the cloud”).

![SharedResponsibilityModel](https://d1.awsstatic.com/security-center/Shared_Responsibility_Model_V2.59d1eccec334b366627e9295b304202faf7b899b.jpg)

**AWS Identity and Access Management (IAM)** - Enables you to manage access to AWS services and resources securely.

**AWS account root user** - This user has access to do **anything**. Ideally, you wouldn't use the root user for everyday tasks and should instead create other users.

**IAM Users** - An identity that you create in AWS. By default, users have no permissions to do anything.

**IAM Policies** - A document that allows or denies permissions to AWS services and resources.

**IAM Groups** - An IAM group is a collection of IAM users. You can apply IAM policies to IAM roups.

**IAM Roles** - An identity that you can assume to gain **temporary** access to permissions.

**AWS Organizations** - You can use AWS Organizations to consolidate and manage multiple AWS accounts within a central location. You can centrally control permissions for the accounts in your organization by using **service control policies (SCPs)**. SCPs enable you to place restrictions on the AWS services, resources, and individual API actions that users and roles in each account can access.

**Organizational Units (OUs)** - You can group accounts into organizational units to make it easier to manage accounts with similar business or security requirements.

**AWS Artifact** - A service that provides on-demand access to AWS security and compliance reports and select online agreements. AWS Artifact consists of these two main sections,

- **AWS Artifact Agreements**
  - You can review, accept, and manage agreements for an individual account and for all your accounts in AWS Organizations. Different types of agreements are offered to address the needs of customers who are subject to specific regulations, such as the Health Insurance Portability and Accountability Act (HIPAA).
- **AWS Artifact Reports**
  - AWS Artifact Reports provide compliance reports from third-party auditors. These auditors have tested and verified that AWS is compliant with a variety of global, regional, and industry-specific security standards and regulations.

**Customer Compliance Center** - Contains resources to help you learn more about AWS compliance.

**AWS Shield** - A service that protects applications against DDoS attacks. AWS Shield provides two levels of protection: Standard and Advanced.

- **AWS Shield Standard**
  - AWS Shield Standard automatically protects all AWS customers at no cost. It protects your AWS resources from the most common, frequently occurring types of DDoS attacks.
- **AWS Shield Advanced**
  - AWS Shield Advanced is a paid service that provides detailed attack diagnostics and the ability to detect and mitigate sophisticated DDoS attacks.

**AWS KeyManagement Service (AWS KMS)** - Enables you to perform encryption operations through the use of cryptographic keys. You can use AWS KMS to create, manage, and use cryptographic keys. You can also control the use of keys across a wide range of services and in your applications.

**AWS WAF** - A web application firewall that lets you monitor network requests that come into your web applications.

**Amazon Inspector** - Amazon Inspector helps to improve the security and compliance of applications by running automated security assessments. It checks applications for security vulnerabilities and deviations from security best practices, such as open access to Amazon EC2 instances and installations of vulnerable software versions.

**Amazon GuardDuty** - A service that provides intelligent threat detection for your AWS infrastructure and resources. It identifies threats by continuously monitoring the network activity and account behavior within your AWS environment.

### Module 6 Quiz

- Which statement best describes an IAM policy?
  - A document that grants or denies permissions to AWS services and resources
- An employee requires temporary access to create several Amazon S3 buckets. Which option would be the best choice for this task?
  - IAM role
- Which statement best describes the principle of least privilege?
  - Granting only the permissions that are needed to perform specific tasks
- Which service helps protect your applications against distributed denial-of-service (DDoS) attacks?
  - AWS Shield
- Which task can AWS Key Management Service (AWS KMS) perform?
  - Create cryptographic keys.

<a name="module7"></a>

# Module 7 - Monitoring and analytics

**Amazon CloudWatch** - A web service that enables you to monitor and manage various metrics and configure alarm actions based on data from those metrics. CloudWatch uses **metrics** to represent the data points for your resources.

**CloudWatch Alarms** - With CloudWatch, you can create alarms that automatically perform actions if the value of your metric has gone above or below a predefined threshold.

**CloudWatch Dashboard** - Enables you to access all the metrics for your resources from a single location.

**AWS CloudTrail** - AWS CloudTrail records API calls for your account. The recorded information includes the identity of the API caller, the time of the API call, the source IP address of the API caller, and more.

**CloudTrail Insights** - This optional feature allows CloudTrail to automatically detect unusual API activities in your AWS account.

**AWS Trusted Advisor** - A web service that inspects your AWS environment and provides real-time recommendations in accordance with AWS best practices. Trusted Advisor compares its findings to AWS best practices in these five categories,

- **Cost**
- **Optimization**
- **Performance**
- **Security**
- **Fault tolerance**
- **Service limits**

### Module 7 Quiz

- Which actions can you perform using Amazon CloudWatch?
  - Monitor your resources’ utilization and performance
  - Access metrics from a single dashboard
- Which service enables you to review the security of your Amazon S3 buckets by checking for open access permissions?
  - AWS Trusted Advisor
- Which categories are included in the AWS Trusted Advisor dashboard?
  - Performance
  - Fault tolerance

<a name="module8"></a>

# Module 8 - Pricing and support

**AWS Free Tier** - Enables you to begin using certain services without having to worry about incurring costs for the specified period. Three types of the free tier,

- **Always free**
- **12 months free**
- **Trials**

**AWS Pricing Calculator** - Lets you explore AWS services and create an estimate for the cost of your use cases on AWS.

**AWS Billing and Cost Management Dashboard** - Pay your AWS bill, monitor your usage, and analyze and control your costs.

**Consolidated Billing** - The consolidated billing feature of AWS Organizations enables you to receive a single bill for all AWS accounts in your organization. Another benefit of consolidated billing is the ability to share bulk discount pricing, Savings Plans, and Reserved Instances across the accounts in your organization.

**AWS Budgets** - You can create budgets to plan your service usage, service costs, and instance reservations. You can also set custom alerts when your usage exceeds (or is forecasted to exceed) the budgeted amount.

**AWS Cost Explorer** - A tool that enables you to visualize, understand, and manage your AWS costs and usage over time.

**AWS Support** - AWS offers four different Support plans to help you troubleshoot issues, lower costs, and efficiently use AWS services (not including free tier).

- **Developer support**
- **Business support**
- **Enterprise on-ramp support**
  - Includes a **Technical Account Manager (TAM)**
- **Enterprise support**
  - Includes a **Technical Account Manager (TAM)**

**AWS Marketplace** - A digital catalog that includes thousands of software listings from independent software vendors. You can use AWS Marketplace to find, test, and buy software that runs on AWS.

### Module 8 Quiz

- Which action can you perform with consolidated billing?
  - Combine usage across accounts to receive volume pricing discounts.
- Which pricing tool is used to visualize, understand, and manage your AWS costs and usage over time?
  - AWS Cost Explorer
- Which pricing tool enables you to receive alerts when your service usage exceeds a threshold that you have defined?
  - AWS Budgets
- Your company wants to receive support from an AWS Technical Account Manager (TAM). Which support plan should you choose?
  - Enterprise On-Ramp or Enterprise
- Which service or resource is used to find third-party software that runs on AWS?
  - AWS Marketplace

<a name="module9"></a>

# Module 9 - Migration and innovation

**AWS Cloud Adoption Framework (AWS CAF)** - Organizes guidance into six areas of focus, called Perspectives. Each Perspective addresses distinct responsibilities. The planning process helps the right people across the organization prepare for the changes ahead. The six areas of focus are,

- **Business perspective**
- **People perspective**
- **Governance perspective**
- **Platform perspective**
- **Security perspective**
- **Operations perspective**

### 6 strategies for migration

- **Rehosting**
  - "Lift-and-shift"
- **Replatforming**
  - "Lift, tinker, and shift"
- **Refactoring/re-architecting**
  - Recreate app using cloud features
- **Repurchasing**
  - Move from traditional license to SaaS
- **Retaining**
  - Keep lights on until eventually retiring
- **Retiring**
  - Remove apps that aren't needed anymore

**AWS Snow Family** - A series of products that are designed to help you migrate your data to AWS. Ideal if you have very large amounts of data (petabytes) that would take weeks or months to migrate. The members of the snow family are,

- **AWS Snowcone**
  - A small, rugged, and secure edge computing and data transfer device.
  - 2 CPUs, 4GB memory, and 8TB storage.
  - AWS ships it you, you upload your data, then you send it back. They'll add it to your AWS account (probably S3 bucket).
- **AWS Snowball**
  - **Snowball Edge Storage Optimized** - Devices are well suited for large-scale data migrations and recurring transfer workflows, in addition to local computing with higher capacity needs.
    - Storage: 80TB HDD, 1TB SSD
    - Compute: 40 vCPUs and 80GiB memory
  - **Snowball Edge Compute Optimized** - Provides powerful computing resources for use cases such as machine learning, full motion video analysis, analytics, and local computing stacks.
    - Storage: 42TB HDD and 7.68TB NVMe SSD
    - Compute: 52 vCPUs and 208GiB memory
- **AWS Snowmobile** - An exabyte-scale data transfer service used to move large amounts of data to AWS. You can transfer up to 100 petabytes of data per Snowmobile, a 45-foot long ruggedized shipping container, pulled by a semi trailer truck.

**Amazon SageMaker** - Enables you to quickly build, train, and deploy machine learning models?

### Module 9 Quiz

- Which Perspective of the AWS Cloud Adoption Framework helps you structure the selection and implementation of permissions?
  - Security Perspective
- Which strategies are included in the six strategies for application migration?
  - Retaining
  - Rehosting
- What is the storage capacity of AWS Snowmobile?
  - 100 PB
- Which statement best describes Amazon Lex?
  - A service that enables you to build conversational interfaces using voice and text

<a name="module10"></a>

# Module 10 - The cloud journey

**AWS Well-Architected Framework** - Helps you understand how to design and operate reliable, secure, efficient, and cost-effective systems in the AWS Cloud. It provides a way for you to consistently measure your architecture against best practices and design principles and identify areas for improvement. The six pillars are,

- **Operational excellence**
  - The ability to run and monitor systems to deliver business value and to continually improve supporting processes and procedures.
- **Security**
  - The ability to protect information, systems, and assets while delivering business value through risk assessments and mitigation strategies.
- **Reliability**
  - Includes testing recovery procedures, scaling horizontally to increase aggregate system availability, and automatically recovering from failure.
- **Performance efficiency**
  - The ability to use computing resources efficiently to meet system requirements and to maintain that efficiency as demand changes and technologies evolve.
- **Cost optimization**
  - The ability to run systems to deliver business value at the lowest price point.
- **Sustainability**
  - The ability to continually improve sustainability impacts by reducing energy consumption and increasing efficiency across all components of a workload by maximizing the benefits from the provisioned resources and minimizing the total resources required.

### Advantages of cloud computing

- **Trade upfront expense for variable expense.**
- **Benefit from massive economies of scale.**
- **Stop guessing capacity.**
- **Increase speed and agility.**
- **Stop spending money running and maintaining data centers.**
- **Go global in minutes.**

### Module 10 Quiz

- Which pillar of the AWS Well-Architected Framework includes the ability to run workloads effectively and gain insights into their operations?
  - Operational Excellence
- What are the benefits of cloud computing?
  - Increase speed and agility.
  - Stop spending money running and maintaining data centers.

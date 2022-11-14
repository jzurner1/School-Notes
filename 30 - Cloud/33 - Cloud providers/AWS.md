Amazon Web Services (AWS) is a secure cloud platform that offers a broad set of global cloud-based products. It provides you with on-demand access to computing, storage, network, database, and other IT resource and management tools.

It offers flexibility and you only pay for the services you need. Those services work together like building blocks.

![[Pasted image 20221023101526.png]]

# Interaction
There are three ways to interact with AWS. All three of the options are built on a common REST-like API that serves as the foundation of AWS.

### AWS management console
The console provides a rich GUI to a majority of the features offered by AWS. When new features are released, they may not initially be accessible through this.

### AWS command line interface (AWS CLI)
This provides a suite of utilities that can be launched from a command script in Linux, macOS, or Windows.

### Software development kits (SDKs)
AWS provides packages that enable accessing AWS in a variety of popular programming languages. This makes it easy to use AWS in your existing applications and it enables you to create applications that deploy and monitor complex systems built entirely through code.

# Global infrastructure
### AWS Regions
An **AWS region** is a geographical area with one or more **availability zones**, which consists of one or more **data centers**. AWS regions are isolated from one another, so data stored in one region is not replicated and stored in another.

![[Pasted image 20221031092649.png]]

When selecting a region, there are a few factors to consider. They include the local data governance and legal requirements, proximity to customers, services available within the region, and costs.

### Availability zones
Availability zones exist within regions, and there are usually two or more. Each zone is a fully isolated partition of the AWS infrastructure. There are 69 available worldwide, and they consist of data centers. Availability zones are interconnected with high-speed private networking. It is recommended to replicate data and resources across availability zones for resiliency.

### Data centers
AWS data centers are designed for security, and customers do not get to choose their own data centers. This is where the data itself resides and where the data processing occurs. Each data center has redundant power, networking, and connectivity, and is housed in a separate facility. Each data center typically has 50,000 to 80,000 physical servers. Data center locations are not disclosed.

### Points of presence
AWS provides a global network of 187 points of presence locations. This consists of 176 **edge locations** and 11 **regional edge caches**, all used to lower latency. This is all used with Amazon CloudFront, again to reduce latency. Regional edge caches are used for content with infrequent access.

### AWS infrastructure features
- **Elasticity and scalability**: Elastic infrastructure, dynamic adaption of capacity. Scalable infrastructure, adapts to accommodate growth.
- **Fault tolerance**: Continues operating properly in the presence of a failure; built-in redundancy of components.
- **High availability**: High level of operational performance, minimized downtime, and no human intervention.

# Services and service categories
While there are more services than those listed below, the ones below are some of the most commonly used.

### Storage service
The AWS storage service category is represented by the **Amazon Simple Storage Service**, also known as **Amazon S3**, which is an object storage service that offers scalability, data availability, security, and performance.

**Amazon Elastic Block Store** (**Amazon EBS**) is another form of storage. It is a high-performance block storage designed for use with Amazon EC2 for through-put and transaction-intensive workloads.

**Amazon Elastic File System** (**Amazon EFS**) is another storage service that provides a scalable, fully-managed elastic network file system (NFS) for use within AWS cloud services and on-premise resources.

Lastly is **Amazon Simple Storage Service Glacier**, which is a secure, durable, and extremely low-cost AWS S3 cloud storage class, usually used for data archiving and long-term backups.

### Compute services
**Amazon Elastic Compute Cloud**, also known as **Amazon EC2**, provides resizeable compute capacity as virtual machines in the cloud. The Amazon EC2 Auto Scaling service enables you to automatically add or remove EC2 instances according to conditions that you define.

**Amazon Elastic Container Service** (**Amazon ECS**) is a highly scalable and high-performance container orchestration service that supports Docker containers. Amazon EC2 Container Registry (Amazon ECR) is a fully-manager Docker container registry that makes it easy for developers to store, manage and deploy docker containers.

**AWS Elastic Beanstalk** is a service for deploying and scaling web applications and services on familiar servers such as Apache.

**AWS Lambda** enables you to run code without provisioning or managing servers. You only pay for the compute time that you consume.

**Amazon Elastic Kubernetes Service** (**Amazon EKS**) makes it easy to deploy, manage, and scale containerized applications that use Kubernetes on AWS.

Lastly, **AWS Fargate** is a compute engine for Amazon ECS that allows you to run containers without having to manage servers or clusters.

### Database services
**Amazon Relational Database Service**, also known as **Amazon RDS**, is an easy to set up, easy to operate, and scalable relational database in the cloud. It provides resizeable capacity while automating time-consuming administration tactics such as hardware provisioning and database setup and backups.

**Amazon Aurora** is a mySQL- and PostgreSQL-compatible relational database. It is set up to be five times faster than standard mySQL databases and three times faster than standard PostgreSQL databases.

**Amazon Redshift** enables you to run analytic queries against large amounts of data that is locally stored in Amazon. It delivers fast performance at any scale.

**Amazon DynamoDB** is a fully managed key-value and document no-SQL database that delivers fast performance at any scale with built-in security, backups, and restore as well as memory caching.

### Networking and content delivery services
**Amazon Virtual Private Cloud**, also known as **Amazon VPC**, enables you to provision logically-isolated sections of the AWS cloud to launch AWS resources in a virtual network that you define.

**Elastic Load Balancing** automatically distributes incoming application traffic across multiple targets such as Amazon EC2 instances, containers, IP addresses, and Lambda functions.

**Amazon CloudFront** is a fast content delivery network (CDN) that securely delivers data, videos, and applications and application programming interfaces (APIs) to customers globally with low latency and high transfer speeds.

The **AWS Transit Gateway** service enables customers to connect their Amazon VPCs and on-premises networks to a single, centrally managed gateway.

**Amazon Route 53** is a scalable cloud domain name system web service designed to give you a reliable way to route end users to applications. It translates URLs into their IP addresses.

**AWS Direct Connect** provides a way to create a dedicated private network connection from your data center or office to AWS, which can significantly decrease costs and increase bandwidth throughput.

**AWS VPN** provides a secure private tunnel for your network or device to the AWS global network.

### Security, identity, and compliance services
**AWS Identity and Access Management** (**IAM**) enables you to manage access to AWS services and resources securely.

**AWS organizations** allows you to restrict what services and actions are allowed in your accounts.

**Amazon Cognito** allows you to add user authentication and access control to your web and mobile apps.

**AWS Artifact** provides on-demand access to AWS security and compliance reports as well as some online agreements.

The **AWS Key Management Service** (**AWS KMS**) enables you to create and manage encryption keys. This can be used to control encryption across a wide range of AWS services.

**AWS Shield** is a managed DDoS protection service that safeguards applications running on AWS.

### Cost management service
**AWS Cost and Usage Report** contains the most comprehensive cost and usage data available, including additional metadata about AWS services, pricing, and reservations.

**AWS Budgets** allows you to set custom budgets that alert you when your AWS costs exceeds, or is forecasted to exceed, your budgeted amount.

**AWS Cost Explorer** enables you to visualize and understand and manage your AWS costs and usage over time.

### Management and governance
**AWS Management Console** is a web-based user interface for accessing your AWS account.

**AWS Config** is a service that allows you to track service inventory and changes.

**Amazon CloudWatch** allows you to monitor resources and applications.

**AWS Auto Scaling** provides features that allow you to scale multiple resources to meet demand.

**AWS Command Line Interface** provides a unified tool to manage AWS services.

**AWS Trusted Advisor** is an online tool that helps you optimize performance and security using AWS best practices.

The **AWS Well-Architected Tool** provides help in reviewing and improving your workloads.

**AWS CloudTrail** tracks user activity and API usage across your AWS accounts.

# Pricing
There are three fundamental drivers of cost with AWS. The first is ccomputing, which varies by instance type. The next is storage, which is charged per GB. The last is data transfer, where outbound transfers are charged per GB. Inbound transfers are usually not charged.

AWS always charges for just what you use. You can start or stop a service at any time, making charges more customizable. You also pay less per unit if you use more units.

Some services are free, specifically Amazon VPC, Elastic Beanstalk, Auto Scaling, AWS CloudFormation, and AWS Identity and Access Management.

### TCO
The total cost of ownership, or TCO, is the financial estimate to help identify direct and indirect costs of a system. It is used to compare the costs of running an entire infrastructure environment or specific workload on-premises versus on AWS as well as to budget and build the business case for moving to the cloud.

![[Pasted image 20221031142832.png]]

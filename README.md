# Blue-Green-Deployment-using-CF

**Blue/Green Deployment on AWS with CloudFormation**
This repository contains the Infrastructure as Code (IaC) solution for setting up a Blue/Green (B/G) deployment for a mission-critical web application on AWS using AWS CloudFormation.

**Problem Statement**
The goal was to establish two separate environments: blue and green. The blue environment consists of Amazon EC2 instances running the current production version, while the green environment contains instances running the new version. Each environment is behind its own Application Load Balancer (ALB), allowing gradual traffic shifting from blue to green using Amazon Route 53.

**Solution Highlights**
Complete IaC Template: The CloudFormation template defines the infrastructure components required for the blue and green environments, including EC2 instances, Auto Scaling groups, ALBs, Route 53 records, and SSL certificate management.
**
****Blue/Green Environment Configuration:** **Separate Auto Scaling groups for blue and green environments ensure isolation and independent scaling. Path-based routing on the ALBs enables traffic segregation between the two environments.

**Auto-Scaling Template:** Auto Scaling policies are defined to automatically adjust the capacity of EC2 instances based on traffic demand, ensuring high availability and efficient resource utilization.

**Custom Domain Name:** Route 53 is utilized to assign a custom domain name to the ALB endpoints, allowing the application to be accessed securely over HTTPS.
**
**SSL Certificate Management:**** AWS Certificate Manager provisions SSL certificates for the custom domain, ensuring secure communication between clients and the ALBs.

**Routing Policy Rules:** Route 53 routing policies are configured to gradually shift traffic from the blue environment to the green environment based on predefined rules, facilitating seamless deployment updates.

**Backend Database Handling:** **In a Blue/Green deployment, the backend database endpoints remain unchanged. Both blue and green environments connect to the same database instance, ensuring data consistency across **deployments.

**Usage**
Clone the repository.
Upload the CloudFormation template to an S3 bucket.
Use the AWS Management Console or AWS CLI to create a CloudFormation stack, providing the S3 URL of the template and necessary parameters.
Monitor the stack creation process and check the outputs for ALB URLs and other relevant information.
Access the application using DNS

# aws-highly-available-scalable-webapp
This repository contains the project files for building a highly available, scalable web application on AWS. This project is part of the AWS Academy Lab Project, where I implemented real-world use cases using various AWS services to demonstrate best practices for scalability, availability, and cost optimization.

Project Overview
This project involves multiple phases:

Creating a basic functional web application on a single EC2 instance.
Decoupling the application by separating the web server and database.
Implementing high availability and scalability by leveraging Auto Scaling and Load Balancing.
As part of the AWS Academy Lab, this project adheres to the following goals:

Cloud-native architecture using AWS best practices.
Hands-on learning with AWS services like EC2, RDS, Auto Scaling, Load Balancer, VPC, and Secrets Manager.
Cost optimization within a budget of $100/month.


Phases of Implementation
Phase 1: Planning and Design
In this phase, I planned the architecture and estimated the cost of the AWS services required for the project. The core AWS services involved include:

Elastic Load Balancer (ELB): Distributes traffic across multiple EC2 instances.
Auto Scaling Group (ASG): Automatically adjusts the number of EC2 instances based on traffic.
Amazon EC2: Web servers for hosting the application.
Amazon RDS: Managed relational database to store student records.
Amazon VPC: Virtual network for secure hosting.
Security Groups and NACLs: To ensure secure access to resources.
Amazon S3 or EFS (Optional): For storing static assets or backups.
Phase 2: Creating a Basic Functional Web Application
Task 1: Creating a Virtual Network
I set up a Virtual Private Cloud (VPC) with subnets for hosting the web application.

Task 2: Creating a Virtual Machine
I launched an EC2 instance using the latest Ubuntu AMI to host the web application. I installed the necessary packages using the JavaScript code provided by aws from UserdataScript-phase-2(1).sh


Task 3: Testing the Deployment
I accessed the web application using the IPv4 address of the EC2 instance and tested CRUD operations such as viewing, adding, deleting, or modifying records.

Phase 3: Decoupling the Application Components
Task 1: Updating the VPC Configuration
I modified the VPC to include private subnets in at least two Availability Zones.

Task 2: Creating and Configuring Amazon RDS
I provisioned an Amazon RDS instance with MySQL and configured the database to be accessed only by the web application.

Task 3: Configuring the Development Environment
I provisioned an AWS Cloud9 environment and connected using SSH.

Task 4: Using AWS Secrets Manager
I created a secret for database credentials using AWS Secrets Manager. I used the provided script to configure Secrets Manager: cloud9-scripts.yml

Task 5: Provisioning a New Web Server Instance
I launched another EC2 instance for the web application and configured it to connect to Amazon RDS.

Task 6: Migrating the Database
I used a provided script to migrate data from the original EC2-hosted database to the Amazon RDS instance.

Task 7: Testing the Application
I tested the application again by performing CRUD operations.

Phase 4: Implementing High Availability and Scalability
Task 1: Creating an Application Load Balancer
I set up an Application Load Balancer to distribute incoming traffic across multiple instances.

Task 2: Implementing EC2 Auto Scaling
I configured EC2 Auto Scaling using a launch template and ensured that the Auto Scaling group adjusts the number of EC2 instances based on traffic.

Task 3: Accessing the Application
I accessed the web application using the Load Balancer's endpoint and tested its functionality.

Task 4: Load Testing
I performed load testing using a provided script to validate the scalability of the web application:

AWS Cloud9 Load Testing Script


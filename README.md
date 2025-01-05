# Host-Dynamic-App-using-ECS
Host a Dynamic Application Using AWS Elastic Container Service

### Introduction:
This Project demonstrates deploying the dynamic website in Elastic Container Service. A Containerized App is deployed in ECS cluster using Fargate mode which is serverless way of deploying the container application. Dynamic app is running in ECS Cluster in the private subnets in multiple Availability zone and fronted with Application Load balancer for efficient traffic distribution across multiple AZs and storing the data in RDS MYSQL database also deployed in private subnets.To connect the Private instances, EC2 Instance Connect Endpoint Service for secure SSH access.

### Architecture:

![image](https://github.com/user-attachments/assets/2db4aba9-7149-417d-bb10-9ad494b713b5)

### **Project Highlights**

1. **Version Control**:
   - Used **Git and GitHub** for seamless code deployment and storing the codebase efficiently.

2. **Containerization**:
   - Containerized the dynamic web application using **Docker** to ensure consistent runtime environments.

3. **RDS MySQL**:
   - Created and configured **RDS MySQL** to serve as the database for the application.

4. **ECS Cluster**
   - Created the Elastic Container Service Cluster to deploy the containerized App, ensuring scalability and resilience.

5. **FARGATE**
   - Used Sererless mode of running the container called "Fargate", which AWS automatically creates the compute in the background for running the ECS tasks.

6. **EC2 Instance Connect**:
   - Deployed **EC2 Instance Connect Endpoint** within the private subnet for secure access.

7. **TLS/SSL Encryption**:
   - Generated and stored **TLS/SSL certificates** using **AWS Certificate Manager (ACM)** for in-transit encryption.

8. **Secrets Manager**:
   - Stored cluster credentials securely in **Secrets Manager**, ensuring safe and centralized access.

9. **Database Migration**:
   - Used **S3** to store and execute **Flyway DB scripts** for migrating data to RDS MySQL.

10. **Elastic Container Registry (ECR)**:
    - Set up **ECR** to store Docker images for streamlined deployment to EKS.

11. **Route 53**:
    - Created a **Route 53** alias record to route traffic to the Network Load Balancer (NLB).

12. **IAM**:
    - Configured **IAM roles and policies** for secure access control.

13. **Load Balancer**:
    - Deployed a **Network Load Balancer (NLB)** in public subnets to distribute traffic efficiently across the cluster in multiple AZs.

14. **VPC Setup**:
    - Designed a **custom VPC** with public, private, and database subnets across multiple Availability Zones.
   
### **Understanding the ECS Cluster**
- To run the containerized App, ECS Cluster provides multiple modes which are EC2 mode and Fargate Mode. In EC2 Mode, we have to create the EC2 instances and maintain it for running the containerized app. However, In Fargate mode, AWS creates the compute in the background which is serverless way of running the containers.
- Create the ASG policy for scaling the ECS tasks
- Integrated with **CloudWatch** for real-time monitoring and logging.

### Key Learning Outcomes:
1. Designed and Implemented the VPC from scratch with the public and private subnets for the network isolation.

![image](https://github.com/user-attachments/assets/1e0f0b9f-1d05-4513-a951-82f360e72176)

2. Understand of creating and build docker file and image.

3. Create the Elastic Container Registry to store the docker image in AWS and push it from local computer.

![image](https://github.com/user-attachments/assets/1cd88286-f5fe-416e-9a1e-fb86fb315361)

4. Create and configure ECS Cluster to run ECS fargate container in the private subnet in both the AZ for High availabilty and fault tolerant.

![image](https://github.com/user-attachments/assets/c921a39c-493c-4226-bd60-1da2e3b43552)

![image](https://github.com/user-attachments/assets/590f0780-f9ae-40a0-a0ed-48429e0576a4)

5. Create the task defintion by providing the ECR image URI.

6. Create and configure the ECS Service by providing the network configuration, Auto-Scaling groups.

![image](https://github.com/user-attachments/assets/eaee3f14-0d4b-4d85-8821-7c70248fb3ce)

7. Executed database migrations using **Flyway** scripts hosted on **S3**.

8. Utilized **Secrets Manager** to secure credentials for ECS workloads.

9. Deployed **TLS/SSL certificates** to ensure secure communication through **ACM**.

10. Distributed traffic effectively using **ALB** with alias routing via **Route 53**.

![image](https://github.com/user-attachments/assets/788d8ca3-5d2b-4623-a484-e2d7a4d83408)

![image](https://github.com/user-attachments/assets/04636b12-4b0e-446d-a440-40b277482422)

### Conclusion:
This Project demonstrates successful deployment of Containerized application in ECS cluster using Fargate. This Architecture provides High Availability, Scalibility, Fault Tolerant and Secure way of implementing the cloud native applications.This hands-on experience reinforces the practical knowledge of designing, deploying, and managing cloud-based applications, making it a significant step forward in mastering modern application hosting solutions.

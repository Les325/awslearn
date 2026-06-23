# AWS EC2 Web Server Deployment and Management Lab

## **Task 1: Launch and Configure an Amazon EC2 Instance**

* Launched an Amazon EC2 instance using the Amazon Linux 2023 AMI.
* Selected a t3.micro instance type and configured networking within a Virtual Private Cloud (VPC).
* Created and configured a Security Group to control network access.
* Enabled termination protection to prevent accidental deletion of the instance.
* Used EC2 User Data to automate server configuration during launch.
* Installed and configured an Apache web server that automatically started when the instance booted.
* Deployed a basic web page to validate successful server provisioning.

## **Task 2: Monitor EC2 Instance Health and Performance**

* Reviewed EC2 instance status checks to verify system and instance health.
* Explored Amazon CloudWatch monitoring metrics for performance visibility.
* Accessed the EC2 Instance Screenshot feature to support troubleshooting and operational monitoring.
* Examined key instance details, networking configuration, and security settings through the AWS Management Console.

## **Task 3: Configure Security Group Rules and Access the Web Server**

* Tested external access to the deployed web server using the instance's public IPv4 address.
* Identified that inbound HTTP traffic was blocked by Security Group rules.
* Updated the Security Group to allow inbound HTTP (Port 80) traffic from the internet.
* Successfully verified web server accessibility by accessing the hosted webpage through a browser.

## **Task 4: Resize EC2 Compute and Storage Resources**

* Stopped the running EC2 instance to perform infrastructure modifications.
* Upgraded the instance type from t3.micro to t3.small to increase available compute resources.
* Modified the attached Amazon EBS root volume size from 8 GiB to 10 GiB.
* Restarted the instance and confirmed successful resource scaling.

## **Task 5: Test EC2 Termination Protection**

* Attempted to terminate the EC2 instance and verified that termination protection prevented deletion.
* Disabled termination protection through EC2 instance settings.
* Successfully terminated the instance after protection was removed.
* Demonstrated understanding of AWS safeguards designed to protect critical workloads from accidental deletion.

## **Skills Demonstrated**

* Amazon EC2
* Amazon EBS
* Amazon VPC
* Security Groups
* Instance Monitoring
* Amazon CloudWatch
* Linux Server Deployment
* Apache Web Server Configuration
* Infrastructure Scaling
* Termination Protection
* Cloud Infrastructure Management
* AWS Management Console
* Infrastructure Security Best Practices

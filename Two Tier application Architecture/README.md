Deploy 2-Tier application architecture

Stage 1 – Create a basic landing zone

Steps:- 
•	Create a VPC
•	Create  4 subnets, 2 in each availability zone
•	Create a internet gateway
•	Create a NAT gateway
•	Create 2 roles , a. OS administrator b. DB Administrator

Stage 2 – Deploy service in a availability zone and establish connectivity
•	Create EC2 instance using AWS Linux AMI with autoscaling group with minimum 1 node in public subnet – 1st availability zone
•	Login into EC2 instance and check internet accessibility
•	Install apache linux and tested apache services
•	Install RDS instance in private subnet
•	Establish connectivity between EC2 instance and RDS instance
•	Open only RDS DB instance port in security group to ensure only web server can reach to RDS instance over Database port.

Stage 3 – Deploy High Availability and testing
•	Create EC2 instance using AWS Linux AMI with autoscaling group with minimum 1 node in public subnet – 2nd availability zone
•	Login into EC2 instance and check internet accessibility
•	Install apache linux and tested apache services
•	Configure RDS replica for 1st RDS instance
•	Open only RDS DB instance port in security group to ensure only web server can reach to RDS instance over Database port.
•	Perform testing to check autoscaling group is working well. Checked secondary EC2 instance is able to connect with primary RDS instance. Checked internet load balancer is equally distributing the load across both EC2 instances

Services Used :
•	AWS EC2 Instances with AWS Linux
•	AWS RDS instances
•	Internet Gateway
•	VPC
•	IAM
•	Security Groups
•	NAT Gateway 
•	apache webserver

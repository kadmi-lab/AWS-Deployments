# AWS-Deployments

#Create Secure High availability network in AWS

1. Create VPC with IPv4 address range 10.0.0.0/16
2. Create Internet Gateway
3. Attach IGW to VPC
4. Create 2 Public Subnets in different availability zones and add them to our VPC
5. Edit subnet settings and "Enable auto-assign public IPv4 address" for both Subnets
6. Edit Route Table and add another route for destination "0.0.0.0/0" to Target to our created IGW
7. Create 2 Private Subnets in different availability zones and add them to our VPC
8. Create different Route Tables for Private Subnets
9. Create 2 Databse Subnets in different availability zones and add them to our VPC
10. Create Route Table for DB Subnets
11. Create 2 NAT Gateways
12. Edit both Route Tables and add another route for destination "0.0.0.0/0" to Target to our created NAT Gateways A and B

Our Network almost created 

Now we can also add Bastion Host so we can get access to private network from an external network
1. Create Security group to our VPC for SSH Bastion access from Anywhere "0.0.0.0/0"
2. Generate New Key pair
3. Create Launch Configuration for AutoScaling Group and add a "SSH Bastion access" Security Group
4. Create AutoScaling Group with Public Subnet A and B
5. Create Ec2 instances on Private and Database subnets
6. Connect via SSH to Bastion Host
7. Connect from Bastion Host to Private and Database Ec2 instances
8. Move key to Private and Database Ec2 instances
9. Test internet connection from EC2 instances

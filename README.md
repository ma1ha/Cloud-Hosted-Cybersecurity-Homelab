# Cloud-Hosted-Cybersecurity-Homelab
This project demonstrates the setup and implementation of a cloud-hosted cybersecurity homelab using AWS. The purpose of the lab is to create a safe and isolated environment to simulate real-world security attacks and defenses, such as penetration testing, vulnerability assessment, and monitoring network traffic.
# Architecture
This homelab consists of three EC2 instances with specific roles:

1- Vulnerable Box (Windows Client) - A standard Windows machine set up as a target for attack.

2- Attacker Box - A Kali Linux machine used to launch attacks on the vulnerable Windows machine.

3- Security Box - A monitoring machine used to capture traffic, monitor system performance, and perform vulnerability scans.

The instances are connected via a custom VPC with the necessary security groups and firewall rules to restrict access.
# Prerequisites
-AWS Account: You need an AWS account to provision EC2 instances and set up networking.

-IAM User: An IAM user should be created for managing the AWS environment.

-VPC Setup: A custom Virtual Private Cloud (VPC) should be set up with necessary subnetting and security group rules.
#  Setup Instructions
1. IAM User Creation
Create an IAM user for managing your AWS resources.

Attach the necessary permissions (e.g., AdministratorAccess).

Generate API keys for accessing AWS from the command line or automation tools.

3. Creating Security Groups
Vulnerable Box Security Group: This security group allows inbound and outbound traffic on specific ports required for communication.

Attacker Box Security Group: A similar security group with rules to allow connections from the attacker to the vulnerable box.

Security Box Security Group: Rules to monitor traffic, such as ports for Nessus and Splunk to collect data.

Common Ports Configured:
Port 22 (SSH) for remote management of Linux-based systems.

Port 3389 (RDP) for connecting to the Windows client.

5. Launching EC2 Instances
I launched three instances using AWS EC2 Images (AMIs):

 Windows Client (Vulnerable Box): A basic Windows image used as the target machine.
 
Attacker Image: A Kali Linux image used for launching attacks.

Monitoring Image (Security Box): A Linux-based image where I installed monitoring and scanning tools such as Splunk and Nessus.

4. Connecting to Instances
For each instance, use Remote Desktop Protocol (RDP) for Windows and SSH for Linux-based instances.
Ensure that security group rules allow remote connections.

5. Setting Up Monitoring and Scanning Tools
On the Security Box, install and configure the following tools:

Splunk: Used to capture and analyze logs, network traffic, and system performance.

Nessus: A vulnerability scanner used to identify security vulnerabilities in the Windows box.

7. Attacking the Windows Box
On the Attacker Box, I started by using common penetration testing tools like Metasploit, Netcat, and others to exploit vulnerabilities on the Vulnerable Box.
The goal was to gain unauthorized access to the Windows machine and escalate privileges.

8. Analyzing and Monitoring the Attack
On the Security Box, I used Splunk to capture logs and analyze network traffic between the attacker and the target machine.
I also performed vulnerability scanning using Nessus to detect any weaknesses in the Windows machine.

9. Results
I successfully gained access to the Windows box and performed various attacks to simulate a real-world penetration testing scenario.
Through Splunk and Nessus, I was able to monitor the attack and identify weaknesses in the system.

# Conclusion
This homelab setup has allowed me to experiment with real-world security scenarios in a controlled cloud environment. I was able to learn how to configure AWS instances, set up VPCs, use security groups, and employ various security tools to perform vulnerability assessments and monitor attacks.

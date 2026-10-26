# AWS/Linux Web Server Lab

A hands-on AWS project covering network configuration, Linux web-server deployment, monitoring, and service troubleshooting.

**Built by Corey Johnson**

## Video Walkthrough

[Watch the full project walkthrough on YouTube](https://youtu.be/vjFcq9BalmM)

## Project Goal

Build a working Linux-hosted website and practice supporting the infrastructure behind it: networking, access permissions, web-service configuration, monitoring, and recovery.

## Architecture

Internet traffic reaches an EC2 Linux instance through an internet gateway and a public subnet's route table.

Nginx serves the website, IAM provides AWS service permissions, and the CloudWatch agent reports server metrics.

## Tools Used

- Amazon VPC
- Amazon EC2
- AWS IAM
- Amazon CloudWatch and CloudWatch Agent
- Amazon Linux
- Nginx
- Linux command-line tools
- IPv4 addressing, CIDR, subnets, and routing
- Security groups

## What I Built

### 1. Network Foundation

- Created a VPC with the address space `10.20.0.0/16`.
- Created a public subnet using `10.20.1.0/24`.
- Created and attached an internet gateway.
- Configured a default route through the gateway.
- Associated the public subnet with its route table.

### 2. Linux Web Server

- Created an EC2 IAM role and web-server security group.
- Launched an EC2 Linux instance in the project network.
- Connected to the instance and performed package-management tasks.
- Installed and configured Nginx.
- Created the Corey CloudOps Lab website.
- Tested the website from a browser.

### 3. Monitoring

- Attached the CloudWatch agent policy to the EC2 role.
- Installed and configured the monitoring agent.
- Reviewed the server's reported metrics in CloudWatch.

### 4. Troubleshooting and Recovery

- Investigated web-service behavior using Linux commands and service output.
- Reviewed Nginx status and diagnostic information.
- Applied corrections and repeated HTTP/browser checks.
- Verified that the website was reachable after troubleshooting.

## Verification

The walkthrough shows:

- Network configuration and routing.
- EC2 instance creation and terminal access.
- Nginx installation and website configuration.
- CloudWatch agent configuration and metric review.
- Service investigation and a successful browser check.

## Lessons Learned

- Public connectivity depends on routing, addressing, and security-group rules working together.
- A running EC2 instance does not automatically mean its web service is working.
- Service status, logs, and HTTP checks provide different pieces of troubleshooting evidence.
- Monitoring helps establish what normal server behavior looks like.

## Project Scope

This is a personal portfolio lab, not a production or employer deployment.

It uses a single web server and demonstrates HTTP access. Production improvements would include HTTPS, stronger access controls, patch management, backups, and a tested high-availability design.

## Skills Demonstrated

Cloud networking, Linux administration, web-server configuration, IAM role configuration, monitoring, troubleshooting, and recovery verification.

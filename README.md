# My First AWS EC2 Instance

This repository documents the step-by-step process of how I created my first EC2 instance on AWS and set up monitoring with CloudWatch and SNS notifications.

## Step 1: Launching the Instance
- Logged into the **AWS Management Console**.
- Navigated to **EC2 → Instances → Launch Instance**.
- Selected **Amazon Linux 2 AMI**.
- Chose **t3.micro** (Free Tier eligible).
- Created a **key pair** for SSH access.
- Configured a **security group** to allow:
  - SSH (port 22) for Linux access
  - HTTP/HTTPS if hosting a web app

## Step 2: Connecting to the Instance
- Downloaded the `.pem` key file.
- Connected via SSH
- 
## Step 3: Monitoring with CloudWatch
Opened CloudWatch → Metrics → EC2 → CPUUtilization.

Created a CloudWatch Alarm:

Metric: CPUUtilization

Statistic: Average

Period: 5 minute

Threshold: Trigger if CPU > 70%

## Step 4: Configuring SNS Notifications
Created an SNS topic named EC2-CPU-Alarm.

Subscribed the account administrator’s email.

Confirmed subscription via email.

Linked the SNS topic to the CloudWatch alarm.


## Step 5: Testing the Alarm
Ran a CPU-intensive task on the instance to simulate high load.

Observed CPU utilization spike above threshold.

Alarm state changed to ALARM.

SNS notification was sent to the administrator’s email.

Alarm triggered notification

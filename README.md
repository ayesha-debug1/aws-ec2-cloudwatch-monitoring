# aws-ec2-cloudwatch-monitoring
Monitoring EC2 CPU utilization with Amazon CloudWatch alarms and SNS email notifications.



## 1. Project Overview

This project demonstrates how to monitor an Amazon EC2 instance using Amazon CloudWatch and configure automated email alerts through Amazon SNS.
The objective is to identify high CPU utilization on a server and notify the administrator so that the issue can be investigated.


## 2. Problem Statement

In a cloud environment, an EC2 instance may experience high CPU utilization due to heavy workloads, inefficient processes, or unexpected application activity.
High CPU usage can cause slow application responses and reduce server performance. Without proper monitoring and alerting, administrators may not notice the problem in time.


## 3. Proposed Solution

Amazon CloudWatch monitors the CPU utilization metric of the EC2 instance. A CloudWatch alarm evaluates the metric against a configured threshold.
When CPU utilization exceeds the threshold, the alarm enters the ALARM state and sends a notification through Amazon SNS.
This helps administrators identify potential performance issues earlier.


## 4. AWS Services Used

- Amazon EC2 — hosts the test server.
- Amazon CloudWatch — collects CPU metrics and evaluates alarms.
- Amazon SNS — sends email notifications.
- GitHub — stores project documentation and screenshots.


## 5. Architecture

EC2 Instance  
↓  
CloudWatch CPUUtilization Metric  
↓  
CloudWatch CPU Alarm  
↓  
Amazon SNS Topic  
↓  
Administrator Email Notification



## 13. References

- [Amazon EC2 Documentation](https://docs.aws.amazon.com/ec2/)
- [Amazon CloudWatch Documentation](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html)
- [CloudWatch CPU Alarm Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/US_AlarmAtThresholdEC2.html)
- [Amazon SNS Documentation](https://docs.aws.amazon.com/sns/)

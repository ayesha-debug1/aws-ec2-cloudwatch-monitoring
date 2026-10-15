## 1. Implementation Steps

1. Launched an Amazon Linux EC2 instance.
2. Verified CPU utilization in Amazon CloudWatch.
3. Created an SNS topic and confirmed an email subscription.
4. Configured a CloudWatch alarm for CPU utilization greater than 50%.
5. Generated CPU load on the test instance.
6. Verified the alarm state , CPU metrics and email notification.
7. Stopped the test workload and observed recovery.

<br>
<br>

## 2. Alarm Configuration

| Parameter | Configuration |
|---|---|
| Metric | CPUUtilization |
| Namespace | AWS/EC2 |
| Statistic | Average |
| Period | 5 minutes |
| Threshold | Greater than 50% |
| Evaluation periods | 1 |
| Notification | Amazon SNS email |

<br>
<br>

## 3. Testing and Results

| Test | Description | Result |
|------|-------------|--------|
|  1 | Simulated high CPU load on the EC2 instance by running a stress process, deliberately pushing CPU utilization above the configured alarm threshold | [CPU-load](screenshots/CPU-load.png) |
|  2 | Verified that the elevated CPU usage triggered the CloudWatch alarm, causing its state to change from OK to ALARM | [In-alarm](screenshots/In-alarm.png) |
|  3 | Reviewed the CloudWatch CPU metrics graph, which showed the CPU utilization line crossing the defined threshold value | [CPU-metrics](screenshots/CPU-metrics.png) |
|  4 | Confirmed that an email notification was received through the SNS topic, informing about the alarm state change along with the alarm details | [Email-notification](screenshots/Email-notification.png) |
|  5 | Stopped the running stress process on the EC2 instance so that CPU utilization could return to its normal baseline level | [CPU-ok-status](screenshots/CPU-ok-status.png) |
|  6 | Observed the alarm automatically return to the OK status once the CPU usage dropped back below the threshold, confirming normal recovery | [Alarm-ok-status](screenshots/Alarm-ok-status.png) |

<br>
<br>

## 10. Conclusion

This project demonstrates basic cloud monitoring and alerting using Amazon EC2, Amazon CloudWatch, and Amazon SNS.
It shows how cloud administrators can detect high CPU utilization and receive notifications without continuously checking the server manually.


# aws-guardduty-security-monitoring
monitoring of all AWS account activities and automatically alert me in real-time if any malicious behavior was detected 

Tech Stack

Data Logging:AWS CloudTrail, Amazon S3

Threat Detection (AI/ML):Amazon GuardDuty

Automation & Routing: Amazon EventBridge

Alerting: Amazon SNS (Simple Notification Service)


## Architecture Flow
1. CloudTrail continuously records all API calls and console actions across the AWS account and securely stores them in an S3 Bucket.
2. GuardDuty actively analyzes these CloudTrail logs, VPC Flow Logs, and DNS logs using machine learning to detect anomalies.
3. When GuardDuty detects a threat, it generates a "Finding" which triggers an **EventBridge Rule**.
4. The EventBridge rule pushes the alert to an **SNS Topic**, which instantly sends an email notification to the administrator.




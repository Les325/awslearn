# Monitor an EC2 Instance

## Overview

This lab focused on monitoring an Amazon EC2 instance using **Amazon CloudWatch** and **Amazon Simple Notification Service (SNS)**.

The lab demonstrated how logging and monitoring can be used together to maintain system performance, identify abnormal activity, and provide security visibility. A CloudWatch alarm was configured to detect when the CPU utilization of an EC2 instance exceeded a defined threshold, while an SNS topic was configured to send an email notification when the alarm entered the **In alarm** state.

A CPU stress test was then performed against the EC2 instance to simulate a scenario where abnormal activity, such as malware, causes CPU utilization to spike. A CloudWatch dashboard was also created to provide a quick visual view of the instance's CPU utilization.

---

## Task 1: Configure Amazon SNS

Created an Amazon SNS topic and email subscription to provide notifications when the CloudWatch alarm was triggered.

Key activities completed:

* Opened Amazon SNS from the AWS Management Console.
* Created a **Standard** SNS topic named `MyCwAlarm`.
* Created an email subscription for the SNS topic.
* Confirmed the subscription using the AWS notification email.
* Verified that the subscription status changed to **Confirmed**.

Skills demonstrated:

* Amazon SNS
* SNS topics
* SNS subscriptions
* Email notifications
* Notification confirmation
* Amazon CloudWatch alert integration

---

## Task 2: Create a CloudWatch Alarm

Configured an Amazon CloudWatch alarm to monitor the CPU utilization of the **Stress Test** EC2 instance.

Key activities completed:

* Opened CloudWatch Metrics.
* Navigated to **EC2 → Per-Instance Metrics**.
* Located the `CPUUtilization` metric for the Stress Test instance.
* Created a metric alarm using the CPU utilization metric.
* Configured the statistic as **Average**.
* Configured the monitoring period as **1 minute**.
* Set the threshold to trigger when CPU utilization was greater than **60 percent**.
* Configured the alarm to enter the **In alarm** state when the threshold was exceeded.
* Connected the alarm to the existing `MyCwAlarm` SNS topic.
* Created the alarm named `LabCPUUtilizationAlarm`.

Skills demonstrated:

* Amazon CloudWatch
* CloudWatch Metrics
* EC2 monitoring
* Metric alarms
* CPU utilization monitoring
* Alarm thresholds
* SNS integration

---

## Task 3: Test the CloudWatch Alarm

Performed a CPU stress test against the Stress Test EC2 instance to verify that the CloudWatch alarm and SNS notification system worked correctly.

Key activities completed:

* Connected to the Stress Test EC2 instance.
* Used the `stress` command to increase CPU utilization.
* Ran the stress test for 400 seconds.
* Used the `top` command to monitor live CPU utilization.
* Observed CPU utilization increase to approximately 100 percent.
* Monitored the `LabCPUUtilizationAlarm` in CloudWatch.
* Confirmed that the alarm changed to the **In alarm** state after CPU utilization exceeded the 60 percent threshold.
* Confirmed that an AWS Notifications email was received through the configured SNS subscription.

Command used for the CPU stress test:

    sudo stress --cpu 10 -v --timeout 400s

Command used to monitor CPU utilization:

    top

Skills demonstrated:

* EC2 instance monitoring
* CPU stress testing
* Linux command-line monitoring
* CloudWatch alarm validation
* SNS alert validation
* Security monitoring concepts
* Identifying abnormal CPU utilization

---

## Task 4: Create a CloudWatch Dashboard

Created a CloudWatch dashboard to provide a centralized view of the Stress Test EC2 instance's CPU utilization.

Key activities completed:

* Opened CloudWatch Dashboards.
* Created a dashboard named `LabEC2Dashboard`.
* Created a line graph widget.
* Selected the EC2 **Per-Instance Metrics**.
* Added the Stress Test instance's `CPUUtilization` metric.
* Created the metric widget.
* Saved the CloudWatch dashboard.

The dashboard provides a quick-access view of the EC2 instance's CPU utilization and can be used to monitor resource activity from a centralized location.

Skills demonstrated:

* CloudWatch dashboards
* Metric visualization
* EC2 performance monitoring
* CloudWatch widgets
* Operational monitoring

---

## Key Learning Outcomes

Completed practical exercises covering:

* Creating Amazon SNS topics and subscriptions.
* Configuring email-based SNS notifications.
* Using Amazon CloudWatch to monitor EC2 metrics.
* Monitoring the `CPUUtilization` metric.
* Creating CloudWatch metric alarms.
* Configuring alarm thresholds.
* Integrating CloudWatch alarms with SNS.
* Performing an EC2 CPU stress test.
* Using Linux `top` to monitor CPU utilization.
* Validating CloudWatch alarm state changes.
* Confirming SNS email notifications.
* Creating CloudWatch dashboards.
* Understanding how abnormal CPU utilization can be used as an indicator of potentially malicious activity.
* Understanding the relationship between monitoring, alerting, and security operations.

---

## Technologies Used

* Amazon EC2
* Amazon CloudWatch
* Amazon CloudWatch Metrics
* Amazon CloudWatch Alarms
* Amazon CloudWatch Dashboards
* Amazon SNS
* AWS IAM
* AWS Systems Manager Session Manager
* Linux
* Linux Command Line Interface (CLI)
* `stress`
* `top`

# Managing Services - Monitoring

## Overview

This lab focused on managing Linux services and monitoring system performance within an Amazon Linux environment running on Amazon EC2. The exercises introduced service management using `systemctl`, process monitoring with the `top` command, and infrastructure monitoring using Amazon CloudWatch.

The lab demonstrated how to verify service availability, monitor system resource utilization, simulate CPU workloads, and analyze performance metrics using both Linux and AWS monitoring tools.

---

**Task 1: Manage Linux Services**

Verified and controlled the Apache HTTP Server (`httpd`) service using Linux service management commands.

Key activities completed:

* Checked the status of the Apache HTTP service.
* Started and stopped the `httpd` service using `systemctl`.
* Verified service availability by accessing the web server through a browser.
* Confirmed successful service operation on the Amazon EC2 instance.

Skills demonstrated:

* Linux service management
* Service status verification
* Apache HTTP Server administration
* System administration using `systemctl`

---

**Task 2: Monitor System Processes**

Monitored system performance and resource utilization using built-in Linux tools.

Key activities completed:

* Displayed active system processes using the `top` command.
* Monitored CPU and memory utilization in real time.
* Executed a workload simulation script to generate increased CPU activity.
* Observed process behavior under system load.

Skills demonstrated:

* Process monitoring
* CPU utilization analysis
* Linux performance monitoring
* Real-time system administration

---

**Task 3: Monitor Infrastructure with Amazon CloudWatch**

Used Amazon CloudWatch to monitor the performance of an EC2 instance.

Key activities completed:

* Accessed the automatic EC2 monitoring dashboard.
* Reviewed key performance metrics, including CPU utilization, disk activity, and network traffic.
* Observed changes in resource usage during the simulated workload.
* Compared Linux command-line monitoring with AWS graphical monitoring tools.

Skills demonstrated:

* Amazon CloudWatch monitoring
* EC2 performance analysis
* Infrastructure monitoring
* Cloud operations and observability

---

**Key Learning Outcomes**

Completed practical exercises covering:

* Managing Linux services using `systemctl`.
* Verifying web server availability.
* Monitoring processes with the `top` command.
* Analyzing CPU utilization during simulated workloads.
* Monitoring Amazon EC2 instances using Amazon CloudWatch.
* Understanding the relationship between operating system metrics and cloud monitoring services.

---

**Technologies Used**

* Amazon Linux
* Amazon EC2
* Amazon CloudWatch
* Apache HTTP Server (httpd)
* SSH
* Linux Command Line Interface (CLI)
* systemctl
* top


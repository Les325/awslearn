# Managing Log Files

## Overview

This lab introduced Linux log management and basic security auditing by examining authentication logs and user login history on an Amazon EC2 instance. The exercises demonstrated how Linux stores security-related events and how administrators can investigate login activity, authentication failures, and system access using built-in logging tools.

The lab focused on reviewing system logs rather than modifying them, providing practical experience with monitoring and troubleshooting Linux systems.

---

## Task 1: Review Secure Log Files

Examined the Linux secure log to investigate authentication events and system access attempts.

Key activities completed:

* Connected to an Amazon Linux EC2 instance using SSH.
* Navigated to the working directory.
* Opened the sample secure log using `less`.
* Reviewed authentication failures and login attempts.
* Examined details such as usernames, source IP addresses, authentication status, and network ports.
* Exited the log viewer after inspection.

Skills demonstrated:

* Linux log analysis
* Security event monitoring
* Authentication troubleshooting
* Using the `less` command for log navigation

---

## Task 2: Review User Login History

Used the `lastlog` utility to examine previous user login activity.

Key activities completed:

* Executed the `lastlog` command.
* Reviewed the most recent login time for every user account.
* Identified accounts that had never logged in.
* Interpreted login history for auditing and administrative purposes.

Skills demonstrated:

* User account auditing
* Login history analysis
* System administration
* Linux account management

---

## Key Learning Outcomes

Completed practical exercises covering:

* Viewing Linux authentication logs.
* Investigating failed login attempts.
* Using `less` to navigate large log files.
* Reviewing user login history with `lastlog`.
* Understanding how Linux records authentication events.
* Performing basic security auditing on a Linux server.

---

## Commands Practiced

```bash
pwd
cd companyA
sudo less /tmp/log/secure
q
sudo lastlog
```

---

## Technologies Used

* Amazon Linux
* Amazon EC2
* SSH
* Linux Command Line Interface (CLI)
* System Log Files
* `less`
* `lastlog`
* Authentication Logs
* Linux Security Auditing
```

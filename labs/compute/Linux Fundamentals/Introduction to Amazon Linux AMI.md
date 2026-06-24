# Introduction to Amazon Linux AMI and Linux Command Line Fundamentals

## Overview
This lab provided hands-on experience working with an Amazon Linux Amazon Machine Image (AMI) hosted on Amazon EC2. The objective was to gain familiarity with accessing cloud-based Linux environments, using SSH for remote administration, and understanding the Linux manual page system for command discovery and documentation.

The lab demonstrated foundational skills required for cloud administration, including secure instance access, Linux shell navigation, and command-line troubleshooting.

---

**Task 1: Connect to an Amazon Linux EC2 Instance Using SSH**

Accessed an Amazon Linux EC2 instance within an AWS lab environment using Secure Shell (SSH).

Key activities completed:
- Retrieved and configured SSH credentials using an AWS-provided key pair.
- Updated private key permissions to ensure secure authentication.
- Established a remote connection to an EC2 instance using the Linux terminal.
- Authenticated into the Amazon Linux environment without password-based login.

Skills demonstrated:
- Amazon EC2 instance access
- SSH remote connectivity
- Linux terminal usage
- Secure key-based authentication

---

**Task 2: Explore Linux Manual Pages Using the `man` Command**

Used the Linux manual page system to explore built-in command documentation and understand how Linux users access command references.

Key activities completed:
- Used the `man` command to access documentation for Linux utilities.
- Examined common manual page sections, including:
  - NAME
  - SYNOPSIS
  - DESCRIPTION
  - OPTIONS
  - EXAMPLES
  - SEE ALSO
- Navigated and exited manual pages using terminal controls.

Skills demonstrated:
- Linux command documentation
- Bash terminal navigation
- Understanding Linux command structure
- Self-service troubleshooting using built-in documentation

---

**AWS Components Used**

**Amazon EC2**
- Worked with an EC2 instance running Amazon Linux.
- Used a t3.micro instance configured with:
  - 1 virtual CPU
  - 1 GiB memory
- Practiced basic cloud instance management and remote administration.

**Amazon Machine Image (AMI)**
- Used an Amazon Linux AMI as the operating system template for the EC2 environment.
- Gained exposure to how cloud providers use machine images to deploy virtual servers.

---

**Key Learning Outcomes**

Completed practical exercises covering:
- Launching and accessing cloud-based Linux environments.
- Using SSH as a primary method for secure server administration.
- Understanding the role of AMIs in AWS infrastructure.
- Navigating Linux documentation through manual pages.
- Building foundational Linux skills required for cloud engineering and DevOps workflows.

# Software Management

## Overview

This lab focused on managing software packages on an Amazon Linux EC2 instance using the **YUM package manager** and installing the **AWS Command Line Interface (AWS CLI)**. The exercises covered updating the operating system, managing package versions, viewing package history, rolling back software installations, and configuring the AWS CLI to interact with AWS resources directly from the Linux terminal.

The lab demonstrated essential Linux system administration tasks related to software lifecycle management and introduced the AWS CLI as a powerful tool for automating AWS resource management.

---

## Task 1: Update the Linux System

Used the YUM package manager to check for available updates and apply the latest software and security patches.

Key activities completed:

* Checked available package updates using YUM.
* Applied security-related updates.
* Upgraded installed packages to their latest versions.
* Installed the Apache HTTP Server (`httpd`) package.
* Reviewed installed packages and update history.

Skills demonstrated:

* Linux package management
* System updates
* Security patch management
* Software installation using YUM

---

## Task 2: Roll Back a Package Update

Learned how to inspect package installation history and undo previously completed software transactions.

Key activities completed:

* Displayed the YUM transaction history.
* Examined detailed information about previous package installations.
* Identified transaction IDs.
* Rolled back a previous package installation using YUM history.
* Verified package rollback functionality.

Skills demonstrated:

* Package version management
* Software rollback
* Transaction history analysis
* Linux package recovery

---

## Task 3: Install the AWS Command Line Interface (AWS CLI)

Installed the AWS CLI and its required dependencies on an Amazon Linux EC2 instance.

Key activities completed:

* Verified Python installation.
* Checked for the Python package manager (`pip`).
* Downloaded the AWS CLI installation package using `curl`.
* Extracted the installation archive.
* Installed the AWS CLI.
* Verified the installation using the built-in help command.

Skills demonstrated:

* Software installation
* Dependency verification
* Archive extraction
* AWS CLI installation

---

## Task 4: Configure the AWS CLI

Configured the AWS CLI to authenticate with AWS and interact with cloud resources from the command line.

Key activities completed:

* Configured AWS CLI default settings.
* Added AWS credentials to the credentials file.
* Specified the default AWS Region and output format.
* Connected the AWS CLI to the AWS account.
* Retrieved EC2 instance information using AWS CLI commands.

Skills demonstrated:

* AWS CLI configuration
* AWS authentication
* Credential management
* AWS service interaction
* EC2 resource querying

---

## Key Learning Outcomes

Completed practical exercises covering:

* Managing Linux software packages with YUM.
* Applying operating system and security updates.
* Installing and upgrading software packages.
* Viewing package installation history.
* Rolling back package updates.
* Installing the AWS Command Line Interface.
* Configuring AWS CLI credentials and default settings.
* Managing AWS resources directly from the Linux command line.

---

## Technologies Used

* Amazon Linux
* Amazon EC2
* SSH
* Linux Command Line Interface (CLI)
* YUM Package Manager
* AWS Command Line Interface (AWS CLI)
* Python 3
* pip
* curl
* unzip
* nano
* Amazon Web Services (AWS)

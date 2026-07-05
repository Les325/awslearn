# Bash Shell Scripts

## Overview

This lab focused on creating and executing Bash shell scripts to automate repetitive administrative tasks in Linux. The primary objective was to develop a reusable backup script that automatically creates a compressed archive of a directory using the current date as part of the filename.

The lab demonstrated how shell scripting can improve efficiency by combining multiple Linux commands into a single executable script, providing the foundation for task automation commonly used by Linux system administrators and DevOps engineers.

---

## Task 1: Create a Bash Backup Script

Created a Bash shell script to automate the backup of the **CompanyA** directory into a compressed `.tar.gz` archive.

Key activities completed:

* Created a new shell script named `backup.sh`.
* Modified file permissions to make the script executable.
* Added the Bash shebang (`#!/bin/bash`) to specify the script interpreter.
* Created variables to dynamically generate the current date and backup filename.
* Used the `tar` command to compress the CompanyA directory into a dated backup archive.
* Saved and executed the script from the command line.
* Verified that the backup archive was successfully created in the `backups` directory.

Skills demonstrated:

* Bash scripting fundamentals
* Creating executable scripts
* Using variables in shell scripts
* Linux automation
* Directory backup using `tar`

---

## Task 2: Automate File Naming

Used Linux variables and the `date` command to generate unique filenames automatically.

Key activities completed:

* Created a variable containing the current system date.
* Built dynamic backup filenames using variables.
* Stored backup archives with descriptive, date-based names.
* Eliminated the need to manually rename backup files.

Skills demonstrated:

* Variable creation
* Command substitution
* Dynamic file naming
* Bash syntax

---

## Task 3: Execute and Verify the Backup

Executed the completed Bash script and verified that the backup archive was successfully created.

Key activities completed:

* Ran the shell script using the Linux terminal.
* Observed the backup process through verbose output.
* Confirmed the archive was created in the designated backup directory.
* Validated the completed backup using directory listing commands.

Skills demonstrated:

* Script execution
* Archive verification
* Linux file management
* Backup validation

---

## Key Learning Outcomes

Completed practical exercises covering:

* Creating Bash shell scripts.
* Using the Bash shebang (`#!/bin/bash`).
* Making scripts executable with `chmod`.
* Working with variables and command substitution.
* Automating directory backups using `tar`.
* Generating dynamic filenames based on the current date.
* Executing reusable scripts from the Linux command line.
* Understanding how Bash scripting simplifies repetitive administrative tasks.

---

## Technologies Used

* Amazon Linux
* Amazon EC2
* SSH
* Bash Shell
* Linux Command Line Interface (CLI)
* Bash Scripting
* `tar`
* `chmod`
* `date`
* Shell Variables
* Vim

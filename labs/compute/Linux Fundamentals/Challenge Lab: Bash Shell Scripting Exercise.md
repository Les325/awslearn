# Challenge Lab: Bash Shell Scripting Exercise

## Overview

This challenge focused on applying Bash scripting concepts to automate file creation in a Linux environment running on an Amazon EC2 instance. The objective was to develop a reusable script that automatically creates batches of files while tracking previously created files to avoid duplicate numbering.

## Objectives

* Connect to an Amazon Linux EC2 instance using SSH.
* Create a Bash script to automate file creation.
* Generate 25 empty files using the `touch` command.
* Automatically determine the next available file number without hard-coding values.
* Validate the script by displaying the directory contents.

## Technologies Used

* Amazon EC2
* Amazon Linux 2
* Bash Shell
* SSH
* Nano Text Editor

## Commands Used

```bash
mkdir challenge
cd challenge
nano createfiles.sh
chmod +x createfiles.sh
./createfiles.sh
ls -l
```

## Script Features

The Bash script performs the following tasks:

* Stores a username in a variable.
* Detects the highest numbered file already present in the directory.
* Starts numbering from the next available number.
* Creates 25 new empty files using a loop.
* Prevents duplicate filenames by automatically continuing the numbering sequence.

Example output after the first execution:

```text
lesego1
lesego2
...
lesego25
```

Running the script again generates:

```text
lesego26
lesego27
...
lesego50
```

## Skills Demonstrated

* Bash scripting fundamentals
* Variables
* Command substitution
* Conditional statements (`if`)
* Arithmetic expansion
* `for` loops
* File creation with `touch`
* File permissions using `chmod`
* Linux directory navigation
* Script execution and testing

## Outcome

Successfully developed and tested an automated Bash script that creates sequential batches of empty files. The solution dynamically determines the highest existing file number and continues the numbering without requiring manual updates, demonstrating practical automation and scripting skills commonly used in Linux system administration.


# Working with Commands

## Overview

This lab focused on using essential Linux command-line utilities to process, manipulate, and analyze text files within an Amazon Linux environment running on Amazon EC2. The exercises introduced several powerful commands commonly used by Linux administrators and DevOps engineers to automate tasks, transform data, and improve command-line productivity.

The lab demonstrated how standard input, output redirection, pipes, and text-processing commands can be combined to efficiently manage and manipulate data.

---

**Task 1: Display and Save Command Output**

Used the `tee` command to display command output in the terminal while simultaneously saving it to a file.

Key activities completed:

* Generated the system hostname.
* Redirected command output to both the terminal and a text file.
* Verified successful file creation.

Skills demonstrated:

* Standard input and output handling
* Output redirection
* File creation using command output
* Linux command-line workflows

---

**Task 2: Sort and Search File Contents**

Created structured data files and manipulated their contents using sorting and search commands.

Key activities completed:

* Created a CSV file containing sample records.
* Sorted records alphabetically using the `sort` command.
* Used the pipe (`|`) operator to pass command output between utilities.
* Filtered file contents using `grep`.

Skills demonstrated:

* Data sorting
* Pattern searching
* Command chaining with pipes
* Linux text processing

---

**Task 3: Extract Data from Files**

Processed structured CSV data using field extraction commands.

Key activities completed:

* Created a CSV file containing city and state information.
* Used the `cut` command with delimiters to extract specific fields.
* Displayed selected data from structured text files.

Skills demonstrated:

* CSV file processing
* Field extraction
* Delimiter-based parsing
* Command-line data manipulation

---

**Task 4: Edit Text Using Stream Editor**

Modified text within files using the Linux stream editor.

Key activities completed:

* Replaced characters within CSV files using the `sed` command.
* Performed search-and-replace operations on structured data.
* Applied text transformations without manually editing files.

Skills demonstrated:

* Text replacement
* Stream editing
* File transformation
* Linux automation fundamentals

---

**Key Learning Outcomes**

Completed practical exercises covering:

* Command output redirection using `tee`.
* Sorting and filtering data with `sort` and `grep`.
* Command chaining with the pipe (`|`) operator.
* Extracting structured data using `cut`.
* Editing text programmatically using `sed`.
* Core Linux text-processing techniques used in system administration, automation, and DevOps workflows.

---

**Technologies Used**

* Amazon Linux
* Amazon EC2
* SSH
* Linux Command Line Interface (CLI)
* tee
* sort
* grep
* cut
* sed
* Pipe Operator (`|`)


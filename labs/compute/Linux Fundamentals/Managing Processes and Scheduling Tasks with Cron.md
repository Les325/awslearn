Overview

In this lab, I learned how to monitor Linux processes, capture process information into a log file, and automate administrative tasks using cron jobs. The lab also reinforced Linux command-line skills while working on an Amazon Linux EC2 instance.

Objectives
Connect to an Amazon Linux EC2 instance using SSH
Generate a process report using the ps command
Monitor running processes with the top command
Create a scheduled task using cron
Verify scheduled jobs using the root crontab
Skills Practiced
SSH
Linux Process Management
Process Monitoring
File Redirection
Pipes
grep
tee
cron
crontab
Basic sed usage
Commands Used
Connect to the EC2 Instance
ssh -i labsuser.pem ec2-user@<public-ip>
Verify Current Directory
pwd
Change Directory
cd companyA
Generate a Process Report
sudo ps -aux | grep -v root | sudo tee SharedFolders/processes.csv
Breakdown
Command	Purpose
ps -aux	Lists all running processes
grep -v root	Excludes processes owned by the root user
tee	Displays the output while saving it to a file
View the Report
cat SharedFolders/processes.csv
Monitor Running Processes
top

Information displayed includes:

Running tasks
Sleeping tasks
Zombie processes
CPU utilization
Memory usage
Swap usage

Exit the monitor by pressing:

q

(No need to press Enter.)

View Top Help and Version
top -hv
Creating a Cron Job

Edit the root crontab:

sudo crontab -e

Cron configuration:

SHELL=/bin/bash
PATH=/usr/bin:/bin:/usr/local/bin
MAILTO=root
0 * * * * ls -la $(find .) | sed -e 's/..csv/#####.csv/g' > /home/ec2-user/companyA/SharedFolders/filteredAudit.csv
Verify the Cron Job
sudo crontab -l

Expected output:

SHELL=/bin/bash
PATH=/usr/bin:/bin:/usr/local/bin
MAILTO=root
0 * * * * ls -la $(find .) | sed -e 's/..csv/#####.csv/g' > /home/ec2-user/companyA/SharedFolders/filteredAudit.csv
Key Linux Concepts Learned
ps

Displays information about currently running processes.

Example:

ps -aux
top

Provides a real-time view of:

CPU usage
Memory usage
Running processes
System load

Useful for troubleshooting system performance.

cron

A Linux scheduler that automatically runs commands at specified times.

Cron syntax:

* * * * * command
│ │ │ │ │
│ │ │ │ └── Day of Week
│ │ │ └──── Month
│ │ └────── Day of Month
│ └──────── Hour
└────────── Minute

Example used in this lab:

0 * * * *

Meaning:

Run at minute 0 of every hour, every day.

tee

Writes command output to both the terminal and a file simultaneously.

Example:

command | tee filename
grep -v

Filters out matching lines.

Example:

grep -v root

Removes all lines containing root.

sed

A stream editor used to modify text.

In this lab:

sed -e 's/..csv/#####.csv/g'

Replaces matching .csv filename patterns with #####.csv in the generated audit output.

Challenges Encountered

While completing the lab, I encountered a few issues that strengthened my understanding of Linux and Vim:

Initially attempted to exit top by pressing q followed by Enter, which caused Bash to interpret q as a command (command not found). Learned that pressing q alone exits top.
The lab instructions contained minor inaccuracies:
Pressing Enter after i in Vim inserted an unnecessary blank line.
Pressing the Space bar after SHELL=/bin/bash incorrectly placed the PATH variable on the same line.
Accidentally opened Vim's command-line window while editing the crontab and learned how to recover and correctly save the configuration.

These troubleshooting experiences improved my confidence using Linux editors and interpreting terminal behavior.

Key Takeaways
Learned how Linux manages processes.
Used ps and top to inspect system activity.
Created process log files for auditing.
Gained experience using pipes and output redirection.
Learned how cron automates recurring administrative tasks.
Became more comfortable editing configuration files using Vim.
Reinforced Linux troubleshooting and command-line navigation skills.
Technologies Used
Amazon EC2
Amazon Linux
SSH
Linux Terminal
Cron
Vim
Bash

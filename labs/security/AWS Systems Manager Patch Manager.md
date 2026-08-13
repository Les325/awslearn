AWS Systems Manager Patch Manager — Windows Patch Baseline & Compliance

Overview

This lab demonstrates how to use AWS Systems Manager Patch Manager to manage operating system patching across Amazon EC2 instances.

The lab covered:

Patching Linux EC2 instances using an AWS default patch baseline

Creating a custom Windows patch baseline

Associating the custom baseline with a patch group

Tagging Windows EC2 instances for patch management

Running Patch Manager using the instance tags

Verifying patch installation and compliance

The lab environment contained six EC2 instances:

3 × Amazon Linux

3 × Windows Server 2019

AWS Services Used

AWS Systems Manager

Patch Manager

Fleet Manager

Run Command

State Manager

Amazon EC2

AWS IAM

Lab Architecture / Workflow

The patching workflow used in this lab was:

EC2 Windows Instances
        │
        │  Tag: Patch Group = WindowsProd
        ▼
Patch Group
        │
        │  Associated with
        ▼
Custom Patch Baseline
WindowsServerSecurityUpdates
        │
        │  Windows Server 2019
        │  Security Updates
        │  Critical + Important
        │  Auto-approval: 3 days
        ▼
AWS Systems Manager Patch Manager
        │
        │  Patch Now
        ▼
Run Command / PatchBaselineOperations
        │
        ▼
Patch Installation
        │
        ▼
Compliance Reporting

Task 1 — Patch Linux Instances Using the Default Baseline

The Linux instances were patched using the AWS-provided default patch baseline:

AWS-AmazonLinux2DefaultPatchBaseline

Configuration used:

Patching operation: Scan and install

Reboot option: Reboot if needed

Target selection: Specify instance tags

Tag key: Patch Group

Tag value: LinuxProd

The three Linux instances were successfully patched and later reported as Compliant.

Task 2 — Create a Custom Windows Patch Baseline

A custom Windows patch baseline named:

WindowsServerSecurityUpdates

was created.

Patch Baseline Configuration

Operating system: Windows

Default patch baseline: No

Description: Windows security baseline patch

Approval Rule 1

Product: WindowsServer2019

Severity: Critical

Classification: SecurityUpdates

Auto-approval: 3 days

Compliance reporting: Critical

Approval Rule 2

Product: WindowsServer2019

Severity: Important

Classification: SecurityUpdates

Auto-approval: 3 days

Compliance reporting: High

The baseline was then associated with the patch group:

WindowsProd

Task 3 — Tag and Patch Windows Instances

Each Windows instance was tagged with:

Key

Value

Patch Group

WindowsProd

The instances were:

Windows-1

Windows-2

Windows-3

Patch Manager was then configured to target:

Patch Group = WindowsProd

with:

Patching operation: Scan and install

Reboot option: Reboot if needed

Patch Operation Verification

The Run Command output confirmed that Patch Manager was using the intended patch group and custom baseline.

Example output:

PatchGroup          : WindowsProd
BaselineId          : pb-0dc393e0afb80fae5
Baseline            : WindowsServerSecurityUpdates
OperationType       : Install
RebootOption        : RebootIfNeeded
FailedCount         : 0
MissingCount        : 0

The patch operation successfully installed patches on the Windows instances.

The output also demonstrated that Patch Manager uses the PatchBaselineOperations component to perform the patching operation.

Compliance Verification

The final Patch Manager compliance report showed all six instances as Compliant.

Final Compliance Result

Instance

OS

Compliance

Baseline

Windows-1

Windows Server 2019

Compliant

pb-0dc393e0afb80fae5

Windows-2

Windows Server 2019

Compliant

pb-0dc393e0afb80fae5

Windows-3

Windows Server 2019

Compliant

pb-0dc393e0afb80fae5

Linux-1

Amazon Linux

Compliant

pb-0e930e75b392d70da

Linux-2

Amazon Linux

Compliant

pb-0e930e75b392d70da

Linux-3

Amazon Linux

Compliant

pb-0e930e75b392d70da

The Windows nodes all reported the custom Windows baseline:

pb-0dc393e0afb80fae5

The Linux nodes reported the AWS default baseline:

pb-0e930e75b392d70da

Key AWS Concepts Learned

Patch Manager

AWS Systems Manager Patch Manager automates the process of scanning and installing operating system patches on managed nodes.

Patch Baseline

A patch baseline defines which patches are approved for installation and how compliance is evaluated.

Patch Group

A patch group associates a group of managed nodes with a particular patch baseline.

In this lab:

Patch Group = WindowsProd

was associated with:

WindowsServerSecurityUpdates

Tags and Patch Groups

EC2 tags were used to identify the Windows instances that should receive the custom baseline:

Key:   Patch Group
Value: WindowsProd

This allowed Patch Manager to target all three Windows instances together.

Run Command

Patch Manager uses Run Command to execute patching operations on managed nodes.

The lab output showed the PatchBaselineOperations process being executed on the Windows instances.

Compliance Reporting

Patch Manager provides compliance information showing whether managed nodes satisfy their assigned patch baseline.

Important compliance metrics include:

Critical non-compliant count

Security non-compliant count

Other non-compliant count

Available security updates

Last operation date

Baseline ID used

Troubleshooting Experience

During the lab, the Windows instances initially showed different compliance states.

Windows-1 and Windows-2 initially reported two available security updates as security non-compliant.

The custom baseline was adjusted so that available security updates were treated as Compliant for compliance reporting.

Windows-3 initially showed Never reported, but after running the patch operation again, it successfully reported against the same custom baseline.

The final compliance report showed all six instances as Compliant.

This demonstrated the importance of checking:

EC2 tags

Patch group association

Baseline ID used

Last patch operation

Patch compliance results

Key Takeaways

Patch Baseline = What patches are approved?

Patch Group = Which instances use the baseline?

EC2 Tags = How instances are grouped for targeting

Patch Manager = Automates patch scanning and installation

Run Command = Executes the patch operation

Compliance Reporting = Shows whether instances meet the baseline

A useful mental model is:

Instance Tag
     ↓
Patch Group
     ↓
Patch Baseline
     ↓
Patch Manager
     ↓
Run Command
     ↓
Patch Installation
     ↓
Compliance

Evidence / Screenshots

Recommended screenshots for the GitHub portfolio:

Custom WindowsServerSecurityUpdates patch baseline

Patch group showing WindowsProd

Windows EC2 instance tags

Patch Manager patch operation

Run Command output showing PatchGroup : WindowsProd

Final Compliance Reporting screen showing all six instances as Compliant

Conclusion

This lab provided practical experience with AWS Systems Manager Patch Manager, including custom patch baselines, patch groups, EC2 tagging, automated patch installation, Run Command execution, and compliance reporting.

The final environment successfully demonstrated patch management across both Linux and Windows EC2 instances, with all six instances reporting as Compliant.

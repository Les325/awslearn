# Introduction to AWS Identity and Access Management (IAM)

## Overview

This lab focused on **AWS Identity and Access Management (IAM)** and how it can be used to control access to AWS resources.

The primary objective was to create and apply an account-level password policy, explore IAM users and user groups, inspect managed and inline policies, assign users to groups based on their job functions, and test how those permissions affected access to Amazon S3 and Amazon EC2.

The lab demonstrated the principle of granting users only the permissions required for their role, using IAM groups and policies to centrally manage access to AWS resources.

---

## Task 1: Create an Account Password Policy

Created a custom IAM password policy to strengthen authentication requirements across the AWS account.

Key activities completed:

* Opened **AWS Identity and Access Management (IAM)**.
* Accessed **Account settings**.
* Modified the minimum password length from `8` to `10` characters.
* Enabled the required password complexity options.
* Left **Password expiration requires administrator reset** disabled.
* Configured password expiration to **90 days**.
* Configured prevention of password reuse for the previous **5 passwords**.
* Saved the updated account password policy.

Skills demonstrated:

* IAM account security
* Password policy configuration
* Authentication security
* AWS account-level security controls
* Identity security best practices

---

## Task 2: Explore IAM Users and User Groups

Explored the pre-created IAM users and user groups within the AWS account to understand how permissions can be assigned and managed.

Key activities completed:

* Reviewed the pre-created IAM users:
  * `user-1`
  * `user-2`
  * `user-3`
* Reviewed the permissions assigned to `user-1`.
* Confirmed that `user-1` initially had no permissions or group membership.
* Reviewed the security credentials associated with the user.
* Explored the pre-created IAM groups:
  * `EC2-Admin`
  * `EC2-Support`
  * `S3-Support`
* Inspected the **AmazonEC2ReadOnlyAccess** managed policy attached to the `EC2-Support` group.
* Inspected the **AmazonS3ReadOnlyAccess** managed policy attached to the `S3-Support` group.
* Inspected the customer inline **EC2-Admin-Policy** attached to the `EC2-Admin` group.
* Reviewed the structure of IAM policies.

### IAM Policy Structure

Examined the three fundamental components of an IAM policy statement:

* **Effect** — Specifies whether an action is `Allow` or `Deny`.
* **Action** — Specifies the AWS API actions that the identity can perform.
* **Resource** — Specifies which AWS resources the permissions apply to.

The lab demonstrated the difference between:

* **Managed policies** — Reusable policies that can be attached to multiple users or groups.
* **Inline policies** — Policies directly assigned to a specific user or group for more specific or one-off permissions.

Skills demonstrated:

* IAM user management
* IAM group management
* IAM policy inspection
* Managed policies
* Inline policies
* Understanding IAM policy structure
* Least-privilege access concepts

---

## Task 3: Add Users to IAM Groups

Assigned IAM users to groups according to their job responsibilities so that they inherited the appropriate permissions from the policies attached to those groups.

The business scenario assigned permissions as follows:

| User | Group | Permissions |
| --- | --- | --- |
| `user-1` | `S3-Support` | Read-only access to Amazon S3 |
| `user-2` | `EC2-Support` | Read-only access to Amazon EC2 |
| `user-3` | `EC2-Admin` | View, start, and stop EC2 instances |

Key activities completed:

* Added `user-1` to the **S3-Support** group.
* Added `user-2` to the **EC2-Support** group.
* Added `user-3` to the **EC2-Admin** group.
* Verified that each group contained the correct user.
* Confirmed that users inherited permissions through their group memberships.

This demonstrated how IAM groups can simplify permission management by assigning permissions to groups rather than configuring each user individually.

Skills demonstrated:

* IAM group membership
* Permission inheritance
* Role-based access control
* Least-privilege access
* Centralized permission management
* User access administration

---

## Task 4: Sign In and Test User Permissions

Tested the permissions of each IAM user by signing into the AWS Management Console and attempting to access different AWS services and perform different actions.

### User-1: S3 Support

Signed in as `user-1` and tested the permissions provided by the **S3-Support** group.

Key activities completed:

* Used the IAM user sign-in URL.
* Signed in as `user-1`.
* Accessed **Amazon S3**.
* Successfully viewed S3 buckets and their contents.
* Attempted to access **Amazon EC2**.
* Confirmed that `user-1` was not authorized to access EC2 resources.

This demonstrated that `user-1` had S3 read-only permissions but did not have EC2 permissions.

### User-2: EC2 Support

Signed in as `user-2` and tested the permissions provided by the **EC2-Support** group.

Key activities completed:

* Signed in as `user-2`.
* Accessed **Amazon EC2**.
* Successfully viewed EC2 instances.
* Attempted to stop an EC2 instance.
* Confirmed that the stop operation was denied because the user only had read-only permissions.
* Attempted to access Amazon S3.
* Confirmed that `user-2` did not have permission to list S3 buckets.

This demonstrated the difference between viewing AWS resources and modifying them.

### User-3: EC2 Administrator

Signed in as `user-3` and tested the permissions provided by the **EC2-Admin** group.

Key activities completed:

* Signed in as `user-3`.
* Accessed Amazon EC2.
* Successfully viewed EC2 instances.
* Selected an EC2 instance.
* Used the **Instance state** menu to stop the instance.
* Successfully stopped the EC2 instance.

This demonstrated that the EC2 administrator had broader permissions than the EC2 support user.

Skills demonstrated:

* IAM authentication
* IAM user sign-in
* Permission testing
* S3 access control
* EC2 access control
* Read-only permissions
* Resource modification permissions
* Permission troubleshooting
* Role-based access control

---

## Key Learning Outcomes

Completed practical exercises covering:

* Configuring an AWS account password policy.
* Understanding IAM users and user groups.
* Understanding the purpose of IAM policies.
* Understanding the difference between managed and inline policies.
* Reading IAM policy statements.
* Understanding `Effect`, `Action`, and `Resource`.
* Assigning users to IAM groups.
* Using groups to provide role-based permissions.
* Applying the principle of least privilege.
* Understanding permission inheritance through IAM groups.
* Testing permissions through the AWS Management Console.
* Controlling access to Amazon S3.
* Controlling access to Amazon EC2.
* Understanding the difference between read-only and administrative permissions.
* Verifying that unauthorized actions are denied by IAM.

A key concept demonstrated by the lab was:

**IAM User = Identity**

**IAM Group = Collection of users**

**IAM Policy = Permissions**

**Group Membership = Permissions inherited by the user**

**Least Privilege = Give users only the access required for their job**

---

## Technologies Used

* AWS Identity and Access Management (IAM)
* IAM Users
* IAM User Groups
* IAM Policies
* Managed Policies
* Inline Policies
* IAM Password Policies
* Amazon S3
* Amazon EC2
* AWS Management Console
* Role-Based Access Control (RBAC)
* Least-Privilege Access

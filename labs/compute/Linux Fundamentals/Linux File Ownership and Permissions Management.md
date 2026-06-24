# Linux File Ownership and Permissions Management

## Overview

This lab focused on managing file ownership, group ownership, and access permissions within a Linux environment running on Amazon EC2. The exercises simulated an enterprise file system where different departments and managers required controlled access to company resources.

The lab introduced Linux security fundamentals by assigning ownership, modifying permissions, and validating access controls using common administrative commands.

---

**Task 1: Configure File and Directory Ownership**

Updated ownership and group assignments for company departments and files.

Key activities completed:

* Assigned ownership of the company directory structure to designated users.
* Configured group ownership for departmental resources.
* Updated ownership recursively across nested directories and files.
* Verified ownership assignments using recursive file listings.

Skills demonstrated:

* Ownership management using `chown`
* User and group administration
* Recursive permission changes
* Linux access control management

---

**Task 2: Modify File Permission Modes**

Created files and managed permissions using both symbolic and numeric methods.

Key activities completed:

* Created files using the Vim editor.
* Applied symbolic permission changes using `chmod`.
* Applied absolute (numeric) permission changes using `chmod`.
* Verified permission assignments through file listings.

Examples of permissions configured:

* Added write access for group members.
* Assigned read, write, and execute permissions using numeric notation.

Skills demonstrated:

* Permission management using `chmod`
* Symbolic permission notation
* Numeric permission notation
* Linux file security administration

---

**Task 3: Assign Departmental Access Controls**

Configured ownership and permissions for departmental folders to support role-based access.

Key activities completed:

* Assigned ownership of Shipping resources to the Shipping manager.
* Assigned ownership of Sales resources to the Sales manager.
* Updated associated group ownership settings.
* Validated ownership and permission changes.

Skills demonstrated:

* Role-based access control (RBAC) concepts
* Departmental resource management
* Security administration
* Linux user and group permissions

---

**Key Learning Outcomes**

Completed practical exercises covering:

* Linux file ownership management.
* Group-based access control.
* Symbolic and numeric permission modes.
* Recursive permission and ownership changes.
* Security principles used in Linux server administration and cloud environments.

---

**Technologies Used**

* Amazon Linux
* Amazon EC2
* SSH
* Linux Command Line Interface (CLI)
* chown
* chmod
* Vim
* Linux User and Group Management

# AWS KMS and AWS Encryption SDK CLI

## Overview

This lab focused on using **AWS Key Management Service (AWS KMS)** together with the **AWS Encryption SDK Command Line Interface** to encrypt sensitive data using a KMS key.

The lab demonstrated how AWS KMS provides centralized key management while the AWS Encryption SDK performs client-side encryption of files. The exercise also introduced encryption context, commitment policies, encryption metadata, and the use of a KMS key ARN when performing encryption operations from the Linux command line.

---

## Task 1: Create and Configure an AWS KMS Key

Created and configured an AWS KMS key to be used as the wrapping key for encryption operations.

Key activities completed:

* Created/accessed the KMS key provided by the lab environment.
* Copied the KMS key ARN for use in later encryption commands.
* Identified the AWS Region associated with the KMS key.
* Used the KMS key ARN as the identifier for the encryption key.

Skills demonstrated:

* AWS KMS fundamentals
* Customer managed encryption keys
* KMS key ARNs
* AWS Region awareness
* Key management

---

## Task 2: Configure AWS Credentials and the Linux Environment

Configured the Linux environment so that AWS CLI and encryption operations could authenticate against AWS services.

Key activities completed:

* Configured AWS CLI credentials using `aws configure`.
* Reviewed the AWS credentials configuration.
* Confirmed the default AWS Region as `us-west-2`.
* Prepared the Linux environment for the AWS Encryption SDK CLI.

Skills demonstrated:

* AWS CLI configuration
* AWS authentication
* Linux environment configuration
* AWS Region configuration
* Credential management

---

## Task 3: Install and Configure the AWS Encryption SDK CLI

Installed the AWS Encryption SDK Command Line Interface and prepared it for use on the Linux instance.

Key activities completed:

* Installed the `aws-encryption-sdk-cli` Python package using `pip3`.
* Identified that the CLI executable was installed under `/home/ssm-user/.local/bin`.
* Added the installation directory to the `PATH`.
* Used `which aws-encryption-cli` to verify the executable location.
* Identified a Python 3.7 compatibility issue involving `importlib.metadata`.
* Installed and verified the `importlib-metadata` package.
* Updated the CLI dependency reference to use the compatible `importlib_metadata` module.
* Verified that `aws-encryption-cli --help` successfully executed.

Skills demonstrated:

* Python package installation
* AWS Encryption SDK CLI
* Linux PATH configuration
* Troubleshooting Python dependencies
* Command-line troubleshooting
* Package management with `pip3`

---

## Task 4: Create and Encrypt a Sensitive File

Created a test file containing sensitive information and encrypted it using the AWS Encryption SDK CLI and AWS KMS.

Key activities completed:

* Created an `output` directory for encrypted files.
* Created a test file named `secret1.txt`.
* Added test data to the file.
* Verified the file contents using `cat`.
* Stored the KMS key ARN in the `keyArn` shell variable.
* Used the KMS key as the wrapping key for the encryption operation.
* Applied an encryption context using `purpose=test`.
* Used the `require-encrypt-require-decrypt` commitment policy.
* Generated encryption metadata.
* Stored the encrypted output in the `output` directory.

The encryption command used was:

    aws-encryption-cli --encrypt \
        --input secret1.txt \
        --wrapping-keys key=$keyArn \
        --metadata-output ~/metadata \
        --encryption-context purpose=test \
        --commitment-policy require-encrypt-require-decrypt \
        --output ~/output/.

Skills demonstrated:

* File encryption
* AWS Encryption SDK
* AWS KMS integration
* KMS wrapping keys
* Encryption context
* Commitment policies
* Linux file management
* Command-line encryption

---

## Key Learning Outcomes

Completed practical exercises covering:

* Understanding the role of AWS KMS in encryption.
* Using a KMS key ARN with the AWS Encryption SDK.
* Configuring AWS CLI credentials in a Linux environment.
* Installing and configuring the AWS Encryption SDK CLI.
* Troubleshooting command-line tools and Python dependencies.
* Using shell variables to store a KMS key ARN.
* Encrypting files from the Linux command line.
* Using encryption context as additional authenticated information.
* Applying an AWS Encryption SDK commitment policy.
* Generating encryption metadata alongside encrypted files.
* Understanding how AWS KMS integrates with the AWS Encryption SDK to protect sensitive data.

---

## Technologies Used

* AWS Key Management Service (AWS KMS)
* AWS Encryption SDK
* AWS Encryption SDK CLI
* Amazon EC2
* AWS CLI
* Linux
* Bash Shell
* Python 3.7
* `pip3`
* `aws-encryption-cli`
* KMS Key ARN
* Encryption Context
* Commitment Policy

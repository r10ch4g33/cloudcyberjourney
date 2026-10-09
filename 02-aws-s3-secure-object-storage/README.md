# AWS S3 Secure Object Storage & Access Control

## 1. Project Overview

This project demonstrates how to configure an Amazon S3 bucket for secure object storage using AWS security best practices.

The focus is on preventing unintended public access, enabling encryption, validating access permissions, and documenting security controls.

**Project type:** Hands-on cloud engineering and cloud security
**Cloud platform:** Amazon Web Services (AWS)
**Primary service:** Amazon S3
**Difficulty:** Beginner

## 2. Objectives

* Create and configure an Amazon S3 bucket.
* Understand S3 buckets, objects, and bucket-level settings.
* Prevent unintended public access.
* Enable and verify default encryption.
* Upload and retrieve a test object.
* Validate authorised and unauthorised access.
* Document security decisions, evidence, and cleanup procedures.

## 3. Architecture


The project uses an Amazon S3 bucket to store a non-sensitive test file. Bucket-level security settings control public access and encryption. Access is tested using the AWS identity and permissions configured for the lab.

## 4. Services and Tools

* Amazon S3
* AWS Management Console

## 5. Implementation

### Step 1: Create the S3 bucket

* Region: ap-southeast-2
* Bucket name: 02-sample-bucket-v1-10102026
* Purpose: Store a non-sensitive sample object.

### Step 2: Configure public access protection

* Block Public Access: block all
* Bucket policy: Public access is blocked because Block Public Access settings are turned on for this bucket
* Public access test: view screenshot '01-Denied-user-isdenied-in-shell'

### Step 3: Configure encryption

* Default encryption: Server-side encryption with Amazon S3 managed keys (SSE-S3)

### Step 4: Upload a test object

* Object: sample-file.txt
* Purpose: Test storage and retrieval.
* Data classification: Non-sensitive test data.

### Step 5: Validate access permissions

| Test                                | Expected result | Actual result   |
| ----------------------------------- | --------------- | --------------- |
| Upload using authorised identity    | Allowed         | success - txt   |
| Access using unauthorised user      | Denied          | screenshot 01   |


## 6. Security Controls

* **Public access protection:** Prevents unintended public exposure of bucket objects.
* **Encryption at rest:** Protects stored objects using the configured encryption method.
* **Least privilege:** Access permissions should be limited to the actions and resources required.
* **Access validation:** Positive and negative tests help verify the intended permissions.
* **Credential safety:** No access keys, private keys, passwords, or other secrets are committed to this repository.

## 7. Validation and Evidence

Evidence is available in the `screenshots/` directory.

The evidence should demonstrate:

* Bucket configuration.
* Public access protection.
* Default encryption.
* Test object upload.
* Successful authorised access.
* Failed unauthorised access.

## 8. Challenges and Lessons Learned

[Document the real issues you encountered.]

Examples of topics to discuss:

* How bucket policies differ from IAM identity policies.
* Why an object URL does not automatically mean an object is publicly accessible.
* How to interpret AccessDenied errors.
* Why public access prevention and least-privilege permissions are separate controls.

## 9. AWS-to-GCP Mapping

| Concept                  | AWS                                               | Google Cloud                                            |
| ------------------------ | ------------------------------------------------- | ------------------------------------------------------- |
| Object storage           | Amazon S3                                         | Cloud Storage                                           |
| Identity and access      | AWS IAM                                           | Cloud IAM                                               |
| Public access protection | S3 Block Public Access and bucket policy controls | Public Access Prevention and IAM/bucket access controls |
| Encryption at rest       | S3 default encryption                             | Cloud Storage default encryption                        |
| Audit activity           | AWS CloudTrail                                    | Cloud Audit Logs                                        |

The services have similar purposes, but their permission models and configuration details are not identical.

## 10. Cost and Cleanup

* Confirm the bucket is empty before deleting it.
* Delete the test objects and any object versions created.
* Delete the bucket when no longer needed.
* Check AWS Billing and Cost Management for any remaining usage or charges.
* Record any costs or account-plan limitations encountered.

## 11. Future Improvements

* Create a dedicated least-privilege IAM role for the test workflow.
* Automate bucket configuration with Terraform.
* Add automated configuration checks.
* Extend the project with audit-log analysis.
* Compare the AWS implementation with a separate Google Cloud Storage implementation.

## 12. Key Takeaway

This project provides practical experience with AWS object storage, access controls, encryption, security validation, and technical documentation. It also demonstrates how core cloud-storage security concepts transfer between AWS and Google Cloud.

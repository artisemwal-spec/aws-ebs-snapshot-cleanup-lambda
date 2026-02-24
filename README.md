# Automated EBS Snapshot Cleanup with AWS Lambda

## Overview
This project implements an AWS Lambda–based automation to identify and delete unused or stale EBS snapshots in an AWS account.
Snapshots that are no longer linked to active EC2 workloads are automatically removed, helping reduce unnecessary storage costs and improve resource hygiene.

 ---
 
## How It Works
The Lambda function performs the following actions:

- Retrieves all EBS snapshots owned by the account
- Retrieves all running EC2 instances

Evaluates each snapshot and deletes it if:

- The snapshot has no associated volume
- The associated volume no longer exists
- The volume exists but is not attached to any running EC2 instance

---

## AWS Services Used
- AWS Lambda
- Amazon EC2
- Amazon EBS
- AWS IAM

---

## Required IAM Permissions
- ec2:DescribeSnapshots
- ec2:DescribeInstances
- ec2:DescribeVolumes
- ec2:DeleteSnapshot

---

## Use Case
- Automate cleanup of unused EBS snapshots
- Optimize AWS storage costs in dev and test environments
- Prevent accumulation of obsolete infrastructure resources

---

## Author
**Arti Semwal**

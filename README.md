# cost-optimization-project\# Identifying and Cleaning Stale EBS Snapshots using AWS Lambda

##  Project Overview
This project demonstrates how to optimize AWS storage costs by automatically identifying and deleting **stale EBS snapshots** that are no longer associated with any active EC2 instances.

The solution uses **AWS Lambda** with **Python (boto3)** to scan EBS snapshots owned by the AWS account and remove those that are no longer required.

##  Problem Statement
Over time, EBS snapshots accumulate due to:
- Deleted EC2 instances
- Deleted EBS volumes
- Unused backup snapshots

## These unused snapshots increase AWS storage costs unnecessarily.

##  Solution
A serverless AWS Lambda function that:
1. Retrieves all EBS snapshots owned by the account (`OwnerIds=['self']`)
2. Retrieves all active EC2 instances (running and stopped)
3. Checks whether each snapshot:
   - Has no associated volume, or
   - Is associated with a volume that is not attached to any active EC2 instance
4. Deletes such stale snapshots automatically

##  Technologies Used
- **AWS Lambda**
- **Amazon EC2**
- **Amazon EBS**
- **AWS IAM**
- **Python (boto3 SDK)**



# AWS Lambda and Boto3 Automation Assignments

## Overview

This repository contains solutions for multiple AWS automation assignments implemented using AWS Lambda and Boto3. The objective of these assignments was to automate common AWS operational and storage management tasks while gaining hands-on experience with AWS Lambda, IAM, Amazon EC2, Amazon S3, EventBridge, and Boto3.

---

# Assignment 1: Automated Instance Management Using AWS Lambda and Boto3

## Objective

Automate the starting and stopping of EC2 instances based on predefined tags.

## AWS Services Used

* AWS Lambda
* Amazon EC2
* AWS IAM
* Amazon CloudWatch
* Boto3

## Implementation Steps

1. Created two EC2 instances.
2. Tagged one instance with:

   * Key: Action
   * Value: Auto-Stop
3. Tagged another instance with:

   * Key: Action
   * Value: Auto-Start
4. Created an IAM role with AmazonEC2FullAccess permissions.
5. Developed a Lambda function to:

   * Identify instances tagged Auto-Stop and stop them.
   * Identify instances tagged Auto-Start and start them.
   * Log affected instance IDs.
6. Manually invoked the Lambda function.
7. Verified instance state changes in the EC2 Console.

## Result

Successfully automated EC2 instance management using Lambda and Boto3.

---

# Assignment 2: Automated S3 Bucket Cleanup Using AWS Lambda and Boto3

## Objective

Automatically delete files older than a specified retention period from an S3 bucket.

## AWS Services Used

* AWS Lambda
* Amazon S3
* AWS IAM
* Amazon CloudWatch
* Boto3

## Implementation Steps

1. Created an S3 bucket.
2. Uploaded test files.
3. Created an IAM role with AmazonS3FullAccess permissions.
4. Developed a Lambda function to:

   * List objects in the bucket.
   * Identify objects older than the configured retention period.
   * Delete outdated objects.
   * Log deleted files.
5. Tested the cleanup process through manual Lambda invocation.
6. Verified file removal from the bucket.

## Result

Successfully automated S3 object cleanup and retention management.

---

# Assignment 3: Auto-Tagging EC2 Instances on Launch Using AWS Lambda and Boto3

## Objective

Automatically tag newly launched EC2 instances for better resource tracking and governance.

## AWS Services Used

* AWS Lambda
* Amazon EC2
* Amazon EventBridge
* AWS IAM
* Amazon CloudWatch
* Boto3

## Implementation Steps

1. Created an IAM role with AmazonEC2FullAccess permissions.
2. Developed a Lambda function to:

   * Capture EC2 launch events.
   * Retrieve the instance ID.
   * Apply automatic tags including:

     * LaunchDate
     * Environment
3. Created an EventBridge rule to monitor EC2 instance launch events.
4. Configured EventBridge to trigger the Lambda function.
5. Launched a new EC2 instance.
6. Verified automatic tag creation.

## Result

Successfully automated EC2 instance tagging during launch events.

---

# Assignment 4: Archive Old Files from S3 to Glacier Using AWS Lambda and Boto3

## Objective

Automatically archive older S3 objects to Glacier storage for cost optimization.

## AWS Services Used

* AWS Lambda
* Amazon S3
* Amazon S3 Glacier
* AWS IAM
* Amazon CloudWatch
* Boto3

## Implementation Steps

1. Created an S3 bucket:

   * demobucket060701
2. Uploaded sample files.
3. Created an IAM role with AmazonS3FullAccess permissions.
4. Developed a Lambda function to:

   * List objects in the bucket.
   * Identify files older than six months.
   * Change the storage class to Glacier.
   * Log archived files.
5. Invoked the Lambda function manually.
6. Verified storage class transitions in S3.

## Result

Successfully automated archival of older S3 objects to Glacier storage class.

---

# Prerequisites

* AWS Account
* AWS Lambda
* Amazon EC2
* Amazon S3
* Amazon EventBridge
* AWS IAM
* Python 3.x
* Boto3

---

# How to Run

1. Create the required AWS resources.
2. Create the corresponding IAM roles.
3. Deploy the Lambda functions.
4. Configure EventBridge triggers where applicable.
5. Execute the Lambda functions manually or through configured events.
6. Verify outputs through AWS Console and CloudWatch Logs.

# Conclusion

These assignments demonstrate practical AWS automation using Lambda and Boto3. The implemented solutions automate infrastructure management, storage lifecycle operations, resource tagging, and archival processes while reducing manual effort and improving operational efficiency.

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

## Screenshots
<img width="773" height="395" alt="Auto-Start Tag" src="https://github.com/user-attachments/assets/9d328918-7021-4f3b-a04d-dbd99f817d36" />

<img width="768" height="391" alt="Auto-Stop Tag" src="https://github.com/user-attachments/assets/dcc3badd-fba0-44bc-b859-75ab5b9fdc42" />

<img width="794" height="317" alt="Instance Stopped" src="https://github.com/user-attachments/assets/9c035756-dc78-4d71-976e-f025f79b4a97" />

<img width="809" height="429" alt="Lambda Code" src="https://github.com/user-attachments/assets/fbbbed6c-4b40-409e-a621-2483684cfcee" />

<img width="959" height="421" alt="Lambda Function" src="https://github.com/user-attachments/assets/e49e7d6f-c0bd-47ce-b3fe-e0bddcbb89a4" />

<img width="766" height="418" alt="Role for Lambda" src="https://github.com/user-attachments/assets/dbaa596d-6d79-4fa3-9801-82b51b969791" />

<img width="757" height="449" alt="Test Event" src="https://github.com/user-attachments/assets/4acf0a36-8e87-473a-b770-83a527994a32" />

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

## Screenshot

<img width="1888" height="715" alt="Event" src="https://github.com/user-attachments/assets/6b520aff-8d3d-4233-8b26-ea02c4deb873" />

<img width="1915" height="973" alt="Files in S3 Bucket" src="https://github.com/user-attachments/assets/62733d70-ef73-4eb4-a97c-3ce7c05ca3f9" />

<img width="1535" height="861" alt="IAM Role" src="https://github.com/user-attachments/assets/45716354-1402-4db3-84fb-fcf59a64db03" />

<img width="830" height="443" alt="Lambda Code Deployment" src="https://github.com/user-attachments/assets/4e2a0b8d-8685-42c7-a2c4-8e8f5f76cffe" />

<img width="1918" height="834" alt="S3 Bucket" src="https://github.com/user-attachments/assets/b4886726-629b-4d55-862d-7c43503c37f5" />

<img width="1919" height="944" alt="Updated List" src="https://github.com/user-attachments/assets/0ccd99b7-9b30-4629-bed6-d0b55eded18b" />

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

## Screenshot

<img width="1594" height="858" alt="EC2Tagged" src="https://github.com/user-attachments/assets/1b4e2adc-4428-4a4d-822a-24d907d30ecc" />

<img width="1554" height="874" alt="EventBridge" src="https://github.com/user-attachments/assets/a5bbe599-0269-4093-90eb-4c8eccd2bae9" />

<img width="1473" height="912" alt="Lambda Function" src="https://github.com/user-attachments/assets/1843797f-d8fe-4137-99c4-f74428dbbd60" />

<img width="1914" height="928" alt="Lambda Role" src="https://github.com/user-attachments/assets/2345fbb7-2948-4abc-b539-9cbb3801941e" />

<img width="1600" height="660" alt="Screenshot 2026-06-07 015859" src="https://github.com/user-attachments/assets/94797572-dbbc-42c4-bee9-75ee8806d127" />

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

## Screenshot

<img width="1919" height="525" alt="LambdaCode" src="https://github.com/user-attachments/assets/6bcfe597-f130-4d2a-bb00-bcf7acfb8b81" />

<img width="1919" height="981" alt="LambdaFunction" src="https://github.com/user-attachments/assets/ac32beeb-8239-4ff0-9d4f-4a9967341694" />

<img width="1587" height="837" alt="LambdaRole" src="https://github.com/user-attachments/assets/700b7ba1-1319-4d64-8551-1014eb5bcb5e" />

<img width="1915" height="928" alt="S3Bucket" src="https://github.com/user-attachments/assets/7eb5b035-dee8-4e50-8bed-e27ee1a56dde" />

<img width="1614" height="848" alt="S3BucketArchival" src="https://github.com/user-attachments/assets/397cd750-afba-4567-a719-578b22c0de78" />

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

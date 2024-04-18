# File Upload Notification System

## Introduction
This project develops a system that observes an S3 Bucket for newly uploaded files. It operates by activating a Lambda function to handle uploaded files, dispatching notifications using SNS (Simple Notification Service), and retaining metadata in a SQS (Simple Queue Service) queue for subsequent processing.

## Benefits
- Real-time Monitoring: The system provides real-time monitoring of newly uploaded files to the S3 bucket, ensuring immediate awareness of data changes.

- Automated Handling: By activating a Lambda function, the system automates the handling of uploaded files, reducing manual intervention and streamlining workflows.

- Notification Dispatching: Dispatching notifications via SNS enables stakeholders to receive timely alerts about file uploads, facilitating prompt action or response.

- Metadata Retention: Storing metadata in an SQS queue allows for efficient and organized management of file-related information, aiding in subsequent processing or analysis.

- Scalability and Reliability: Leveraging AWS services like Lambda, SNS, and SQS ensures scalability and reliability, enabling the system to handle large volumes of file uploads seamlessly and consistently over time.

## Creating a Notification Pipeline

1. **Create a Bucket:** Name the bucket and select your region.
2. **Amazon SNS Setup:**
   - Create a topic in Amazon SNS.
   - Choose standard topics, ensuring FIFO (First In, First Out) message delivery if necessary.
   - Subscribe to the topic using your email for notifications.
3. **SQS Queue Configuration:**
   - Create a standard queue in Amazon SQS.
   - Leave remaining options as default.

## Setting Up Lambda Function

1. **Navigate to Lambda Page:**
   - Create a function from scratch with Python runtime environment.
   - Ensure to create a role with basic Lambda permissions.
2. **Set Permissions:**
   - Add policies to allow Lambda function access to SNS and SQS resources.

## Adding Code to Lambda Function

- Insert the provided Python code into the Lambda function, ensuring to adjust ARNs obtained from SNS and SQS configurations.
- Deploy the code.

## Configuring S3 Bucket Event Notification

1. **Configure Bucket Event Notification:**
   - Under bucket properties, create a new event notification.
   - Select all object create events.
   - Choose the Lambda function to trigger and save changes.

## Usage

- Upload a file to the S3 bucket.
- Receive a notification via email.
- If no email is received, check CloudWatch logs for debugging.
- View received messages in the SQS queue.

## Conclusion

This system effectively monitors file uploads to an S3 bucket, providing timely notifications for further processing or action.

[Read more](https://teebaba.hashnode.dev/file-upload-notification-system)

---
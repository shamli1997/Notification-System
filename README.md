# File Upload Notification System

## Overview

In this inaugural project, you will construct a sophisticated system that monitors an S3 bucket for newly uploaded files. It seamlessly triggers a Lambda function to process these files, sends out notifications using SNS, and diligently stores essential metadata in an SQS queue for subsequent processing.

## Architecture Diagram

![Notification-System Arhitecture Diagram](https://github.com/shamli1997/Notification-System/blob/main/notification-system-architecture.png)

## Video Walkthrough

Here's a walkthrough of implemented features:

<img src='https://github.com/shamli1997/Notification-System/blob/main/notification-system-demo.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />

## Key Components

1. **Amazon S3**:
   - **Event Trigger**: S3 is configured to trigger an event whenever a new file is uploaded to the bucket. This event initiates the Lambda function.

2. **AWS Lambda**:
   - **Processing**: The Lambda function is triggered by the S3 event. It processes the uploaded file and extracts essential metadata.
   - **Notification and Metadata Storage**: After processing, the Lambda function sends out notifications using SNS and stores metadata in an SQS queue for further processing.

3. **Amazon SQS**:
   - **Metadata Storage**: SQS is used to store the metadata of the processed files. This allows for asynchronous processing and decouples the file upload event from subsequent processing steps.

4. **Amazon SNS**:
   - **Notifications**: SNS is used to send out notifications about the new file upload. This can be used to inform other systems or users about the new file.

## Key Focus Areas

### a. S3 Event Trigger
   - The S3 bucket is configured to trigger an event when a new file is uploaded. This event contains information about the file, which is passed to the Lambda function.

### b. Lambda
   - The Lambda function is the core processing unit that is automatically triggered by the S3 event. It extracts metadata from the uploaded file and performs necessary processing.

### c. SQS
   - The metadata extracted by the Lambda function is sent to an SQS queue. This queue stores the metadata for further asynchronous processing.

### d. SNS
   - Notifications about the file upload are sent out using SNS. This ensures that any interested parties or systems are informed about the new file.

### e. Integration of S3 with Other Services
   - S3 is seamlessly integrated with Lambda, SQS, and SNS. The event-driven architecture ensures that file uploads trigger the necessary processing and notifications without manual intervention.

## Getting Started

To set up and deploy this system, follow these steps:

1. **Create an S3 bucket** in the desired region.
2. **Deploy the Lambda function** in the same or another AWS region.
3. **Create an SQS queue** and an SNS topic in the same region as the Lambda function or another region.
4. **Configure the S3 bucket to trigger the Lambda function** on file uploads.
5. **Ensure the Lambda function has the necessary permissions** to interact with S3, SQS, and SNS.
6. **Upload a file to the S3 bucket** and monitor the processing, notifications, and metadata storage.

## Conclusion

This project demonstrates the power of integrating various AWS services to create a robust, event-driven notification system. By leveraging S3, Lambda, SQS, and SNS, you can build scalable and efficient solutions to handle file uploads and subsequent processing.


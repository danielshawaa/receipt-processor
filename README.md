# Receipt Processor (AWS Serverless Project)

## Project Overview

This project is a serverless receipt processing system built using AWS. The goal of the project is to automatically read receipts and store important information like the vendor, purchase date, and total amount.

When a receipt image is uploaded, the system processes the receipt automatically using several AWS services. The extracted information is then stored so it can be used later for organizing or tracking expenses.

This project helped me understand how cloud services can work together to automate everyday tasks.

---

## Why I Built This Project

I built this project because I wanted to learn more about cloud computing and how automation can help with real life problems.

My mom often has to read and organize receipts for her clients and for regular day-to-day expenses. It can take a lot of time to go through each receipt and manually record the information. Watching that process made me curious about how technology could make something like that easier.

I wanted to build a simple system that could automatically read receipts and extract the important details so they could be stored and used later.

This project helped me explore how cloud services and AI tools can automate tasks that normally require manual work.

---

## How the System Works

The system follows a simple automated pipeline:

1. A receipt image is uploaded
2. The file is stored in Amazon S3
3. S3 triggers an AWS Lambda function
4. Lambda sends the receipt to Amazon Textract
5. Textract extracts the text from the receipt
6. The processed data is stored in DynamoDB

This entire process happens automatically once the receipt is uploaded.

---

## AWS Services Used

### Amazon S3

Amazon S3 is used to store receipt images. When a receipt is uploaded to the S3 bucket, it automatically triggers the rest of the processing pipeline.

Why I used it:
- Reliable cloud storage
- Easy to integrate with other AWS services
- Supports automatic event triggers

---

### AWS Lambda

AWS Lambda runs the backend code that processes the receipts.

When a receipt is uploaded to S3, Lambda is triggered and performs the following tasks:
- Sends the receipt to Textract
- Processes the extracted text
- Stores the data in DynamoDB

Why I used it:
- No servers to manage
- Automatically runs when triggered
- Works well with event-driven applications

---

### Amazon Textract

Amazon Textract is used to extract text and information from the receipt image.

Textract can identify important fields such as:
- Store name
- Purchase date
- Total amount
- Line items

Why I used it:
- Designed specifically for reading documents
- Uses machine learning to extract structured data

---

### Amazon DynamoDB

DynamoDB is the database used to store the extracted receipt information.

Each receipt record can include fields like:
- Receipt ID
- Vendor name
- Date
- Total purchase amount

Why I used it:
- Fast NoSQL database
- Works well with AWS Lambda
- Easy to store structured data

---

### AWS IAM

AWS IAM manages permissions between the services.

For example:
- Lambda needs permission to read from S3
- Lambda needs permission to call Textract
- Lambda needs permission to store data in DynamoDB

IAM allows these services to communicate securely.

---

## System Architecture

The workflow of the project looks like this:

User uploads receipt  
↓  
Amazon S3 stores the file  
↓  
S3 triggers AWS Lambda  
↓  
Lambda sends the receipt to Amazon Textract  
↓  
Textract extracts receipt information  
↓  
Data is stored in DynamoDB  

---

## Demo Video

Here is a short demo showing how the project works.

(Add your video here)

Example:

[Watch the demo]((https://youtu.be/u3c5CKqw0wo?feature=shared))

---



## What I Learned

From this project I learned:

- How serverless cloud applications work
- How different AWS services connect together
- How event-driven architectures operate
- How AI tools can automate document processing

---

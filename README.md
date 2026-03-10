# AI-Powered Receipt Processing System

This project automates receipt processing by extracting structured data from receipt images using AI-powered OCR.<br>
The system eliminates manual data entry by automatically extracting receipt information and storing it in a database for auditing and reporting.

---

## Architecture Overview

Receipt images are uploaded to Amazon S3, which triggers a Lambda function that processes the file using Amazon Textract.

Extracted data is parsed and stored in a DynamoDB table. After processing, an email notification containing the extracted information is sent via Amazon SES.

---

## Architecture Diagram

<p align="center">
  <img src="https://i.gyazo.com/92d4427239c3cec253fc6531da6aa497.png" alt="Diagram" width="700">
  <br>
  <sub>Figure 1: Architecture Diagram</sub>
</p>

---

### Key Services

- Amazon S3 – Receipt storage
- Amazon Textract – Optical Character Recognition (OCR)
- Amazon DynamoDB – Structured data storage
- Amazon SES – Email notifications
- AWS Lambda – Workflow automation
- IAM – Access management

---

## Workflow

```text
Receipt image uploaded to S3
        ↓
S3 triggers Lambda function
        ↓
Lambda sends image to Textract
        ↓
Textract extracts text from receipt
        ↓
Lambda processes extracted data
        ↓
Structured data stored in DynamoDB
        ↓
Email notification sent via SES
```

## Key AWS Configuration

Example configurations used during deployment.

<p align="center">
  <img src="https://i.gyazo.com/6a04a1b8f15e2dcd8ac2ba58ca443671.png" alt="Textract Configuration" width="600">
  <br>
  <sub>Figure 2: Textract Configuration</sub>
</p>

<p align="center">
  <img src="https://i.gyazo.com/0064f97d53ef5472a0570fcee8f9ee81.png" alt="Data Model for Receipt Information" width="500">
  <img src="https://i.gyazo.com/db39676bb2051927d2fa9e4d2a9a9019.png" alt="DynamoDB Table" width="700">
  <br>
  <sub>Figure 3: DynamoDB Table</sub>
</p>

---

## Processing Results

Example extracted receipt data stored in DynamoDB.

<p align="center">
  <img src="https://i.gyazo.com/d5d3d6af5c0f7c28a6bf27a4d5c3293b.png" alt="Receipt Processing Output" width="700">
  <br>
  <sub>Figure 4: Receipt Processing Output</sub>
</p>

---

## Key Features

- Automated receipt data extraction
- AI-powered document processing
- Serverless workflow automation
- Structured receipt storage for auditing

---

## Design Considerations

**AI Integration**<br>
Textract provides high-accuracy OCR for structured receipt extraction.

**Scalable Storage**<br>
DynamoDB enables fast retrieval and scalable storage for receipt records.

**Automation**<br>
Lambda orchestrates the workflow without requiring dedicated infrastructure.

---

## Future Improvements

- Add receipt categorization
- Create reporting dashboards
- Implement expense tracking features

---

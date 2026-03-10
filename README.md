# AI-Powered Receipt Processing System

This project automates receipt processing by extracting structured data from receipt images using AI-powered OCR.<br>
The system eliminates manual data entry by automatically extracting receipt information and storing it in a database for auditing and reporting.

---

## Architecture Overview

Receipt images are uploaded to Amazon S3, which triggers a Lambda function that processes the file using Amazon Textract.

Extracted data is parsed and stored in a DynamoDB table. After processing, an email notification containing the extracted information is sent via Amazon SES.

### Key Services

- Amazon S3 – Receipt storage
- Amazon Textract – Optical Character Recognition (OCR)
- Amazon DynamoDB – Structured data storage
- Amazon SES – Email notifications
- AWS Lambda – Workflow automation
- IAM – Access management

---

## System Workflow

1. Receipt image is uploaded to the S3 bucket.
2. The upload triggers a Lambda function.
3. Lambda sends the image to Amazon Textract for OCR processing.
4. Extracted text is parsed and structured.
5. Structured receipt data is stored in DynamoDB.
6. SES sends an email containing receipt details.

---

## Key Features

- Automated receipt data extraction
- AI-powered document processing
- Serverless workflow automation
- Structured receipt storage for auditing

---

## Architecture Diagram

<p align="center">
  <img src="https://i.gyazo.com/92d4427239c3cec253fc6531da6aa497.png" alt="Diagram" width="700">
  <br>
  <sub>Figure 1: Architecture Diagram</sub>
</p>

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

## Skills Demonstrated

- AI service integration
- Serverless automation
- NoSQL database design
- Document processing pipelines

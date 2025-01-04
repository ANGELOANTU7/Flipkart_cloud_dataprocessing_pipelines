# Flipkart Cloud Data Processing Pipelines

A comprehensive cloud-based system for processing, analyzing, and managing retail data through multiple specialized pipelines. This system integrates various AWS services to handle image processing, data ingestion, expiry management, and automated insight generation for Flipkart's retail operations.

## System Architecture

The system consists of four main pipelines, each handling specific aspects of retail data processing:

1. **Auto Flagging Pipeline**: Manages and processes store images for automated quality control
2. **Data Ingestion Pipeline**: Handles video processing and frame extraction for grocery detection
3. **Expiry Flagging Pipeline**: Tracks and manages expired inventory items
4. **Insight Generator Pipeline**: Generates automated reports and insights using AI

## Core Features

- Serverless architecture using AWS Lambda functions
- Automated image and video processing
- Real-time data ingestion and processing
- AI-powered insight generation using Google's Gemini
- Comprehensive error handling and monitoring
- Secure access management with presigned URLs
- Cross-origin resource sharing (CORS) support

## Prerequisites

- AWS Account with appropriate permissions
- Python 3.10+
- Docker (for Insights Generator)
- Google Cloud Project with Gemini API enabled (for Insights Generator)
- AWS CLI configured with necessary credentials

## Component Pipelines

### 1. Auto Flagging Pipeline
Handles image management and processing in S3 buckets with features for:
- Batch processing of images
- Flagged and unflagged image management
- Secure image access via presigned URLs
- Annotated frame processing

### 2. Data Ingestion Pipeline
Processes video data for AI-based grocery detection:
- Video upload through AWS Gateway
- Automated frame extraction
- Preview generation
- Dataset management and analysis
- Real-time metadata updates

### 3. Expiry Flagging Pipeline
Manages expired item tracking and reporting:
- Annotated frame retrieval for expired items
- DynamoDB-based expiry data management
- Device and batch-based organization
- Pagination support for large datasets

### 4. Insight Generator Pipeline
Generates automated reports and insights:
- Processes Excel files from S3
- AI-powered insight generation using Gemini
- PDF report creation
- Automated report distribution

## AWS Services Used

- AWS Lambda
- Amazon S3
- Amazon DynamoDB
- AWS API Gateway
- Amazon ECR
- AWS IAM

## Security

- Presigned URL implementation for secure resource access
- IAM roles configured with least privilege access
- CORS headers properly configured
- Environment variable management for sensitive data
- Regular credential rotation
- S3 bucket policy best practices

## Installation

Each pipeline has its own installation requirements. Please refer to the individual pipeline documentation for specific setup instructions:

- [Auto Flagging Pipeline](./Flipkart_AutoFlagging_Pipeline/README.md)
- [Data Ingestion Pipeline](./flipkart_data_ingestion_pipeline/README.md)
- [Expiry Flagging Pipeline](./Flipkart_Expiry_Flagging_Pipeline/README.md)
- [Insight Generator Pipeline](./Flipkart_Insight_Generator_Pipeline/README.md)

## Project Structure

```
Flipkart_cloud_dataprocessing_pipelines/
├── Flipkart_AutoFlagging_Pipeline/
│   └── Lambda functions for image processing
├── flipkart_data_ingestion_pipeline/
│   └── Video processing and frame extraction
├── Flipkart_Expiry_Flagging_Pipeline/
│   └── Expired item management
└── Flipkart_Insight_Generator_Pipeline/
    └── Report generation and insights
```

## Development

1. Clone the repository:
```bash
git clone <repository-url>
cd Flipkart_cloud_dataprocessing_pipelines
git submodule update --init --recursive
```

2. Follow the setup instructions in each pipeline's README for local development.

## Deployment

Each pipeline has its own deployment process. Generally:

1. Configure AWS credentials and permissions
2. Set up required AWS services (S3, DynamoDB, etc.)
3. Deploy Lambda functions or containers
4. Configure API Gateway endpoints if required

## Error Handling

All pipelines implement comprehensive error handling with standardized HTTP status codes:
- 200: Successful operation
- 400: Invalid request parameters
- 403: Access denied
- 404: Resource not found
- 500: Internal server error


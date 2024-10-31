# 3-Tier Architecture with AWS Lambda and PostgreSQL
# Author: Gabriela Neicu

## Overview

This project demonstrates a 3-tier architecture using AWS services and a Java-based application. The architecture consists of the following components:

1. Presentation Tier: A static website hosted on an S3 bucket and served via CloudFront.
2. Application Tier: An AWS Lambda function written in Java that processes S3 events.
3. Data Tier: An Amazon RDS PostgreSQL database that stores metadata - filename - about the files uploaded to the S3 bucket.

## Architecture

### Presentation Tier

- **S3 Bucket**: where the files will be uploaded
- **CloudFront**: Distributes the content globally with low latency.

### Application Tier

- **AWS Lambda**: A Java-based Lambda function that gets triggered when a file is uploaded to the S3 bucket. The Lambda function writes the file name to the PostgreSQL database.

### Data Tier

- **Amazon RDS**: A PostgreSQL database that stores metadata - filename about the files uploaded to the S3 bucket.

## Project Build

Project was built with ./gradlew build and 

## Deploy with Terraform 
terraform init
terraform apply

## Pre-requisites

AWS Free Tier Account to configure the resources (S3 with Trigger Object Created served via CloudFront, PostgresSQL DB with credentials, IAM Demo user with Access Key and Secret Key to configure AWS CLI)
# AWS Serverless Performance Optimization Lab

## Overview

This project demonstrates how to build, test, and optimize a serverless microservice using AWS services.

Technologies used:

* Amazon API Gateway
* AWS Lambda
* Amazon DynamoDB
* AWS Step Functions
* AWS Lambda Power Tuning
* Postman Performance Testing

The objective was to build a serverless API, test it under load, and identify the optimal Lambda memory configuration using data-driven analysis.

---

## Architecture

![Serverless Architecture](images/serverless-architecture.png)

Client → API Gateway → Lambda → DynamoDB

The Lambda function performs CRUD operations against DynamoDB through a REST API exposed by API Gateway.

### Serverless Benefits

* No servers to manage
* Auto scaling
* Pay-per-use pricing
* Event-driven architecture

---

## Load Testing with Postman

Performance testing was performed using Postman Runner.

### Test Configuration

* Ramp Up Profile
* 10 Virtual Users
* 2 Minute Duration

### Results

![Postman Test 1](images/postman-load-test-results-1.png)

![Postman Test 2](images/postman-load-test-results-2.png)

The tests established a performance baseline and helped measure application behavior under load.

---

## AWS Lambda Power Tuning

![Power Tuning Overview](images/lambda-power-tuning-overview.png)

AWS Lambda Power Tuning was used to compare multiple memory configurations:

* 128 MB
* 256 MB
* 512 MB
* 1024 MB

The objective was to identify the optimal balance between cost and performance.

### Power Tuning Results

![Power Tuning Results](images/lambda-power-tuning-results.png)

Key metrics evaluated:

* Execution duration
* Cost per invocation
* Cost vs Performance tradeoffs

---

## AWS Well-Architected Framework

### Performance Efficiency

Power Tuning helps identify the most efficient Lambda memory allocation.

### Cost Optimization

Different memory configurations impact execution cost and overall efficiency.

### Operational Excellence

Load testing provides measurable performance data that supports architecture decisions.

### Reliability

Testing validates application behavior under load and helps identify bottlenecks.

---

## Key Takeaways

One key takeaway from this project is that serverless applications still require performance engineering.

Rather than relying on default settings, load testing and Lambda Power Tuning provide measurable data that supports better architectural decisions and workload optimization.

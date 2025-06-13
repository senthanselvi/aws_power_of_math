# aws_power_of_math
**
Automated Power Calculator via AWS Lambda + API Gateway + DynamoDB**
This project is a serverless application that calculates the power of two numbers (base^exponent) using AWS services. The frontend is hosted on AWS Amplify, while the backend uses AWS Lambda, triggered via API Gateway, and stores the results in DynamoDB.

**Project Overview**
* Accepts base and exponent values from a web UI.
* Sends a POST request to an API Gateway endpoint.
* Triggers an AWS Lambda function to compute the result.
* Returns the result to the user on the frontend.
* Logs input and output to a DynamoDB table with a timestamp.


# aws_power_of_math

**Automated Power Calculator via AWS Lambda + API Gateway + DynamoDB**

This project is a serverless application that calculates the power of two numbers (`base^exponent`) using AWS services. The frontend is hosted on AWS Amplify, while the backend uses AWS Lambda, triggered via API Gateway, and stores the results in DynamoDB.

**Project Overview**
* Accepts `base` and `exponent` values from a web UI.
* Sends a POST request to an API Gateway endpoint.
* Triggers an AWS Lambda function to compute the result.
* Returns the result to the user on the frontend.
* Logs input and output to a DynamoDB table with a timestamp.
 
**Technologies Used**
* AWS Lambda
* Amazon API Gateway
* AWS DynamoDB
* AWS Amplify(for static web hosting)
* IAM(for permissions)
* Python

**Working**
1. A user enters a base and exponent in the web interface.
2. A JavaScript function sends these values as a POST request to API Gateway.
3. API Gateway triggers the Lambda function.
4. Lambda calculates the result (`base^exponent`) and stores the record in DynamoDB.
5. The result is returned and displayed in the browser.
 
**Deployment Steps**

**1. Frontend Deployment (Amplify)**
* Create a simple HTML + JS form to collect user input.
* Host the frontend on **AWS Amplify** using the “Deploy without Git” method.
* Use the Amplify-provided URL to access the UI.

**2. Lambda Setup**
* Create a Lambda function in AWS using **Python 3.9**.
* Write code to read `base` and `exponent`, compute the result, and return it.
* Add logic to log the result with a timestamp to DynamoDB.

**3. API Gateway Setup**
* Create a **REST API** in API Gateway.
* Create a `POST` method and link it to your Lambda function.
* Enable **CORS**.
* Deploy the API to a stage (e.g., `dev`) and note the **Invoke URL**.

**4. DynamoDB Setup**
* Create a DynamoDB table named `ThePowerOfMathDatabase`.
* Set primary key as `ID` (or use any unique identifier like timestamp + input).

**5. IAM Permissions**
* Attach a role to your Lambda function with the following permissions:

  * `AmazonDynamoDBFullAccess` (or scoped access to your table)
  * `AWSLambdaBasicExecutionRole`

**6. Integration**
* Update the frontend JS with the deployed API Gateway URL.
* Reupload the HTML file to Amplify to reflect the changes.

**7. Test the Application**
* Visit the hosted frontend.
* Enter numbers and click **Calculate**.
* You should see the result and verify that the data is stored in DynamoDB.

![image](https://github.com/user-attachments/assets/1a186da3-55b0-4c50-81c0-81bcf9eb836f)

![image](https://github.com/user-attachments/assets/0ebd8451-187d-4ec9-9ca8-5ceec116d82b)

![image](https://github.com/user-attachments/assets/d0535d07-f952-4118-beae-5ec73b90fa5d)

![image](https://github.com/user-attachments/assets/55cab539-5ac8-4ca2-87dc-3dd27172d1b9)

![image](https://github.com/user-attachments/assets/14c4e8e0-b9b6-4beb-a5a3-65fb4b18a4bd)

![image](https://github.com/user-attachments/assets/ab6492c2-0668-4537-b447-fb8c11a62158)









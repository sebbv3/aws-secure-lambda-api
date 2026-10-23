# Secure AWS Lambda API – AWS Security Lab

## Project Overview

This project focuses on building and securing a serverless REST API using AWS services. The goal was to implement an AWS Lambda function, expose it through Amazon API Gateway, configure API key authentication, apply AWS WAF security rules, and monitor the application using Amazon CloudWatch and SNS.

## AWS Services Used

- **AWS Lambda** – Serverless Python function for processing API requests.
- **Amazon API Gateway** – REST API integration with AWS Lambda.
- **AWS IAM** – Execution role and permissions management.
- **AWS WAF** – Configuration of security rules for web application protection.
- **Amazon CloudWatch** – Application logs, error monitoring, and alarms.
- **Amazon SNS** – Email notifications for Lambda errors.

## Implementation

### 1. AWS Lambda

Created a Python-based Lambda function named `SecureStudentAPI`.

The function processes incoming requests and returns a JSON response indicating successful execution.

### 2. API Gateway

Created a Regional REST API named `SecureStudentRESTAPI`.

- Configured a `GET /students` endpoint.
- Integrated the endpoint with AWS Lambda.
- Deployed the API to the `dev` stage.
- Successfully tested the API endpoint.

### 3. API Key and Usage Plan

Implemented API key-based access control.

- Created an API key.
- Configured the `StudentSecurityPlan` usage plan.
- Set a throttling rate of 5 requests per second.
- Configured a burst limit of 10 requests.
- Set a daily quota of 500 requests.
- Successfully tested authenticated API requests using PowerShell and the `x-api-key` HTTP header.

### 4. AWS WAF Configuration

Configured AWS WAF security rules, including:

- AWS Managed Core Rule Set.
- AWS Managed Known Bad Inputs Rule Set.
- A custom rate-based rule for request limiting.

The managed rule groups were configured in Count mode for monitoring, while the custom rate-based rule was configured to block requests exceeding the defined threshold.

The final WAF association and IP-blocking test were not verified.

### 5. CloudWatch Monitoring

Configured Amazon CloudWatch to monitor Lambda execution.

- Reviewed Lambda execution logs.
- Configured log retention.
- Created the `SecureStudentLambdaErrorAlarm`.
- Configured the alarm to detect Lambda execution errors.

### 6. Amazon SNS Notifications

Created the `StudentSecurityAlerts` SNS topic and configured email notifications.

- Confirmed the email subscription.
- Intentionally triggered a Lambda execution error.
- Successfully received a CloudWatch alarm notification by email.
- Restored and redeployed the original Lambda function afterward.

## Testing and Results

| Test | Result |
|---|---|
| Lambda execution | Successful |
| REST API GET request | Successful |
| API request with valid API key | Successful |
| API request without API key | Forbidden (403) |
| CloudWatch logging | Verified |
| Lambda error alarm | Triggered successfully |
| SNS email notification | Received successfully |
| WAF IP-blocking test | Not performed |

## Skills Demonstrated

- Serverless application development
- REST API deployment and integration
- API key access control
- AWS IAM permissions
- API throttling and usage quotas
- Web application firewall rule configuration
- Cloud monitoring and troubleshooting
- Automated alerting with CloudWatch and SNS
- API testing using Windows PowerShell

## Conclusion

This lab provided hands-on experience with AWS serverless architecture, API security, monitoring, and automated notifications.

The API, API key authentication, CloudWatch monitoring, and SNS email alerting were successfully tested. AWS WAF rules were configured, but the final IP-blocking verification was not completed.

**Environment:** AWS Academy Lab  
**Region:** US East (N. Virginia) – `us-east-1`  
**Language:** Python

**Screenshots**

<img width="1974" height="938" alt="Screenshot 2026-10-23 171442" src="https://github.com/user-attachments/assets/3ac0cc4f-a2f0-4a7c-88d3-1957c06eccb2" />
<img width="2559" height="1388" alt="Screenshot 2026-10-23 171000" src="https://github.com/user-attachments/assets/6d92bc93-a851-4b60-89ac-5f7e312bac8f" />
<img width="2559" height="1010" alt="Screenshot 2026-10-23 170634" src="https://github.com/user-attachments/assets/5e20423b-f6d4-458c-9b5d-75c83589d295" />
<img width="2559" height="684" alt="Screenshot 2026-10-23 170531" src="https://github.com/user-attachments/assets/eacdb050-e929-49f0-a48d-ed3ef7a0d37f" />
<img width="905" height="444" alt="Screenshot 2026-10-23 170443" src="https://github.com/user-attachments/assets/18a94b53-a4ba-4b2f-a101-bccd0e740c4f" />
<img width="2291" height="561" alt="Screenshot 2026-10-23 165321" src="https://github.com/user-attachments/assets/4a336f42-638e-4a0b-a128-9dcc88b79bdf" />
<img width="2559" height="1391" alt="Screenshot 2026-10-23 165215" src="https://github.com/user-attachments/assets/f9e74887-a8a7-4be0-a195-b26e992b00a9" />
<img width="1058" height="234" alt="Screenshot 2026-10-23 164128" src="https://github.com/user-attachments/assets/099e54f4-bf6c-4e2a-b785-477574461e35" />
<img width="2559" height="1391" alt="Screenshot 2026-10-23 162331" src="https://github.com/user-attachments/assets/e8391b29-e899-4ea1-9d68-2c5a05e5a769" />
<img width="2557" height="1388" alt="Screenshot 2026-10-23 162315" src="https://github.com/user-attachments/assets/4858fa86-4701-413a-8b77-6ee4f8727b32" />
<img width="2558" height="1389" alt="Screenshot 2026-10-23 162258" src="https://github.com/user-attachments/assets/cd31bae9-c228-4a9e-93ba-2012bd3acc68" />
<img width="2557" height="1390" alt="Screenshot 2026-10-23 161713" src="https://github.com/user-attachments/assets/47d629a6-477f-4f2a-bbb2-620581eca03a" />
<img width="2559" height="1394" alt="Screenshot 2026-10-23 161609" src="https://github.com/user-attachments/assets/41585a32-8202-47ce-b836-0ead297f8ed7" />
<img width="2559" height="1395" alt="Screenshot 2026-10-23 161515" src="https://github.com/user-attachments/assets/f233880f-ab43-4e36-ae33-dd831ed403a5" />
<img width="2559" height="1395" alt="Screenshot 2026-10-23 161343" src="https://github.com/user-attachments/assets/36ebc9bb-87f8-4d8e-a485-2c1a911163b2" />
<img width="1734" height="807" alt="Screenshot 2026-10-23 161056" src="https://github.com/user-attachments/assets/237e6cd9-ab26-43c0-bf56-93f11d5be3b7" />
<img width="2559" height="1392" alt="Screenshot 2026-10-23 160927" src="https://github.com/user-attachments/assets/215d4282-0813-4ad4-8139-a8673b6cf3d4" />

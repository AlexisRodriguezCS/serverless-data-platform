# 🧠 Serverless Data Platform – AWS Project

A cloud-based backend system that lets users upload data, store it safely, and run SQL queries on it — all using **AWS serverless services**. Built with **Python**, **AWS CDK**, and a full **CI/CD pipeline**.

---

## 🔧 What This Project Does

- Users can **sign up and log in** (via Cognito)
- Users can **upload files** through an API
- Files are stored in **Amazon S3**
- File info (metadata) is saved to **DynamoDB**
- Users can run **SQL queries** on their files using **Amazon Athena**
- The entire backend is **serverless** (Lambda, API Gateway)
- Infrastructure is deployed with **AWS CDK (Python)**
- CI/CD auto-builds, tests, and deploys on every commit
- Logs, metrics, and alarms are included for monitoring
- Designed for **multi-user support (multi-tenancy)**

---

## ☁️ AWS Services Used

| Service                  | What It Does                                                             |
|--------------------------|---------------------------------------------------------------------------|
| **AWS Lambda**           | Runs backend code without needing servers                                 |
| **Amazon API Gateway**   | Handles HTTP API requests and routes them to Lambda                       |
| **Amazon Cognito**       | Manages user sign-up, login, and access control                           |
| **Amazon DynamoDB**      | Stores metadata about uploaded files (NoSQL database)                     |
| **Amazon S3**            | Stores uploaded files and raw data                                        |
| **Amazon Athena**        | Lets users run SQL queries on S3 data                                     |
| **AWS CDK**              | Deploys infrastructure using Python code                                  |
| **AWS CodePipeline**     | Automates builds, tests, and deployments                                  |
| **AWS CodeBuild**        | Compiles code and runs tests                                              |
| **Amazon CloudWatch**    | Collects logs and system metrics                                          |
| **AWS X-Ray**            | Traces requests to help find and debug problems                           |
| **AWS IAM**              | Manages secure permissions for users and services                         |
| **AWS KMS**              | Encrypts stored data for security                                         |
| **AWS Secrets Manager**  | Stores passwords and API keys securely                                    |
| **AWS WAF**              | Protects APIs from common web attacks                                     |
| **Amazon CloudTrail**    | Records and audits API activity                                           |

---

## 🧱 Tech Stack

- **Language**: Python
- **Frameworks**: FastAPI (used inside Lambda), AWS CDK (Python)
- **Data**: S3 (files), DynamoDB (metadata), Athena (SQL queries)
- **Auth**: Amazon Cognito
- **CI/CD**: CodePipeline + CodeBuild
- **Monitoring**: CloudWatch, AWS X-Ray
- **Security**: IAM, KMS, WAF, Secrets Manager

---

## 🗂️ Project Structure

```text
/cdk/         → CDK code for infrastructure setup  
/src/         → Lambda functions (data upload, querying)  
/tests/       → Pytest unit and integration tests  
/docs/        → Diagrams and full architecture documentation  
```
## 🔍 How It Works (Quick Summary)
1. User logs in using Cognito
2. Upload request hits API Gateway → triggers a Lambda
3. Lambda stores the file in S3 + logs metadata in DynamoDB
4. Another API lets users run SQL queries using Athena
5. Monitoring and logging is set up using CloudWatch & X-Ray

## 🧪 Testing
- Tests are written using Pytest
- Includes unit tests for Lambda functions
- Integration tests use mock AWS services
- Tests are run automatically in the CI/CD pipeline before deployment

## 🛠️ CI/CD Pipeline
- Uses AWS CodePipeline and CodeBuild
- On code push to GitHub (or CodeCommit):
- Runs unit & integration tests
- Deploys infrastructure with CDK
- Supports dev, stage, and prod environments
- Automatically rolls back if deployment fails

## 🔐 Security Features
- Cognito + IAM roles control API access
- All data is encrypted using KMS
- Secrets (e.g. API keys) are in Secrets Manager
- AWS WAF protects the APIs from attacks
- CloudTrail tracks everything for security auditing

## 📈 Monitoring & Observability
- CloudWatch Logs: All Lambda/API logs
- CloudWatch Metrics: Function error rates, invocations, duration
- X-Ray Tracing: Full trace of API → Lambda → DynamoDB/S3
- Alarms: For high latency, errors, or failed invocations

## 📚 Documentation

Documentation is located in the `/docs/` folder.  

- `architecture.md` – Full system diagram and data flow explanation  
- `api.md` – API endpoints and usage guide  
- `auth.md` – Cognito setup and user roles  
- `deploy.md` – Step-by-step deployment instructions  
- `ci-cd.md` – How the CodePipeline/CodeBuild CI/CD works  
- `monitoring.md` – Logs, metrics, alarms, and X-Ray details  
- `security.md` – Security features and best practices used  

## 🙌 Contributions
This is a personal project but engineered to production-level quality. PRs and suggestions are welcome if aligned with the core vision.

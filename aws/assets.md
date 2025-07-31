# AWS Assets to Protect

This document identifies and classifies the key assets in the AWS environment that are critical to security, privacy, and business continuity.

| Asset Name               | Description                                              | Sensitivity Level (High / Medium / Low) |
|-------------------------|----------------------------------------------------------|----------------------------------------|
| **IAM Users and Roles**  | Identities used by humans and services with defined permissions | High                                   |
| **S3 Buckets**           | Object storage containing user data, backups, logs       | High                                   |
| **EC2 Instances**        | Virtual machines running application workloads           | Medium                                 |
| **Lambda Functions**     | Serverless compute resources executing application logic  | Medium                                 |
| **API Gateway Endpoints**| Entry points for APIs exposing backend services           | High                                   |
| **DynamoDB Tables**      | NoSQL databases storing application data                  | High                                   |
| **RDS Instances**        | Managed relational databases                               | High                                   |
| **CloudTrail Logs**      | Audit trail of API activity                                | High                                   |
| **CloudWatch Metrics & Alarms** | Monitoring and alerting data                          | Medium                                 |
| **VPC & Security Groups**| Network isolation and access control                       | High                                   |
| **Secrets Manager / Parameter Store** | Secure storage of secrets and configuration     | High                                   |
| **Cognito User Pools**   | User authentication and identity management               | High                                   |
| **CloudFront Distributions** | CDN for frontend content delivery                      | Medium                                 |

---

## Notes

- Sensitivity levels reflect potential impact on confidentiality, integrity, or availability.
- Assets marked **High** require stringent protection controls and monitoring.
- This list should be tailored to your specific AWS architecture and business requirements.


# AWS Mitigations & Security Controls

This document describes key mitigations to reduce the risk of identified threats within AWS environments. It includes AWS-native services and best practices.

---

## 1. Identity and Access Management (IAM)

- **Implement Least Privilege:**  
  Grant only necessary permissions to users, roles, and services.

- **Use IAM Roles Over Access Keys:**  
  Avoid long-lived access keys; prefer IAM roles with temporary credentials.

- **Enforce Multi-Factor Authentication (MFA):**  
  Require MFA for all privileged accounts, including root user.

- **Regularly Rotate Credentials:**  
  Implement automated credential rotation and revoke unused keys.

- **Use IAM Access Analyzer:**  
  Detect unintended resource access granted via policies.

---

## 2. Data Protection

- **Encrypt Data At Rest:**  
  Use AWS-managed or customer-managed AWS KMS keys for S3, EBS, RDS, DynamoDB.

- **Encrypt Data In Transit:**  
  Enforce TLS 1.2+ for all client-server and inter-service communication.

- **Use S3 Bucket Policies and ACLs:**  
  Restrict public access and implement fine-grained permissions.

- **Enable Versioning and MFA Delete on S3 Buckets:**  
  Protect against accidental or malicious deletions.

---

## 3. Network Security

- **Use VPCs and Subnets for Isolation:**  
  Segment resources and apply security group and network ACL rules.

- **Restrict Inbound and Outbound Traffic:**  
  Implement least privilege network access controls.

- **Deploy AWS WAF and Shield:**  
  Protect web applications from common exploits and DDoS attacks.

- **Use Private Endpoints (VPC Endpoints):**  
  Access AWS services without traversing the public internet.

---

## 4. Monitoring and Logging

- **Enable AWS CloudTrail:**  
  Record all API calls and monitor for suspicious activities.

- **Use Amazon CloudWatch:**  
  Monitor metrics and set alarms on anomalous behaviors.

- **Centralize Logs:**  
  Aggregate logs using services like Amazon Elasticsearch or AWS Lake Formation.

- **Implement Automated Alerts:**  
  Integrate with SNS or security tools to notify on critical events.

---

## 5. Secure Development and Deployment

- **Integrate Security into CI/CD Pipelines:**  
  Use AWS CodePipeline with security scanning (e.g., static analysis, dependency checks).

- **Use Infrastructure as Code (IaC):**  
  Define and enforce security best practices using CloudFormation, Terraform.

- **Scan IaC Templates:**  
  Use tools like AWS Config, Checkov, or Terraform Sentinel to enforce compliance.

---

## 6. Incident Response

- **Maintain an Incident Response Plan:**  
  Define roles, communication, and remediation steps.

- **Automate Recovery and Remediation:**  
  Use AWS Lambda for automated mitigation of common issues.

- **Regularly Test Incident Response Procedures:**  
  Conduct tabletop exercises and simulated attacks.

---

## 7. Additional Best Practices

- **Regular Security Audits and Penetration Testing:**  
  Identify gaps and validate controls.

- **Use AWS Security Hub:**  
  Centralize and prioritize security findings across AWS accounts.

- **Implement Guardrails via AWS Organizations:**  
  Enforce policies across multiple AWS accounts.

---

> *Note:* Tailor these mitigations based on your specific AWS architecture, risk appetite, and compliance requirements.


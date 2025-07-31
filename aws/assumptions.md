# AWS Threat Model Assumptions

This document lists the foundational assumptions underpinning the AWS threat model to clarify its scope and limitations.

---

## 1. Identity and Access

- IAM roles and policies are properly scoped with the principle of least privilege.
- Multi-Factor Authentication (MFA) is enforced on all privileged user accounts.
- Access keys and credentials are rotated regularly and securely stored.

## 2. Network and Infrastructure

- All network traffic is encrypted using TLS 1.2 or higher.
- AWS Virtual Private Clouds (VPCs) are configured with appropriate subnet segmentation and security groups.
- Public access to sensitive resources (e.g., S3 buckets, RDS instances) is strictly controlled or disabled.

## 3. Data Protection

- Data at rest is encrypted using AWS-managed or customer-managed keys via AWS KMS.
- Sensitive data is classified and handled according to organizational policies.

## 4. Logging and Monitoring

- AWS CloudTrail is enabled across all regions and accounts.
- Logs are centralized, immutable, and monitored for suspicious activities.
- Alerts are configured for critical security events.

## 5. Development and Deployment

- Infrastructure as Code (IaC) is used for provisioning, reviewed, and scanned for security compliance.
- CI/CD pipelines integrate automated security testing before deployment.
- Application code follows secure development best practices.

## 6. Operational

- Incident response plans are documented, tested, and maintained.
- Security patches and updates for AWS-managed services and custom components are applied promptly.

## 7. Limitations

- This model assumes no insider threat beyond normal privileged access controls.
- Zero-day vulnerabilities or sophisticated nation-state attacks are outside the scope.
- Compliance with regulatory frameworks (e.g., GDPR, HIPAA) is addressed separately.

---

> *Note:* These assumptions should be validated and updated regularly as your AWS environment evolves.


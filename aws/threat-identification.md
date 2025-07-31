# AWS Threat Identification

This document identifies potential threats to the AWS environment using the STRIDE threat modeling framework.

---

## STRIDE Threats for AWS

| STRIDE Category        | Threat Description                                      | Example Threats and Scenarios                                   | Targeted Asset / Service             | Mitigation Overview                    |
|-----------------------|--------------------------------------------------------|-----------------------------------------------------------------|------------------------------------|--------------------------------------|
| **Spoofing**          | Impersonation of users, services, or systems           | - Stolen IAM credentials or access keys<br>- Forged API requests | IAM Users, Access Keys, API Gateway | MFA, short-lived tokens, strict IAM policies |
| **Tampering**         | Unauthorized modification of data or configurations    | - Altered S3 bucket contents<br>- Modified Lambda function code  | S3 Buckets, Lambda functions       | Version control, encryption, logging |
| **Repudiation**       | Denial of performing an action                          | - Deleting CloudTrail logs to hide activities                    | CloudTrail logs, Audit Trails       | Immutable logging, monitoring alerts |
| **Information Disclosure** | Exposure of sensitive information                       | - Public S3 buckets exposing PII<br>- Verbose error messages     | S3 Buckets, API Gateway responses  | Bucket policies, encryption, WAF     |
| **Denial of Service** | Attacks making service unavailable                       | - API flooding causing throttling<br>- Excessive Lambda invocations | API Gateway, Lambda, EC2            | WAF, rate limiting, auto-scaling     |
| **Elevation of Privilege** | Unauthorized privilege escalation                      | - Over-permissive IAM roles<br>- Vulnerable Lambda function permissions | IAM Roles, Lambda execution roles   | Least privilege, role auditing        |

---

## Additional AWS-Specific Threat Scenarios

| Threat Description                             | Impact                         | Affected Components             | Suggested Controls                  |
|-----------------------------------------------|-------------------------------|--------------------------------|-----------------------------------|
| Compromised Access Keys leaked publicly       | Full account compromise       | IAM Access Keys, EC2 Instances  | Key rotation, use of IAM roles     |
| Misconfigured Security Groups allowing inbound traffic from untrusted IPs | Unauthorized network access   | VPC Security Groups             | Regular audits, automated compliance checks |
| Publicly accessible RDS databases              | Data breach                   | RDS Instances                  | Private subnets, encryption        |
| Lack of MFA on privileged accounts             | Increased risk of account takeover | IAM Users, Root account        | Enforce MFA, access monitoring     |

---

## References

- [AWS Well-Architected Framework - Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/framework/security.html)  
- [OWASP Cloud-Native Threat Model](https://owasp.org/www-project-cloud-native-application-security-top-10/)  
- [STRIDE Threat Model](https://www.practical-devsecops.com/what-is-stride-threat-model/?srsltid=AfmBOoq4HDGjiMoJyGGi3F47Qls-ZA-rM6gPsNG_w-rzPWI5v6HHw0-I)


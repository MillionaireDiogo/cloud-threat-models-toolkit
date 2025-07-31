# Azure Threat Model Assumptions

This document outlines the key assumptions made to define the scope and context of the Azure threat model.

---

## 1. Identity and Access

- Azure AD is properly configured with role-based access control (RBAC) following the principle of least privilege.  
- Multi-Factor Authentication (MFA) is enforced for all users with privileged access.  
- Managed Identities are used for service authentication instead of hardcoded credentials.  

## 2. Network and Infrastructure

- Azure Virtual Networks (VNets) and subnets are configured to isolate workloads and enforce security controls.  
- Network Security Groups (NSGs) and Azure Firewall are applied appropriately to restrict traffic.  
- Public exposure of critical resources such as Azure SQL Database and Blob Storage is minimized and controlled.

## 3. Data Protection

- Data at rest is encrypted using Azure Storage Service Encryption, Transparent Data Encryption (TDE), or customer-managed keys.  
- Data in transit is protected by TLS 1.2 or higher.  
- Sensitive data classification and handling policies are in place and followed.

## 4. Monitoring and Logging

- Azure Monitor, Log Analytics, and Security Center are enabled and configured to collect telemetry and security alerts.  
- Logs are retained according to organizational or regulatory requirements and are immutable.  
- Automated alerting is configured for critical events.

## 5. Development and Deployment

- Infrastructure as Code (IaC) is used to provision and manage resources, and templates are reviewed for security compliance.  
- CI/CD pipelines incorporate security testing and approvals.  
- Application code follows secure development lifecycle practices.

## 6. Operational

- Incident response plans are documented and regularly tested.  
- Security patches and updates for Azure services and deployed applications are applied promptly.

## 7. Limitations

- Insider threats beyond normal access controls are not explicitly modeled.  
- Advanced persistent threats (APTs) and zero-day vulnerabilities are considered out of scope.  
- Compliance with specific regulatory frameworks (e.g., GDPR, HIPAA) is handled separately.

---

> *Note:* Assumptions should be validated and updated periodically to reflect changes in the Azure environment and threat landscape.


# Azure Threat Identification

This document identifies potential threats to the Azure environment using the STRIDE threat modeling framework.

---

## STRIDE Threats for Azure

| STRIDE Category          | Threat Description                                      | Example Threats and Scenarios                                   | Targeted Asset / Service             | Mitigation Overview                    |
|-------------------------|--------------------------------------------------------|-----------------------------------------------------------------|------------------------------------|--------------------------------------|
| **Spoofing**            | Impersonation of users, services, or systems           | - Compromised Azure AD credentials<br>- Forged API calls to APIM | Azure Active Directory, APIM         | MFA, Conditional Access, managed identities |
| **Tampering**           | Unauthorized modification of data or configurations    | - Altered Blob Storage data<br>- Modified Azure Function code    | Azure Blob Storage, Azure Functions  | Encryption, versioning, logging      |
| **Repudiation**         | Denial of performing an action                          | - Deletion of Azure Monitor logs or Security Center alerts       | Azure Monitor Logs, Security Center | Immutable logs, alerting             |
| **Information Disclosure** | Exposure of sensitive information                       | - Public Blob containers exposing PII<br>- Verbose error messages | Azure Blob Storage, API responses    | Access policies, encryption, WAF    |
| **Denial of Service**   | Attacks making services unavailable                      | - API flooding of APIM<br>- Excessive Azure Function invocations | API Management, Azure Functions       | Throttling, autoscaling, Azure DDoS Protection |
| **Elevation of Privilege** | Unauthorized privilege escalation                      | - Over-permissive RBAC roles<br>- Vulnerable Function permissions | Azure RBAC, Azure Functions           | Least privilege, role reviews        |

---

## Additional Azure-Specific Threat Scenarios

| Threat Description                             | Impact                         | Affected Components             | Suggested Controls                  |
|-----------------------------------------------|-------------------------------|--------------------------------|-----------------------------------|
| Compromised Azure AD credentials leaked       | Full tenant compromise         | Azure AD, AAD Users             | Conditional Access, Identity Protection |
| Misconfigured NSGs allowing broad access      | Unauthorized network access    | VNets, Network Security Groups | Regular audits, automation        |
| Publicly accessible Azure SQL Databases       | Data breach                   | Azure SQL Database              | Private endpoints, firewall rules |
| Lack of MFA on privileged accounts            | Increased risk of takeover     | Azure AD users, Admins          | Enforce MFA, monitor sign-ins     |

---

## References

- [AWS Well-Architected Framework - Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/framework/security.html)  
- [OWASP Cloud-Native Threat Model](https://owasp.org/www-project-cloud-native-application-security-top-10/)  
- [STRIDE Threat Model](https://www.practical-devsecops.com/what-is-stride-threat-model/?srsltid=AfmBOoq4HDGjiMoJyGGi3F47Qls-ZA-rM6gPsNG_w-rzPWI5v6HHw0-I)


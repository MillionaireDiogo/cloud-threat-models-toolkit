# Azure Risk Assessment Using DREAD

This document provides risk scoring for identified threats in the Azure environment using the DREAD model.

---

## DREAD Risk Scoring Table

| Threat Scenario                                     | Damage (1-10) | Reproducibility (1-10) | Exploitability (1-10) | Affected Users (1-10) | Discoverability (1-10) | Total Score | Risk Level  |
|----------------------------------------------------|---------------|------------------------|----------------------|----------------------|------------------------|-------------|-------------|
| Publicly exposed Azure Blob container with sensitive data | 9             | 9                      | 8                    | 10                   | 7                      | 43          | High        |
| Overly permissive Azure RBAC role allowing privilege escalation | 8             | 8                      | 7                    | 9                    | 6                      | 38          | High        |
| DoS attack on API Management causing throttling    | 6             | 7                      | 8                    | 8                    | 6                      | 35          | Medium      |
| Deletion of Azure Monitor logs to hide malicious activity | 7             | 6                      | 7                    | 9                    | 5                      | 34          | Medium      |
| Unencrypted sensitive data in Blob Storage         | 8             | 6                      | 6                    | 8                    | 5                      | 33          | Medium      |
| Lack of MFA on privileged Azure AD users           | 7             | 5                      | 5                    | 9                    | 6                      | 32          | Medium      |
| Misconfigured NSG allowing public access           | 6             | 5                      | 6                    | 7                    | 5                      | 29          | Low         |

---

## Risk Level Definitions

- **High (40-50):** Immediate remediation required  
- **Medium (30-39):** Address soon and monitor closely  
- **Low (<30):** Acceptable risk or monitor  

---

## Recommendations

- Prioritize remediation of high-risk issues such as exposed sensitive data and privilege escalation.  
- Implement continuous monitoring and automated scanning to detect misconfigurations early.  
- Enforce strong identity and access management policies including MFA and least privilege principles.  
- Regularly review audit logs and Azure Monitor events for suspicious activities.  

---

## Notes

- Adjust scores based on your specific environment and threat landscape.  
- Use this assessment as part of a continuous risk management process.


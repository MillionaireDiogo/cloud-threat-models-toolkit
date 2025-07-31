# Azure Assets to Protect

This document identifies critical assets within the Azure environment that require protection due to their sensitivity and importance.

| Asset Name                  | Description                                                | Sensitivity Level (High / Medium / Low) |
|-----------------------------|------------------------------------------------------------|----------------------------------------|
| **Azure Active Directory (AAD)** | User identities, groups, and access tokens                 | High                                   |
| **Azure Blob Storage**       | Object storage for user files, backups, logs                | High                                   |
| **Azure Virtual Machines**   | Compute instances hosting applications                      | Medium                                 |
| **Azure Functions**          | Serverless compute resources                                | Medium                                 |
| **API Management (APIM)**    | API gateways exposing backend services                      | High                                   |
| **Cosmos DB**                | Globally distributed NoSQL database                         | High                                   |
| **Azure SQL Database**       | Managed relational database                                 | High                                   |
| **Azure Monitor Logs**       | Application and infrastructure telemetry                    | Medium                                 |
| **Network Security Groups**  | Traffic filtering and network access control                | High                                   |
| **Azure Firewall**           | Managed firewall for network security                        | High                                   |
| **Azure Key Vault**          | Secure storage for secrets, keys, and certificates          | High                                   |
| **Azure CDN**                | Content delivery network for static assets                   | Medium                                 |
| **Azure DevOps Pipelines**   | CI/CD pipelines for automated deployments                   | Medium                                 |

---

## Notes

- Sensitivity levels are assigned based on potential impact to confidentiality, integrity, or availability.  
- Customize this list based on your specific Azure deployment and business context.


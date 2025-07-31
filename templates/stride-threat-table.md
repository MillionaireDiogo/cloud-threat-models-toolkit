# ⚠️ STRIDE Threat Modeling Table

Use this STRIDE table to categorize and document potential threats in your system. STRIDE stands for:

- **S**poofing
- **T**ampering
- **R**epudiation
- **I**nformation Disclosure
- **D**enial of Service
- **E**levation of Privilege

---

## 📊 STRIDE Table

| STRIDE Category | Threat Description | Example Threats | Target Asset | Likelihood (H/M/L) | Impact (H/M/L) | Mitigation |
|-----------------|--------------------|------------------|---------------|--------------------|----------------|------------|
| **Spoofing** | Impersonating users or systems | Stolen credentials, session hijacking | IAM Users, Web Login | Medium | High | MFA, token validation, short-lived credentials |
| **Tampering** | Unauthorized modification of data or code | Tampering with APIs, modifying S3 content | Data Storage, APIs | Medium | High | Input validation, WORM storage, checksum |
| **Repudiation** | Denying performed actions | User denies deleting resources | Activity Logs, Audit Trails | Low | Medium | Centralized logging, immutability |
| **Information Disclosure** | Leaking sensitive information | Public S3 buckets, verbose error messages | PII, Secrets, Logs | High | High | Encryption, IAM policies, WAF |
| **Denial of Service** | Making service unavailable | API request flooding, DNS attacks | App Servers, APIs | Medium | High | Auto-scaling, rate limiting, CDN |
| **Elevation of Privilege** | Gaining unauthorized access | Exploiting misconfigured IAM roles | IAM, App Logic | Medium | High | Least privilege, role separation, CSPM tools |

---

## 📝 Notes

- You can expand this table per cloud platform or per service (e.g., S3, EC2, Azure Blob, GKE).
- Risk levels can be replaced with numeric scores if using DREAD.
- Consider linking this with architectural diagrams for context.


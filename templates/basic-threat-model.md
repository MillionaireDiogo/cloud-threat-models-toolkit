# 🛡️ Basic Threat Model Template

This document provides a structured approach to identifying, assessing, and mitigating threats to cloud systems or applications. It can be reused across AWS, Azure, GCP, or hybrid environments.

---

## 1. 🧭 System Overview

- **System Name**:  
- **Description**: *(What the system does, its primary functions)*  
- **Cloud Provider(s)**: AWS / Azure / GCP / Hybrid  
- **Architecture Overview**: *(Brief text + refer to diagram if available)*  
- **Business Objectives**: *(What the system aims to achieve)*

---

## 2. 🔐 Assets to Protect

| Asset | Description | Sensitivity Level (High/Med/Low) |
|-------|-------------|----------------------------------|
| Example: User Credentials | Username, password, MFA tokens | High |
| Example: Cloud Storage | S3 buckets / Blob storage / GCS buckets | High |
| Example: Logs | Application and security logs | Medium |

---

## 3. 👥 Actors and Entry Points

- **Actors**:
  - Internal Users (e.g., Admins, DevOps)
  - External Users (e.g., Customers, Clients)
  - Services (e.g., APIs, Lambda, Functions)
  
- **Entry Points**:
  - Public Web App
  - Mobile API
  - IAM Access via CLI or SDK
  - Admin Portals

---

## 4. 🔐 Trust Boundaries

- **Trust Zones**:
  - Public Internet
  - Application Frontend
  - Backend Services
  - Databases / Storage
  - Cloud Provider Services (e.g., IAM, Key Vault)

- **Boundaries**:
  - Between external user and app (TLS)
  - Between app and database (VNet/Subnet, IAM)
  - Between CI/CD and production (Approval gates)

*Include diagram if available (e.g., `/assets/diagrams/architecture.png`).*

---

## 5. ⚠️ Threat Identification (STRIDE)

| Category | Description | Potential Threats | Targeted Asset | Mitigation |
|----------|-------------|-------------------|----------------|------------|
| Spoofing | Impersonating a user/service | Fake tokens, stolen credentials | User Account | Use MFA, IAM roles |
| Tampering | Altering data or configs | Modified DB records, API abuse | Storage, App DB | Validation, version control |
| Repudiation | Denying actions | No audit trail | Logs, Activity History | Centralized logging |
| Information Disclosure | Unauthorized access | Leaked S3 bucket, eavesdropping | PII, Keys | Encryption, access control |
| Denial of Service | Make service unavailable | API flooding, login abuse | App/API | WAF, rate limiting |
| Elevation of Privilege | Gaining unauthorized access | Privilege escalation | IAM roles, App functions | RBAC, scoped policies |

---

## 6. 📊 Risk Assessment (Optional - DREAD Model)

| Threat | Damage | Reproducibility | Exploitability | Affected Users | Discoverability | Risk Score |
|--------|--------|------------------|----------------|----------------|------------------|------------|
| Info Disclosure via Public Bucket | 9 | 9 | 8 | 10 | 7 | 43 |
| DoS via Login Abuse | 6 | 7 | 9 | 8 | 6 | 36 |

---

## 7. 🛡️ Mitigations & Controls

- **Authentication**: MFA, token expiration
- **Authorization**: RBAC, scoped permissions
- **Encryption**: In-transit (TLS), At-rest (KMS)
- **Monitoring**: Centralized logs, alerting, anomaly detection
- **DevSecOps**: Pre-commit hooks, IaC scanning
- **Incident Response**: Playbooks, IR team readiness

---

## 8. 📌 Assumptions

- IAM policies are properly scoped.
- All traffic is encrypted with TLS 1.2+.
- Developers follow secure coding practices.
- No insider threat from privileged roles.

---

## 9. ❗ Open Issues or Future Concerns

- Penetration testing not yet performed.
- No backup strategy for secrets manager.
- High availability for the backend not configured.

---

> 📁 **Usage**: Copy this file into your project directory (`/aws`, `/azure`, or `/gcp`) and update the values accordingly.


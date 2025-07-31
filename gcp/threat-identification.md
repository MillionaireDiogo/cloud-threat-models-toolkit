# ☁️ GCP Threat Identification

This document outlines potential threats to the GCP-deployed system across various components and trust boundaries, categorized using the STRIDE model.

---

## 💻 Web Application

| STRIDE Category | Threat Example |
|----------------|----------------|
| Spoofing        | Forged identity tokens bypassing weak auth on the frontend |
| Tampering       | Manipulation of request payloads to access unauthorized resources |
| Repudiation     | Lack of audit logs for user activity on frontend services |
| Information Disclosure | Insecure error messages leaking stack traces |
| Denial of Service | Bot traffic overwhelming Cloud Run services |
| Elevation of Privilege | Bypassing role-based restrictions due to misconfigured IAM policies |

---

## 📡 APIs and Microservices

| STRIDE Category | Threat Example |
|----------------|----------------|
| Spoofing        | Services calling APIs without verified identities |
| Tampering       | Payload injection in inter-service calls |
| Repudiation     | Missing correlation IDs to trace service-to-service calls |
| Information Disclosure | Sensitive data exposed via unsecured Pub/Sub topics |
| Denial of Service | Flooding endpoints causing Cloud Function throttling |
| Elevation of Privilege | Over-permissioned Cloud Run services accessing sensitive resources |

---

## 🛢️ Data Storage

| STRIDE Category | Threat Example |
|----------------|----------------|
| Spoofing        | Compromised service account accessing BigQuery datasets |
| Tampering       | Alteration of stored data in Cloud SQL without detection |
| Repudiation     | Inadequate logging for data changes in Firestore |
| Information Disclosure | Publicly accessible Cloud Storage buckets |
| Denial of Service | Exhausting storage quotas or overwhelming query limits |
| Elevation of Privilege | Weak KMS policies granting broad decryption rights |

---

## 🔐 Identity and Access Management (IAM)

| STRIDE Category | Threat Example |
|----------------|----------------|
| Spoofing        | Stolen credentials or token reuse |
| Tampering       | Overwriting IAM bindings via unauthorized access |
| Repudiation     | IAM changes not tracked with logs |
| Information Disclosure | Overly permissive roles exposing secrets |
| Denial of Service | Lockout from resources due to IAM misconfiguration |
| Elevation of Privilege | Role escalation through misconfigured service account delegation |

---

## ⚙️ CI/CD & DevOps Pipeline

| STRIDE Category | Threat Example |
|----------------|----------------|
| Spoofing        | Unauthorized actor injecting code via compromised Git repo |
| Tampering       | Malicious code deployment through pipeline misconfig |
| Repudiation     | Inability to trace who deployed a change |
| Information Disclosure | Pipeline secrets exposed in environment variables |
| Denial of Service | Failed deployment halting app availability |
| Elevation of Privilege | Build service account with excessive deployment rights |

---

## 🔗 Third-Party Services

| STRIDE Category | Threat Example |
|----------------|----------------|
| Spoofing        | Forged callback requests from unauthenticated third parties |
| Tampering       | Data tampering in analytics scripts |
| Repudiation     | Lack of logs for third-party interactions |
| Information Disclosure | Third-party SDK leaking user data |
| Denial of Service | Webhooks abused to overload APIs |
| Elevation of Privilege | Improper access scopes granted to OAuth integrations |

---

> 📌 Threat identification helps guide your risk assessment and mitigation strategies. Always re-evaluate as your architecture evolves.

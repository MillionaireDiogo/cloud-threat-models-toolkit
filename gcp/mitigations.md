# ✅ GCP Mitigations

This document outlines recommended mitigations for the identified risks in the GCP environment. Each mitigation is mapped to its corresponding threat.

---

## 💻 Web Application Threats

| Threat | Mitigation |
|--------|------------|
| Forged identity tokens | Use signed and time-bound identity tokens with audience restrictions. Validate tokens on every request. |
| Insecure error messages | Avoid verbose error output. Return generic messages to users and detailed logs to Stackdriver. |
| DDoS via bot traffic | Use Cloud Armor and reCAPTCHA Enterprise to throttle and block unwanted traffic. |
| Misconfigured RBAC | Implement IAM least privilege model and regularly audit permissions. |

---

## 📡 API & Microservices Threats

| Threat | Mitigation |
|--------|------------|
| Payload injection | Use strong input validation, JSON schema enforcement, and Cloud Endpoints with authentication. |
| Unsecured Pub/Sub topics | Restrict publish/subscribe rights via IAM. Use VPC Service Controls for sensitive topics. |
| Missing service traceability | Enforce Stackdriver tracing and logging in all microservices. Use consistent request IDs. |

---

## 🛢️ Data Storage Threats

| Threat | Mitigation |
|--------|------------|
| Public Cloud Storage buckets | Enable bucket-level permissions with uniform access control. Periodic scans for public access. |
| Weak KMS policies | Use customer-managed encryption keys (CMEK) with tight IAM policies. Rotate keys periodically. |
| Inadequate change logging | Enable Audit Logs for all resource types. Stream logs to a central SIEM for review. |

---

## 🔐 IAM Threats

| Threat | Mitigation |
|--------|------------|
| Token reuse | Implement token expiration, rotation, and audience restriction. Monitor for suspicious reuse. |
| Over-permissive roles | Replace primitive roles with custom roles. Use Policy Analyzer to identify and reduce excessive access. |
| Missing audit logs | Enable Admin Activity and Data Access logs for all services. Archive to GCS with retention policies. |

---

## ⚙️ CI/CD Pipeline Threats

| Threat | Mitigation |
|--------|------------|
| Malicious code via Git | Enforce code reviews, branch protections, and static analysis (SAST) via Cloud Build triggers. |
| Leaked pipeline secrets | Store secrets in Secret Manager. Avoid embedding in source code. Audit access to secrets. |
| Build account overreach | Create dedicated least-privilege service accounts for builds. Restrict Cloud Build scopes. |

---

## 🔗 Third-Party Service Threats

| Threat | Mitigation |
|--------|------------|
| Forged third-party callbacks | Validate webhook signatures using HMAC. Use IP allowlists where possible. |
| OAuth over-permission | Use scopes that grant minimal required access. Regularly review third-party access in the admin console. |

---

> 🔒 Apply mitigations alongside continuous monitoring and periodic security reviews to maintain a strong security posture.


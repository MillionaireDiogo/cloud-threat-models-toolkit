# 🔎 GCP Risk Assessment

This document prioritizes identified threats based on **likelihood** and **impact**, using a qualitative risk matrix to guide mitigation efforts.

---

## 🎯 Risk Scoring Method

| Risk Level | Description |
|------------|-------------|
| High       | High likelihood & high impact – requires immediate mitigation |
| Medium     | Either high likelihood or high impact – needs planned action |
| Low        | Low likelihood & low impact – monitor periodically |

---

## 💻 Web Application Risks

| Threat | Likelihood | Impact | Risk Level |
|--------|------------|--------|------------|
| Forged identity tokens | Medium | High | **High** |
| Insecure error messages | High | Medium | **Medium** |
| DDoS via bot traffic | High | High | **High** |
| Misconfigured RBAC | Medium | High | **High** |

---

## 📡 API & Microservices Risks

| Threat | Likelihood | Impact | Risk Level |
|--------|------------|--------|------------|
| Payload injection | Medium | High | **High** |
| Unsecured Pub/Sub topics | Medium | High | **High** |
| Missing service traceability | Medium | Medium | **Medium** |

---

## 🛢️ Data Storage Risks

| Threat | Likelihood | Impact | Risk Level |
|--------|------------|--------|------------|
| Public Cloud Storage buckets | High | High | **High** |
| Weak KMS policies | Medium | High | **High** |
| Inadequate change logging | Low | Medium | **Low** |

---

## 🔐 IAM Risks

| Threat | Likelihood | Impact | Risk Level |
|--------|------------|--------|------------|
| Token reuse | Medium | High | **High** |
| Over-permissive roles | High | High | **High** |
| Missing audit logs | Medium | Medium | **Medium** |

---

## ⚙️ CI/CD Pipeline Risks

| Threat | Likelihood | Impact | Risk Level |
|--------|------------|--------|------------|
| Malicious code via Git | Medium | High | **High** |
| Leaked pipeline secrets | High | High | **High** |
| Build account overreach | Medium | Medium | **Medium** |

---

## 🔗 Third-Party Service Risks

| Threat | Likelihood | Impact | Risk Level |
|--------|------------|--------|------------|
| Forged third-party callbacks | Medium | Medium | **Medium** |
| OAuth over-permission | Medium | High | **High** |

---

> ✅ Prioritize mitigation based on **High** risks first, then **Medium**, while documenting and monitoring **Low** risks.

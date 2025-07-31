# 🔍 Assumptions – Google Cloud Platform (GCP)

This document captures the foundational assumptions that underpin the threat model for systems deployed on GCP. These assumptions define the boundaries of analysis and help ensure clarity when evaluating risks and controls.

---

## 🧱 System Architecture Assumptions

- The application is deployed using Google Kubernetes Engine (GKE) and App Engine.
- All microservices communicate over HTTPS within a private VPC network.
- Data is stored using Cloud SQL, Firestore, and Cloud Storage with CMEK (Customer-Managed Encryption Keys).
- APIs are exposed via Cloud Endpoints or API Gateway with authentication enabled.

---

## 👥 Identity and Access Assumptions

- IAM roles are defined using the principle of least privilege.
- Service accounts are used for inter-service communication with scoped permissions.
- Multi-Factor Authentication (MFA) is enforced for all user accounts accessing the GCP Console.
- All OAuth2 credentials are securely managed using Secret Manager.

---

## 🔐 Security Control Assumptions

- Cloud Audit Logs are enabled for all services.
- VPC Service Controls are used to enforce data exfiltration boundaries.
- Cloud Armor and Identity-Aware Proxy (IAP) are enabled for public-facing applications.
- All GCP resources are deployed using Infrastructure as Code (IaC) with change control in place.

---

## 🔧 Operational Assumptions

- All secrets are stored in Secret Manager, not in environment variables or code.
- All changes to infrastructure and application code go through code review and automated CI/CD pipelines.
- Monitoring and alerting are configured via Cloud Monitoring, with logs aggregated in Cloud Logging.
- Incident response runbooks are defined and tested periodically.

---

## 📦 Third-Party Integration Assumptions

- Webhooks and external APIs validate request signatures and enforce strict scopes.
- External services integrated with the application follow HTTPS and provide SLAs.
- No critical workload depends on unmanaged or undocumented third-party components.

---

> ✅ These assumptions must be reviewed periodically to ensure they remain valid and reflective of the actual environment. If any assumption is violated, the threat model should be updated accordingly.

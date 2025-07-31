# 🌐 System Overview – Google Cloud Platform (GCP)

This document provides a high-level overview of the system architecture deployed on Google Cloud Platform (GCP), highlighting the core components, integrations, and services in use.

---

## 🧭 Architecture Summary

The GCP infrastructure under review includes the following architectural layers:

- **Frontend Layer**: Hosted on Google Cloud Storage (GCS) with HTTPS via Cloud CDN and Cloud Load Balancing.
- **Backend Layer**: Composed of stateless APIs and microservices running on Google Kubernetes Engine (GKE) and Cloud Functions.
- **Data Layer**: Data is stored in Google Cloud SQL, BigQuery, and Cloud Storage buckets.
- **Messaging Layer**: Asynchronous communication handled via Pub/Sub.
- **Monitoring & Logging**: Centralized via Cloud Monitoring, Logging, and Security Command Center.
- **Identity & Access Management**: Handled through Google Cloud IAM and organization policies.
- **Networking**: Managed via VPC networks, subnets, firewall rules, and Cloud Armor.

---

## 🧱 Core Services in Use

| Layer            | GCP Service(s) Used                    |
|------------------|----------------------------------------|
| Compute          | GKE, Cloud Functions, App Engine       |
| Storage          | Cloud Storage, Cloud SQL, BigQuery     |
| Networking       | VPC, Load Balancer, Cloud NAT, Cloud Armor |
| Identity         | Cloud IAM, Workload Identity, Org Policies |
| Observability    | Cloud Logging, Cloud Monitoring, SCC   |
| Messaging        | Pub/Sub                                |

---

## 🔗 Integrations & Dependencies

- **Third-party APIs** for payment processing and analytics
- **GitHub Actions / Cloud Build** for CI/CD
- **IAM federated identity** with external IdPs (e.g., Okta, Azure AD)
- **Secrets Management** via Secret Manager

---

## 🔒 Security Posture

- Least privilege principle enforced with IAM roles
- Workload Identity used to avoid hardcoded credentials
- All traffic encrypted in transit and at rest
- Network segmentation using private VPCs and subnets

---

## 🎯 Threat Modeling Scope

This model focuses on analyzing threats across the following domains:

- Authentication & Authorization
- Data Security
- Network Security
- Compute Environment Isolation
- Supply Chain & CI/CD Pipeline
- Logging, Monitoring & Incident Response

---

> ⚠️ **Note:** Architecture may vary depending on the organization’s GCP environment. Adjust components and scope accordingly.

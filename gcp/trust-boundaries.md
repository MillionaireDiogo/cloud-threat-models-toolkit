# 🛡️ Trust Boundaries in GCP Architecture

This document outlines the trust boundaries within the system deployed on Google Cloud Platform (GCP). Trust boundaries define where different levels of trust are established, often requiring stricter access control and monitoring.

---

## 🌍 External User Boundary

**Description:**  
Untrusted boundary where anonymous or authenticated users interact with public-facing applications.

**Entry Points:**  
- Web Application via HTTPS (Load Balancer)
- Mobile App API Calls

**Controls:**  
- HTTPS encryption
- OAuth 2.0 / Firebase Authentication
- Rate Limiting & Cloud Armor WAF

---

## 🌐 GCP Network Boundary

**Description:**  
Represents the entry point into the GCP-managed network infrastructure (Virtual Private Cloud).

**Entry Points:**  
- Load Balancer to Backend Services
- Public IP to NAT-enabled services

**Controls:**  
- Firewall Rules
- VPC Peering & Private Google Access
- Identity-Aware Proxy (IAP) for internal services

---

## 🧠 Application Trust Boundary

**Description:**  
Boundary between frontend and backend microservices within GCP infrastructure.

**Entry Points:**  
- Cloud Run / GKE Services calling each other
- Pub/Sub triggers and Cloud Functions

**Controls:**  
- mTLS (Mutual TLS) between services
- IAM-based Workload Identity
- Pub/Sub message validation

---

## 💾 Data Trust Boundary

**Description:**  
Boundary around data storage systems where sensitive data is stored or processed.

**Entry Points:**  
- App Engine, Cloud Functions writing to Cloud SQL / BigQuery
- Services reading secrets from Secret Manager

**Controls:**  
- Data Encryption at Rest and in Transit
- IAM Roles with least privilege
- CMEK (Customer-Managed Encryption Keys)

---

## 👩‍💼 Admin and DevOps Boundary

**Description:**  
Boundary where administrators and DevOps teams interact with the system.

**Entry Points:**  
- GCP Console
- gcloud CLI / Terraform / CI-CD Pipelines

**Controls:**  
- Two-Factor Authentication (2FA)
- Role-Based Access Control (RBAC)
- Audit Logging (Cloud Audit Logs)
- Just-in-Time (JIT) Access or Privileged Access Management (PAM)

---

## 🤝 Third-Party Integration Boundary

**Description:**  
Boundary for external service providers such as payment processors, identity providers, or analytics platforms.

**Entry Points:**  
- Outbound HTTP(S) API

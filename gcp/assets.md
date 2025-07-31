# 📦 GCP Assets Inventory

This document outlines the assets involved in the system deployed on Google Cloud Platform (GCP), categorized by type. These assets are the focus of the threat model and must be protected according to their sensitivity and business impact.

---

## 🖥️ Compute Assets

| Asset Name              | Description                                      | Sensitivity |
|-------------------------|--------------------------------------------------|-------------|
| Google Kubernetes Engine (GKE) | Hosts backend services and APIs                | High        |
| Cloud Functions         | Event-driven microservices for async tasks      | Medium      |
| App Engine              | Hosts web applications                          | Medium      |

---

## 📂 Storage Assets

| Asset Name        | Description                                  | Sensitivity |
|-------------------|----------------------------------------------|-------------|
| Cloud Storage     | Stores static content, logs, and backups     | High        |
| Cloud SQL         | Relational data store (user data, metadata)  | High        |
| BigQuery          | Analytical workloads and processed datasets  | Medium      |
| Secret Manager    | Stores secrets, API keys, and credentials    | Critical    |

---

## 🌐 Networking Assets

| Asset Name       | Description                                             | Sensitivity |
|------------------|---------------------------------------------------------|-------------|
| VPC Networks     | Isolated network segments for services                 | High        |
| Load Balancers   | Expose applications to the internet/internal users     | High        |
| Cloud Armor      | Web application firewall for DDoS protection           | Medium      |
| Cloud NAT        | Enables outbound internet access from private subnets  | Medium      |

---

## 🛡️ Identity and Access Assets

| Asset Name             | Description                                      | Sensitivity |
|------------------------|--------------------------------------------------|-------------|
| IAM Roles & Policies   | Access control to GCP resources                  | Critical    |
| Workload Identity      | Associates GKE workloads with IAM identities     | High        |
| Service Accounts       | Used by services and automation pipelines        | High        |

---

## 📊 Observability & Management Assets

| Asset Name             | Description                                     | Sensitivity |
|------------------------|-------------------------------------------------|-------------|
| Cloud Monitoring       | Metrics collection for infrastructure and apps | Medium      |
| Cloud Logging          | Centralized logging for all services           | High        |
| Security Command Center| Central hub for security alerts and insights   | Critical    |

---

## 🔗 External Dependencies

| Asset Name       | Description                                      | Sensitivity |
|------------------|--------------------------------------------------|-------------|
| Third-party APIs | Payment gateways, analytics, email services     | Medium      |
| GitHub / GitLab  | CI/CD source code and workflow pipelines        | Critical    |
| Identity Providers| External IdPs like Okta or Azure AD             | High        |

---

> 🛠️ **Note:** All assets should have proper classification and ownership for better accountability and risk assessment.

# ⚠️ Open Issues – Google Cloud Platform (GCP)

This document lists unresolved or partially resolved issues discovered during the threat modeling process. These items require follow-up analysis, review, or mitigation planning.

---

## 🚨 Security Concerns Needing Further Review

1. **Overprivileged Service Accounts**
   - *Description*: Several service accounts currently use `Editor` role.
   - *Risk*: Increases blast radius in case of compromise.
   - *Action*: Conduct a role audit and enforce least privilege.

2. **Lack of Consistent Egress Controls**
   - *Description*: Some workloads allow unrestricted egress to the internet.
   - *Risk*: Potential data exfiltration.
   - *Action*: Evaluate VPC Service Controls and firewall egress rules.

3. **Cloud SQL Lacks Automated Failover in Some Regions**
   - *Description*: Some Cloud SQL instances lack High Availability (HA) configuration.
   - *Risk*: Possible data loss or downtime in the event of a regional failure.
   - *Action*: Implement HA for all production databases.

---

## 🧪 Unverified Assumptions

4. **IAM Audit Logs Coverage**
   - *Description*: Unclear if all projects and services have `Admin Activity` and `Data Access` logs enabled.
   - *Risk*: Gaps in visibility for forensic analysis.
   - *Action*: Conduct a log coverage assessment and enforce org policy.

5. **Legacy APIs Still Enabled**
   - *Description*: Some legacy GCP APIs are enabled but unused.
   - *Risk*: Increases attack surface unnecessarily.
   - *Action*: Inventory all APIs and disable unused ones.

6. **Insufficient Rate Limiting on Cloud Functions**
   - *Description*: Certain public Cloud Functions lack defined quotas.
   - *Risk*: Susceptible to abuse or denial-of-service (DoS).
   - *Action*: Implement quotas and usage monitoring.

---

## ⏳ Pending Dependencies

7. **Third-Party Audit Reports**
   - *Description*: Awaiting SOC 2 or ISO 27001 reports from integrated SaaS providers.
   - *Risk*: Blind trust in vendor controls.
   - *Action*: Follow up with vendors and validate compliance.

8. **Security Testing for New Workloads**
   - *Description*: Several new microservices have not undergone penetration testing or threat modeling.
   - *Risk*: Unidentified vulnerabilities in production.
   - *Action*: Schedule security review and update threat models accordingly.

---

> 📌 All open issues should be tracked in the central security backlog and prioritized based on impact and exploitability.

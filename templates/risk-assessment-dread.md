# 📊 DREAD Risk Assessment Template

The **DREAD** model helps prioritize threats based on five key factors:

- **D**amage Potential – How severe is the impact?
- **R**eproducibility – How easily can the attack be repeated?
- **E**xploitability – How easy is it to launch the attack?
- **A**ffected Users – How many users would be impacted?
- **D**iscoverability – How easy is it to discover the vulnerability?

Each factor is scored from **1 (low)** to **10 (high)**. The total gives a **risk score (out of 50)**.

---

## 🧮 DREAD Risk Table

| Threat Scenario | Damage | Reproducibility | Exploitability | Affected Users | Discoverability | Total Score | Risk Level |
|------------------|--------|------------------|----------------|----------------|------------------|-------------|------------|
| Publicly exposed S3 bucket with PII | 9 | 9 | 8 | 10 | 7 | 43 | High |
| Misconfigured IAM role allows privilege escalation | 8 | 8 | 7 | 9 | 6 | 38 | High |
| DoS via unauthenticated API abuse | 6 | 7 | 8 | 8 | 6 | 35 | Medium |
| Error messages disclose internal stack traces | 4 | 6 | 6 | 5 | 8 | 29 | Medium |
| Lack of audit logs for critical actions | 5 | 5 | 4 | 6 | 4 | 24 | Low |

---

## 🧠 Interpretation Guidelines

- **40–50** → 🔴 High Risk – Immediate remediation
- **30–39** → 🟠 Medium Risk – Remediate soon
- **0–29** → 🟢 Low Risk – Monitor or document

---

## 🔧 Usage Tips

- Update this table per cloud service or threat modeling scope (e.g., per AWS Lambda function or GCP App Engine).
- Track historical risk scores to measure improvement over time.
- You can automate parts of DREAD scoring using CSPM tools and CI/CD security gates.


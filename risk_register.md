# Risk Register — NIST Compliance Gap Analysis

**Organization:** Retail Financial Services Organization (Simulated)  
**Register Owner:** Shreya Anil, GRC Analyst  
**Last Updated:** Q1 2025  
**Framework Alignment:** NIST CSF 1.1 | ISO 27001:2022  

---

## Risk Scoring Matrix

| Likelihood / Impact | 1 Negligible | 2 Minor | 3 Moderate | 4 Major | 5 Critical |
|---|---|---|---|---|---|
| 5 Almost Certain | 5 | 10 | 15 | 20 | 25 |
| 4 Likely | 4 | 8 | 12 | 16 | 20 |
| 3 Possible | 3 | 6 | 9 | 12 | 15 |
| 2 Unlikely | 2 | 4 | 6 | 8 | 10 |
| 1 Rare | 1 | 2 | 3 | 4 | 5 |

| Score | Rating |
|---|---|
| 1–4 | 🟢 Low |
| 5–9 | 🟡 Medium |
| 10–16 | 🟠 High |
| 17–25 | 🔴 Critical |

---

## RISK-001 — Incomplete MFA Deployment

| Field | Detail |
|---|---|
| **Risk ID** | RISK-001 |
| **Category** | Access Control |
| **NIST CSF Mapping** | PR.AC-7 |
| **ISO 27001 Mapping** | A.9.4.2 |
| **Threat** | Credential theft, account takeover via phishing or brute force |
| **Vulnerability** | 38% of privileged accounts lack MFA enforcement |
| **Current Control** | MFA deployed on 62% of privileged accounts via Azure AD |
| **Likelihood** | 4 — Likely |
| **Impact** | 5 — Critical |
| **Inherent Risk Score** | **20 — 🔴 Critical** |
| **Residual Risk (post-mitigation)** | 8 — 🟡 Medium |
| **Risk Owner** | IT Security Manager |

**Mitigation Steps:**
1. Audit all privileged accounts in Azure AD
2. Enforce Conditional Access policies requiring MFA for all admin roles
3. Address legacy system compatibility via ADFS integration
4. Complete rollout within 30 days

---

## RISK-002 — No Automated Asset Inventory

| Field | Detail |
|---|---|
| **Risk ID** | RISK-002 |
| **Category** | Asset Management |
| **NIST CSF Mapping** | ID.AM-1, ID.AM-2 |
| **ISO 27001 Mapping** | A.8.1.1 |
| **Threat** | Unknown devices as attack entry points; shadow IT |
| **Vulnerability** | 40% of endpoints undocumented; no CMDB; 3 shadow SaaS apps found |
| **Current Control** | Manual Excel spreadsheet updated ad hoc |
| **Likelihood** | 4 — Likely |
| **Impact** | 4 — Major |
| **Inherent Risk Score** | **16 — 🟠 High** |
| **Residual Risk (post-mitigation)** | 6 — 🟡 Medium |
| **Risk Owner** | IT Operations Manager |

**Mitigation Steps:**
1. Evaluate and procure automated asset discovery tool (Qualys or Axonius)
2. Integrate with ServiceNow CMDB
3. Conduct full asset reconciliation within 60 days
4. Establish quarterly asset audit process

---

## RISK-003 — SIEM Alert Fatigue

| Field | Detail |
|---|---|
| **Risk ID** | RISK-003 |
| **Category** | Security Monitoring |
| **NIST CSF Mapping** | DE.AE-2, DE.AE-5, DE.CM-1 |
| **ISO 27001 Mapping** | A.12.4.1 |
| **Threat** | Real security events missed due to alert noise |
| **Vulnerability** | 3,200+ false positive alerts per week; default Splunk rules untuned |
| **Current Control** | Splunk deployed with default correlation rules |
| **Likelihood** | 5 — Almost Certain |
| **Impact** | 4 — Major |
| **Inherent Risk Score** | **20 — 🔴 Critical** |
| **Residual Risk (post-mitigation)** | 8 — 🟡 Medium |
| **Risk Owner** | SOC Lead |

**Mitigation Steps:**
1. Audit Splunk correlation rules; suppress known-benign patterns
2. Implement alert triage SLA (P1: 15 min, P2: 1 hr, P3: 4 hrs)
3. Onboard remaining 60% of log sources
4. Target 70% false positive reduction within 90 days

---

## RISK-004 — Outdated Incident Response Plan

| Field | Detail |
|---|---|
| **Risk ID** | RISK-004 |
| **Category** | Incident Response |
| **NIST CSF Mapping** | RS.RP-1, RS.IM-1, RS.IM-2 |
| **ISO 27001 Mapping** | A.16.1.1 |
| **Threat** | Uncoordinated, prolonged incident response; regulatory penalties post-breach |
| **Vulnerability** | IRP last updated 2021; references obsolete roles and tools |
| **Current Control** | IRP document exists but untested |
| **Likelihood** | 4 — Likely |
| **Impact** | 5 — Critical |
| **Inherent Risk Score** | **20 — 🔴 Critical** |
| **Residual Risk (post-mitigation)** | 8 — 🟡 Medium |
| **Risk Owner** | CISO / GRC Team |

**Mitigation Steps:**
1. Update IRP against NIST SP 800-61r2 within 45 days
2. Update all contact lists, roles, and tool references
3. Conduct ransomware tabletop exercise within 60 days
4. Establish annual IRP review and biannual tabletop cadence

---

## RISK-005 — No Defined RTO/RPO; Untested Backups

| Field | Detail |
|---|---|
| **Risk ID** | RISK-005 |
| **Category** | Business Continuity |
| **NIST CSF Mapping** | RC.RP-1, RC.IM-1 |
| **ISO 27001 Mapping** | A.17.1.1 |
| **Threat** | Ex

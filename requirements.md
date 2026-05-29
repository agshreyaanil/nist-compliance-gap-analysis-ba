# Compliance Requirements Document

**Organization:** Retail Financial Services Organization (Simulated)  
**Document Owner:** Shreya Anil, GRC Analyst  
**Version:** 1.0  
**Date:** Q1 2025  

---

## 1. Purpose

This document traces compliance requirements applicable to the organization's information security program. It maps regulatory obligations to internal controls, identifies ownership, and tracks implementation status to support audit readiness.

---

## 2. Regulatory Scope

| Framework / Regulation | Applicability | Reason |
|---|---|---|
| NIST CSF 1.1 | ✅ In Scope | Primary cybersecurity framework |
| ISO 27001:2022 | ✅ In Scope | Target certification standard |
| PCI-DSS v4.0 | ✅ In Scope | Payment card data processing |
| GLBA | ✅ In Scope | Financial data protection |
| SOC 2 Type II | ✅ In Scope | Customer trust / third-party assurance |
| CCPA | 🟡 Partial | Applicable to California-resident data |

---

## 3. Requirements Traceability Matrix

### 3.1 Access Control

| Req ID | Requirement | Source | NIST Mapping | Status | Evidence Needed |
|---|---|---|---|---|---|
| REQ-AC-001 | All privileged accounts must use MFA | PCI-DSS §8.4.2 | PR.AC-7 | 🟡 In Progress | Azure AD MFA logs |
| REQ-AC-002 | User access reviews conducted quarterly | ISO 27001 / SOC 2 | PR.AC-4 | 🔴 Not Started | Access review schedule |
| REQ-AC-003 | Principle of least privilege enforced | PCI-DSS §7.2 | PR.PT-3 | 🟡 In Progress | AD group policy audit |
| REQ-AC-004 | Stale accounts disabled within 30 days of departure | GLBA / SOC 2 | PR.AC-1 | 🔴 Not Started | Offboarding checklist |
| REQ-AC-005 | Remote access via approved encrypted VPN only | PCI-DSS §8.6 | PR.AC-3 | 🟢 Compliant | VPN policy; deployment docs |

---

### 3.2 Data Security

| Req ID | Requirement | Source | NIST Mapping | Status | Evidence Needed |
|---|---|---|---|---|---|
| REQ-DS-001 | Cardholder data encrypted at rest (AES-256) | PCI-DSS §3.5 | PR.DS-1 | 🟡 In Progress | Database encryption audit |
| REQ-DS-002 | All data in transit encrypted (TLS 1.2+) | PCI-DSS §4.2.1 | PR.DS-2 | 🟡 In Progress | TLS scan results |
| REQ-DS-003 | Data classification policy defined | ISO 27001 | ID.AM-5 | 🔴 Not Started | Classification policy doc |
| REQ-DS-004 | DLP controls prevent unauthorized exfiltration | SOC 2 CC6.7 | PR.DS-5 | 🔴 Not Started | DLP deployment records |
| REQ-DS-005 | Backup data encrypted and tested quarterly | PCI-DSS §9.4.2 | RC.RP-1 | 🟡 In Progress | Last restoration test date |

---

### 3.3 Security Monitoring & Logging

| Req ID | Requirement | Source | NIST Mapping | Status | Evidence Needed |
|---|---|---|---|---|---|
| REQ-LG-001 | Audit logs retained for 12 months minimum | PCI-DSS §10.7 | PR.PT-1 | 🔴 Not Compliant | Splunk retention config |
| REQ-LG-002 | All critical systems onboarded to SIEM | PCI-DSS §10.1 | DE.CM-1 | 🔴 Not Compliant | Splunk data source inventory |
| REQ-LG-003 | SIEM critical alerts responded to within 1 hour | SOC 2 CC7.4 | DE.AE-2 | 🔴 Not Started | Alert SLA policy |
| REQ-LG-004 | Unauthorized access attempts logged and alerted | PCI-DSS §10.2.4 | DE.CM-3 | 🟡 In Progress | Splunk failed login alerts |
| REQ-LG-005 | Tamper-evident logging controls in place | PCI-DSS §10.3 | PR.PT-1 | 🔴 Not Started | Log integrity config |

---

### 3.4 Vulnerability Management

| Req ID | Requirement | Source | NIST Mapping | Status | Evidence Needed |
|---|---|---|---|---|---|
| REQ-VM-001 | Internal vulnerability scans quarterly | PCI-DSS §11.3.1 | ID.RA-1 | 🟡 In Progress | Nessus scan schedule |
| REQ-VM-002 | External ASV scans quarterly | PCI-DSS §11.3.2 | ID.RA-1 | 🟢 Compliant | ASV scan certificates |
| REQ-VM-003 | Critical vulnerabilities patched within 30 days | PCI-DSS §6.3.3 | RS.MI-3 | 🟡 In Progress | Patch management SLA |
| REQ-VM-004 | Penetration test conducted annually | PCI-DSS §11.4 | ID.RA-1 | 🟢 Compliant | Pentest report Q4 2024 |

---

### 3.5 Incident Response

| Req ID | Requirement | Source | NIST Mapping | Status | Evidence Needed |
|---|---|---|---|---|---|
| REQ-IR-001 | Incident Response Plan reviewed annually | PCI-DSS §12.10 | RS.RP-1 | 🔴 Not Compliant | IRP document (2021) |
| REQ-IR-002 | IR tabletop exercise conducted annually | PCI-DSS §12.10.6 | RS.RP-1 | 🔴 Not Compliant | No tabletop in 3+ years |
| REQ-IR-003 | Incidents reported within required timeframes | GLBA / State laws | RS.CO-2 | 🟡 In Progress | Breach notification policy |
| REQ-IR-004 | Post-incident review for all P1/P2 incidents | SOC 2 CC7.5 | RS.IM-1 | 🔴 Not Started | Post-incident review template |

---

### 3.6 Business Continuity

| Req ID | Requirement | Source | NIST Mapping | Status | Evidence Needed |
|---|---|---|---|---|---|
| REQ-BC-001 | BCP documented and reviewed annually | ISO 27001 | RC.RP-1 | 🟡 In Progress | BCP document |
| REQ-BC-002 | RTO and RPO defined for Tier 1 systems | SOC 2 A1.2 | RC.RP-1 | 🔴 Not Started | RTO/RPO register |
| REQ-BC-003 | DR test conducted annually | SOC 2 A1.3 | RC.IM-1 | 🔴 Not Compliant | Last DR test 4+ years ago |
| REQ-BC-004 | Backup restoration tested quarterly | PCI-DSS §12.3 | RC.RP-1 | 🟡 In Progress | Backup restoration log |

---

## 4. Compliance Status Summary

| Domain | Total | 🟢 Compliant | 🟡 In Progress | 🔴 Not Compliant |
|---|---|---|---|---|
| Access Control | 5 | 1 | 3 | 1 |
| Data Security | 5 | 0 | 3 | 2 |
| Monitoring & Logging | 5 | 0 | 2 | 3 |
| Vulnerability Management | 4 | 2 | 2 | 0 |
| Incident Response | 4 | 0 | 1 | 3 |
| Business Continuity | 4 | 0 | 2 | 2 |
| **Total** | **27** | **3 (11%)** | **13 (48%)** | **11 (41%)** |

---

## 5. Next Steps

1. Assign owners to all Not Compliant requirements immediately
2. Establish monthly compliance review cadence with control owners
3. Target 60% compliance within 6 months; 90% within 12 months
4. Schedule external ISO 27001 assessment for Q4 2025

---

*All data is simulated for portfolio demonstration purposes.*

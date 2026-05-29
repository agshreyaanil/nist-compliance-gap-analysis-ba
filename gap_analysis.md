# NIST CSF Gap Analysis Report

**Organization:** Retail Financial Services Organization (Simulated)  
**Assessment Date:** Q1 2025  
**Analyst:** Shreya Anil, GRC Analyst  
**Framework:** NIST Cybersecurity Framework (CSF) 1.1  

---

## Overall Maturity Scores

| NIST CSF Function | Maturity Score (1–5) | Gap Severity |
|---|---|---|
| Identify | 2.4 | 🔴 High |
| Protect | 3.1 | 🟡 Medium |
| Detect | 2.0 | 🔴 High |
| Respond | 1.8 | 🔴 High |
| Recover | 2.2 | 🔴 High |
| **Overall** | **2.3** | **🔴 High** |

---

## IDENTIFY (ID) — Score: 2.4 🔴

| Control | Current State | Gap | Severity |
|---|---|---|---|
| ID.AM-1: Physical asset inventory | 60% documented in spreadsheet | No automated discovery; 40% undocumented | 🔴 High |
| ID.AM-2: Software inventory | Informal list by IT | No CMDB; shadow IT in use | 🔴 High |
| ID.AM-3: Data flows mapped | Not completed | No data flow diagrams exist | 🔴 High |
| ID.GV-1: Security policy | Policy exists (last updated 2021) | Not reviewed in 3+ years | 🟡 Medium |
| ID.RA-2: Threat intelligence | No formal feed | No CTI subscription or ISAC membership | 🔴 High |

**Key Finding:** The organization relies on a manually updated Excel spreadsheet for asset tracking, last updated 5 months ago. Three cloud SaaS applications were discovered during interviews that are not in any inventory.

**Recommendations:**
- Deploy automated asset discovery (Qualys or Tenable) integrated with ServiceNow CMDB
- Establish a data classification policy
- Join FS-ISAC for financial sector threat intelligence

---

## PROTECT (PR) — Score: 3.1 🟡

| Control | Current State | Gap | Severity |
|---|---|---|---|
| PR.AC-7: MFA enforcement | MFA on 62% of privileged accounts | 38% of privileged accounts lack MFA | 🔴 High |
| PR.DS-2: Data-in-transit encryption | TLS 1.2 on web apps only | Internal server-to-server traffic unencrypted | 🔴 High |
| PR.DS-5: DLP controls | No DLP solution deployed | No egress monitoring or content inspection | 🔴 High |
| PR.PT-1: Audit log retention | 30-day Splunk retention | PCI-DSS requires 12 months | 🔴 High |
| PR.PT-4: Network segmentation | Firewall in place | No PCI vs. non-PCI zone segmentation | 🔴 High |

**Key Finding:** MFA is only enforced on 62% of privileged accounts due to legacy system compatibility issues with Azure AD Conditional Access policies.

**Recommendations:**
- Enforce MFA via Azure AD Conditional Access for all privileged roles
- Extend Splunk log retention to 12 months
- Implement network segmentation between PCI and non-PCI zones

---

## DETECT (DE) — Score: 2.0 🔴

| Control | Current State | Gap | Severity |
|---|---|---|---|
| DE.AE-2: Event analysis | Splunk alerts reviewed manually | 3,200+ false positives per week | 🔴 High |
| DE.AE-3: Log correlation | Splunk partially configured | Only 40% of log sources onboarded | 🔴 High |
| DE.CM-1: Network monitoring | Perimeter logs only | Internal east-west traffic not monitored | 🔴 High |
| DE.CM-3: Personnel activity | Basic AD logging | No UBA/UEBA solution deployed | 🔴 High |
| DE.DP-1: Detection roles defined | Informal | No detection playbooks exist | 🔴 High |

**Key Finding:** Splunk is generating 3,200+ false positive alerts per week due to untuned default correlation rules, causing alert fatigue and masking real threats.

**Recommendations:**
- Tune Splunk correlation rules; target 70% false positive reduction within 90 days
- Onboard remaining 60% of log sources into Splunk
- Develop detection playbooks by incident type

---

## RESPOND (RS) — Score: 1.8 🔴

| Control | Current State | Gap | Severity |
|---|---|---|---|
| RS.RP-1: Incident Response Plan | IRP exists (last updated 2021) | Not tested; references obsolete roles and tools | 🔴 High |
| RS.CO-2: Internal incident reporting | Ad hoc email | No defined escalation path | 🔴 High |
| RS.AN-4: Incident classification | None | No incident taxonomy defined | 🔴 High |
| RS.MI-1: Incident containment | Ad hoc | No containment playbooks by incident type | 🔴 High |
| RS.IM-1: Lessons learned | Not performed | No post-incident review process | 🔴 High |

**Key Finding:** The Incident Response Plan references roles that no longer exist and tools that have been replaced. No tabletop exercise has been conducted in 3+ years.

**Recommendations:**
- Update IRP against NIST SP 800-61r2 within 45 days
- Conduct ransomware tabletop exercise within 60 days
- Define incident taxonomy and impact classification matrix

---

## RECOVER (RC) — Score: 2.2 🔴

| Control | Current State | Gap | Severity |
|---|---|---|---|
| RC.RP-1: Recovery plan | BCP exists | Not tested; last tabletop 4+ years ago | 🔴 High |
| RC.IM-1: Lessons learned in recovery | Not performed | No BCP update process post-incident | 🔴 High |
| RC.CO-1: Crisis communications | No process | No crisis communications plan | 🟡 Medium |

**Key Finding:** No RTO or RPO has been defined for any critical system. Backups are performed nightly but restoration has not been tested in 18 months.

**Recommendations:**
- Define RTO/RPO for all Tier 1 systems within 30 days
- Conduct backup restoration test immediately
- Schedule annual DR drill and update BCP

---

## Remediation Roadmap

| Priority | Action | Timeline |
|---|---|---|
| 🔴 Immediate | Deploy MFA for all privileged accounts | 0–30 days |
| 🔴 Immediate | Extend Splunk log retention to 12 months | 0–30 days |
| 🔴 Immediate | Define RTO/RPO for Tier 1 systems | 0–30 days |
| 🟠 Short-Term | Tune Splunk correlation rules (70% FP reduction) | 30–90 days |
| 🟠 Short-Term | Update and test Incident Response Plan | 30–90 days |
| 🟠 Short-Term | Deploy automated asset discovery tool | 30–90 days |
| 🟡 Medium-Term | Implement network segmentation (PCI zones) | 90–180 days |
| 🟡 Medium-Term | Deploy DLP solution | 90–180 days |
| 🟡 Medium-Term | Conduct full BCP/DR tabletop exercise | 90–180 days |

---

*Analysis performed using NIST CSF 1.1. All findings are from a simulated environment for portfolio demonstration purposes.*

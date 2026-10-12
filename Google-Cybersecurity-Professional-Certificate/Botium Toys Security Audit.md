# Portfolio Activity: Conduct a Security Audit

**Author:** Kevin Curtis  
**Course:** Google Cybersecurity Professional Certificate - Play it Safe: Managing Security Risks  
**Status:** Graded Assignment (100%)

---

## Overview

**Botium Toys** is a small U.S. business that develops and sells toys. With a growing online presence, their IT department is under pressure to support customers worldwide. The IT manager decides to conduct an internal audit to secure the company's infrastructure, identify risks, and ensure compliance with regulations for online payments and business in the EU. She implements the NIST Cybersecurity Framework, establishes audit scope and goals, lists managed assets, and completes a risk assessment. The audit aims to provide an overview of potential risks or fines due to their current security posture.

---

## Tasks

1. Review Botium Toys' scope, goals, and risk assessment report, focusing on:
   - IT department assets
   - Bullet points under "Additional comments" in the Risk assessment section
   - Information from the Controls Categories document for your review
2. Review the Controls and Compliance Checklist and evaluate controls as currently in place (`Yes` / `No`).

---

## Controls and Compliance Checklist

### Internal Security Controls

| Control | Yes | No |
| :--- | :---: | :---: |
| **Least Privilege** | | :x: |
| **Disaster recovery plans** | | :x: |
| **Password policies** | | :x: |
| **Separation of duties** | | :x: |
| **Firewall** | :white_check_mark: | |
| **Intrusion detection system (IDS)** | | :x: |
| **Backups** | | :x: |
| **Antivirus software** | :white_check_mark: | |
| **Manual monitoring, maintenance, and intervention for legacy systems** | | :x: |
| **Encryption** | | :x: |
| **Password management system** | | :x: |
| **Locks (offices, storefront, warehouse)** | :white_check_mark: | |
| **Closed-circuit television (CCTV) surveillance** | :white_check_mark: | |
| **Fire detection/prevention (fire alarm, sprinkler system, etc.)** | :white_check_mark: | |

---

### Payment Card Industry Data Security Standard (PCI DSS)

| Best Practice | Yes | No |
| :--- | :---: | :---: |
| Only authorized users have access to customers' credit card information. | | :x: |
| Credit card information is stored, accepted, processed, and transmitted internally, in a secure environment. | | :x: |
| Implement data encryption procedures to better secure credit card transaction touchpoints and data. | | :x: |
| Adopt secure password management policies. | | :x: |

---

### General Data Protection Regulation (GDPR)

| Best Practice | Yes | No |
| :--- | :---: | :---: |
| E.U. customers' data is kept private/secured. | | :x: |
| There is a plan in place to notify E.U. customers within 72 hours if their data is compromised/there is a breach. | :white_check_mark: | |
| Ensure data is properly classified and inventoried. | | :x: |
| Enforce privacy policies, procedures, and processes to properly document and maintain data. | | :x: |

---

### System and Organization Controls (SOC 1 / SOC 2)

| Best Practice | Yes | No |
| :--- | :---: | :---: |
| User access policies are established. | | :x: |
| Sensitive data (PII/SPII) is confidential/private. | | :x: |
| Data integrity ensures the data is consistent, complete, accurate, and has been validated. | | :x: |
| Data is available to individuals authorized to access it. | | :x: |

---

## Recommendations

Botium Toys needs to implement key controls to strengthen the company's security posture, satisfy regulatory compliance requirements, and ensure the confidentiality of sensitive information. 

**Priority Action Items:**
* **Access Control & Password Security:** Implement Least Privilege, Separation of Duties, formal Password Policies, and a Password Management System.
* **Data Security & Privacy:** Implement Encryption (at rest and in transit), Data Classification/Inventory, and enforce privacy policies to adhere to PCI DSS and GDPR.
* **Monitoring & System Maintenance:** Implement an Intrusion Detection System (IDS) and establish manual monitoring, maintenance, and intervention for legacy systems.
* **Resilience & Recovery:** Establish comprehensive Disaster Recovery Plans and an automated Backup routine.
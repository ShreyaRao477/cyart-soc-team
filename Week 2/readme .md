# 🛡️ SOC Week 2 – Alert Management & Incident Response

**Author:** Shreya Rao 
**Date:** October 2025  

---

## 📘 Overview

This project demonstrates the end-to-end **Security Operations Center (SOC)** workflow for **alert prioritization, incident classification, and incident response**.  
It combines theoretical frameworks (CVSS, MITRE ATT&CK, NIST SP 800-61) with practical SOC exercises and simulations.

---

## 🎯 Objectives

- Understand **alert priority levels** and their impact on response time.
- Classify and enrich incidents using standardized taxonomies.
- Execute a complete **incident response lifecycle** (from detection to lessons learned).
- Apply CVSS scoring and SOC prioritization workflows.
- Practice evidence handling and documentation standards.

---

## 🧩 1. Alert Priority Levels

### 🔍 Core Concepts
| Priority | Description | Example |
|-----------|--------------|----------|
| **Critical** | Major data breach / ransomware | Log4Shell CVE-2021-44228 |
| **High** | Unauthorized admin access | Privilege escalation |
| **Medium** | Brute-force attempts | Limited login failures |
| **Low** | Reconnaissance | Port scans |

**Assignment Criteria:**
- **Asset Criticality:** Production > Test environment  
- **Exploit Likelihood:** Public exploit = higher priority  
- **Business Impact:** Financial or compliance risk raises priority  

**References:**  
- [FIRST CVSS v3.1 Guide](https://www.first.org/cvss/v3.1/specification-document)  
- NIST SP 800-61 Rev.2 – *Computer Security Incident Handling Guide*  
- CISA Alert AA21-356A – *Log4Shell Exploitation*  

---

## 🧠 2. Incident Classification

### 🗂️ Frameworks Used
- **MITRE ATT&CK** → Technique: `T1566.001 (Phishing: Spearphishing Attachment)`  
- **ENISA Incident Taxonomy**  
- **VERIS (Vocabulary for Event Recording and Incident Sharing)**  

### 🧾 Example
| Field | Data |
|--------|------|
| **Incident Type** | Phishing Campaign |
| **IOC (Hash)** | `SHA256: <placeholder>` |
| **Source IP** | 192.168.204.131 |
| **Affected User** | 20hotdogg00@gmail.com |

**Skills Gained:**  
✅ Standardized incident categorization  
✅ Metadata enrichment for SOC triage workflows  

---

## ⚙️ 3. Basic Incident Response

### 🔄 Lifecycle (NIST SP 800-61)
1. **Preparation** – Develop playbooks, tools setup  
2. **Identification** – Analyze alerts in SIEM  
3. **Containment** – Isolate infected endpoints  
4. **Eradication** – Remove threats, reset credentials  
5. **Recovery** – Restore systems, monitor  
6. **Lessons Learned** – Document findings  

**Procedures Practiced:**  
- System isolation (iptables/firewall rules)  
- Evidence preservation (hashing, memory dump)  
- Communication via escalation matrix  
- SOAR concepts using Splunk Phantom / Elastic SOAR  

---

## 🧪 4. Practical Application

### 🧮 Alert Classification (from Excel Sheet)
| Alert ID | Type | Priority | MITRE Tactic |
|-----------|------|-----------|---------------|
| 001 | Phishing | High | T1566 |
| 002 | SSH Brute Force | Medium | T1110 |
| 003 | Log4Shell Exploit | Critical | T1190 |

Visualization in Wazuh:
- Pie chart of **Critical vs High vs Medium** alerts  
- Trend graph showing alert frequency over time  

---

## 🧰 5. Phishing Incident Simulation

### **Executive Summary**
On **August 18, 2025**, a phishing email with a malicious link was reported.  
The SOC investigated, isolated the endpoint, and confirmed **no data exfiltration** occurred.

### **Timeline**
| Timestamp | Action |
|------------|--------|
| 2025-10-12 14:00 | Isolated endpoint |
| 2025-10-12 14:30 | Collected memory dump |

### **Impact Analysis**
- One mailbox targeted  
- No credentials stolen  
- No lateral movement detected  

### **Remediation**
- Block sender domain  
- Update mail filters  
- Reset affected user’s password  
- Awareness campaign initiated  

### **Lessons Learned**
- Implement faster phishing reporting  
- Automate IOC checks (URL reputation)  
- Improve user awareness and training  

---

## 🧾 6. Evidence Preservation

| Item | Description | Collected By | Date | Hash |
|------|--------------|--------------|------|------|
| Memory Dump | Server-X | SOC Analyst | 2025-10-12 | `<SHA256>` |

Tools: **Velociraptor**, **FTK Imager**  
Data collected: network connections (`SELECT * FROM netstat`)

---

## 🧱 7. Capstone: Full Alert-to-Response Cycle

**Tools Used:** Metasploit, Wazuh, CrowdSec  

| Timestamp | Source IP | Alert Description | MITRE Technique |
|------------|------------|------------------|-----------------|
| 2025-10-12 11:00 | 192.168.1.100 | VSFTPD exploit detected | T1190 |

**Actions Taken:**
- Isolated the compromised VM  
- Blocked attacker IP using CrowdSec  
- Verified network isolation with ping tests  

### **Reporting**
- 200-word report drafted in SANS template (Executive Summary, Timeline, Recommendations)  
- 100-word non-technical summary prepared for management  

---

## 📊 8. Key Outcomes

- Strengthened understanding of **CVSS-based prioritization**
- Practical experience in **incident response lifecycle**
- Exposure to **MITRE ATT&CK** and **ENISA** frameworks
- Hands-on practice with **Wazuh**, **TheHive**, **SOAR**, and **CrowdSec**

---

## 🚀 Next Steps

- Advance to **threat hunting** with Sigma & YARA rules.  
- Automate **incident enrichment** using SOAR tools.  
- Integrate **threat intelligence feeds** (AlienVault OTX, MISP).  
- Conduct red-team vs blue-team simulations in lab.

---

## 📚 References

- NIST SP 800-61 Rev. 2 – *Incident Handling Guide*  
- FIRST CVSS v3.1 Specification  
- MITRE ATT&CK Framework  
- ENISA Incident Taxonomy  
- SANS Incident Handler’s Handbook  
- CISA Alert (AA21-356A) – *Log4Shell Exploitation*  

---

## 🧑‍💻 Author

**Shreya Rao**  
_B.E. Computer Science (IoT, Cybersecurity & Blockchain)_  
_Alvas Institute of Engineering and Technology_  
🔗 [GitHub](https://github.com/ShreyaRao477) • [LinkedIn](linkedin.com/in/shreya-rao12)

---

> **Note:** This repository is part of the CYART SOC Training Program – Week 2 submission focusing on *Alert Classification & Incident Response*.

# 🛡️ SOC Analyst Portfolio — Threat Investigation & Log Analysis

Welcome to my **Security Operations Center (SOC Tier 1 & Tier 2)** portfolio. This repository documents hands-on threat investigations, alert triage, and incident response workflows conducted inside a dedicated virtualized lab environment powered by the **ELK Stack (Elasticsearch, Logstash, Kibana)**.

> **Core Philosophy:** SIEM platforms are just tools; true detection and response rely on understanding underlying telemetry, correlating raw logs across endpoints and networks, and turning noisy data into actionable incident reports.

---

## 🛠️ Lab Environment & Technical Stack

- **SIEM & Log Management:** ELK Stack (Elasticsearch, Logstash, Kibana)
- **Endpoint Telemetry:** Windows Event Logs, Sysmon, PowerShell Operational Logs
- **Network & Email Telemetry:** Email Gateway Logs (SPF/DKIM/DMARC), Firewall, IDS/IPS, Web Proxy & WAF Logs
- **Threat Intelligence & Enrichment:** VirusTotal, IBM X-Force Exchange, AbuseIPDB, OSINT
- **Frameworks:** MITRE ATT&CK, Cyber Kill Chain, NIST Incident Response Lifecycle

---

## 📂 Portfolio Structure & Investigations

| Module                                                                                         | Focus Area                           | Key Investigation Topics & Artifacts                                                                                                   |
| :--------------------------------------------------------------------------------------------- | :----------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------- |
| **[01-SOC-Overview](./01-SOC-Overview)**                                                       | SIEM Architecture & Attack Lifecycle | Log ingestion pipelines, ELK query fundamentals, Cyber Kill Chain mapping                                                              |
| **[02-Investigating-Email-Threats](./02-Investigating-Email-Threats)**                         | Phishing & Email Gateway Analysis    | Email header forensics, SPF/DKIM/DMARC validation, malicious attachments & URL triage                                                  |
| **[03-Investigating-Microsoft-Windows-Threats](./03-Investigating-Microsoft-Windows-Threats)** | Endpoint Forensics & Hunting         | Brute-force & logon tracking (Event IDs 4624/4625), malicious process execution, obfuscated PowerShell, persistence & lateral movement |
| **[04-Investigating-Network-Threats](./04-Investigating-Network-Threats)**                     | Perimeter & Traffic Analysis         | Firewall & IDS/IPS alert triage, C2 beaconing via Web Proxy logs, WAF web attack analysis                                              |
| **[05-Threat-Intelligence-and-More](./05-Threat-Intelligence-and-More)**                       | IOC Enrichment & Threat Intel        | Reputation analysis and artifact pivoting using VirusTotal, IBM X-Force, and AbuseIPDB                                                 |

---

## 📋 Investigation Methodology

Every lab and incident report in this repository follows a standardized Tier 1 / Tier 2 SOC workflow:

1. **Alert Triage & Scoping:** Reviewing initial SIEM alerts in Kibana and identifying affected assets.
2. **Log Correlation & Deep-Dive:** Pivoting across Windows, Network, and Proxy logs to reconstruct the attack timeline.
3. **Threat Intelligence Enrichment:** Validating suspicious IPs, domains, and file hashes against external TI feeds.
4. **Verdict & MITRE ATT&CK Mapping:** Classifying the event (True Positive vs. False Positive) and mapping attacker TTPs.
5. **Incident Reporting & Remediation:** Documenting containment actions, eradication steps, and detection recommendations.

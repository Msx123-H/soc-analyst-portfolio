# Incident Investigation Report: [Lab / Incident Title]

## 1. Executive Summary

- **Alert / Incident Name:** [e.g., Suspicious PowerShell Execution / Phishing Email Delivery]
- **Severity:** [Low / Medium / High / Critical]
- **Verdict:** [True Positive / False Positive]
- **MITRE ATT&CK Mapping:** [e.g., T1059.001 - PowerShell]

---

## 2. Investigation Scope & Data Sources

- **SIEM Solution:** ELK Stack (Kibana)
- **Log Sources Analyzed:** [e.g., Windows Security Events, Sysmon, Proxy Logs, Email Gateway]
- **Affected Host / User:** [e.g., `DESKTOP-WIN10` / `john.doe` - *Sanitized*]
- **Timeframe (UTC):** [Start Time] to [End Time]

---

## 3. Step-by-Step Log Analysis (ELK Stack)

### Step 1: Initial Triage & Query

- **KQL / Lucene Query Used:**
  ```text
  event.code: "4688" and process.name: "powershell.exe"
  ```
- **Observation:** [Explain what the raw log shows and why it is suspicious.]
- **Evidence Screenshot:**
  ![Initial Log Evidence](./screenshots/01-initial-alert.png)

### Step 2: Log Correlation & Timeline Reconstruction

- **Observation:** [Explain how you pivoted to related logs—e.g., parent process, network connection, or previous failed logins.]
- **Evidence Screenshot:**
  ![Correlated Logs](./screenshots/02-correlation.png)

---

## 4. Threat Intelligence Enrichment

- **Tools Used:** VirusTotal, IBM X-Force, AbuseIPDB
- **Findings:** [Summarize reputation scores, malicious tags, or associated malware families.]
- **Evidence Screenshot:**
  ![Threat Intel Result](./screenshots/03-threat-intel.png)

---

## 5. Indicators of Compromise (IOCs)

| Indicator Type         | Value (Defanged)                      | Context / Role          |
| :--------------------- | :------------------------------------ | :---------------------- |
| **IP Address**         | `192.168.1[.]100`                     | Attacker C2 / Source IP |
| **Domain / URL**       | `hxxp://malicious-domain[.]com`       | Payload hosting         |
| **File Hash (SHA256)** | `e3b0c44298fc1c149afbf4c8996fb924...` | Malicious dropper       |

---

## 6. Containment & Remediation Recommendations

1. **Immediate Containment:** [e.g., Isolate affected host, block malicious IP/domain at Firewall/Proxy, reset compromised user credentials.]
2. **Hardening / Detection Improvement:** [e.g., Enable PowerShell Script Block Logging, create a Kibana alert rule for encoded commands.]

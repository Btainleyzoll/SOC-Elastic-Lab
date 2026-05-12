# SOC Detection Lab

A home SOC lab built to practice threat detection, log analysis, and incident response using the Elastic Stack.

---

# Overview

This project demonstrates how security events can be collected, analysed, and investigated within a small SIEM environment.

The lab includes:

* Windows 10 victim machine
* Ubuntu SIEM server
* Kali Linux attacker machine
* Sysmon + Winlogbeat log collection
* Elasticsearch + Kibana monitoring

---

# Technologies Used

* Elasticsearch
* Kibana
* Sysmon
* Winlogbeat
* Kali Linux
* PowerShell
* Windows Event Logs

---

# Attacks Simulated

| Attack                      | MITRE ATT&CK | Status   |
| --------------------------- | ------------ | -------- |
| Mimikatz Credential Dumping | T1003.001    | Detected |
| PowerShell Download Cradle  | T1059.001    | Detected |
| RDP Brute Force             | T1110.001    | Detected |

---

# Detection Examples

## Mimikatz Detection

```kql id="b5o9wr"
event.code: 10 AND
winlog.event_data.TargetImage: *lsass.exe
```

---

## RDP Brute Force Detection

```kql id="y3ms8g"
event.code: "4625" AND
winlog.event_data.LogonType: "10"
```

---

# Project Structure

```text id="4rhzl8"
SOC-Detection-Lab/
│
├── detection-rules/
├── incident-reports/
├── screenshots/
├── setup/
├── README.md
```

# Skills Demonstrated

* SIEM deployment and configuration
* Threat detection engineering
* Log analysis using Kibana
* Incident investigation
* MITRE ATT&CK mapping
* Windows event monitoring

---

# Setup Summary

## Environment

| Machine       | Purpose                |
| ------------- | ---------------------- |
| Ubuntu Server | Elasticsearch + Kibana |
| Windows 10    | Victim machine         |
| Kali Linux    | Attack simulation      |

## Log Flow

```text id="6tv20p"
Windows Logs → Winlogbeat → Elasticsearch → Kibana
```

---

# Incident Reports

* Mimikatz Credential Dumping
* PowerShell Download Cradle
* RDP Brute Force Attack

Reports can be found in the `incident-reports/` folder.

---

# Disclaimer

This project was created for educational purposes inside an isolated lab environment.

---

# Author

Benjamin Ainley-Zoll

* GitHub: Btainleyzoll
* LinkedIn: https://www.linkedin.com/in/benjamin-ainley-zoll/

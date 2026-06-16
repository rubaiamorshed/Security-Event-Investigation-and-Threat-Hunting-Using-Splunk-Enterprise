# Security-Event-Investigation-and-Threat-Hunting-Using-Splunk-Enterprise
Splunk-based threat hunting and cybersecurity investigation project analyzing web traffic and firewall logs to detect SQL injection, directory traversal, web shell activity, malware execution, and command-and-control communications through attack chain reconstruction and MITRE ATT&amp;CK mapping.

## Overview

This project demonstrates a cybersecurity investigation conducted using Splunk Enterprise to analyze web traffic and firewall logs for indicators of malicious activity. Through log analysis, threat hunting, event correlation, and MITRE ATT&CK mapping, a complete attack chain was reconstructed from initial reconnaissance through post-exploitation activity.

The investigation identified multiple web application attack techniques, including SQL injection attempts, directory traversal attacks, sensitive resource enumeration, web shell execution, malware deployment, and command-and-control (C2) communications.

---

## Objectives

* Analyze web server and firewall logs using Splunk Enterprise
* Identify indicators of compromise (IOCs)
* Detect web application attacks and exploitation attempts
* Correlate events across multiple log sources
* Reconstruct the attacker lifecycle
* Map attacker behavior to the MITRE ATT&CK framework
* Produce a professional incident investigation report

---

## Tools & Technologies

* Splunk Enterprise
* SPL (Search Processing Language)
* MITRE ATT&CK Framework
* OWASP Top 10
* Threat Hunting Methodologies
* Log Analysis
* Web Security Monitoring

---

## Data Sources

### Web Traffic Logs

* HTTP Requests
* User-Agent Strings
* Client IP Addresses
* Request Paths
* HTTP Status Codes

### Firewall Logs

* Source and Destination IP Addresses
* Network Protocols
* Allowed Connections
* Command-and-Control Indicators

---

## Investigation Summary

The investigation identified a likely attack progression consisting of:

1. Reconnaissance and Enumeration
2. Sensitive Resource Discovery
3. SQL Injection Attempts
4. Directory Traversal Attacks
5. Web Shell Activity
6. Malware Execution
7. Command-and-Control Communications

Evidence suggests that the attacker utilized automated tools such as SQLMap and Havij to perform exploitation attempts before transitioning to post-exploitation activities.

---

## Key Findings

### Automated Reconnaissance Activity

Detected automated scanning activity using tools including:

* curl
* wget
* zgrab
* Go-http-client
* Python Requests

### SQL Injection Attempts

Observed time-based SQL injection payloads including:

```text
/item.php?id=1 AND SLEEP(5)--
/search.php?q=test'%20AND%20SLEEP(5)--
```

Associated Tools:

* SQLMap
* Havij

### Sensitive Resource Enumeration

Attackers attempted access to:

```text
/.env
/.git/config
/phpinfo.php
/logs.tar.gz
```

### Directory Traversal Attempts

Observed attempts to access sensitive operating system files:

```text
/download?file=../../etc/passwd
```

### Web Shell Activity

Detected command execution through a web shell endpoint:

```text
/shell.php?cmd=whoami
/shell.php?cmd=chmod +x bunnylock.bin
/shell.php?cmd=./bunnylock.bin
```

### Command-and-Control Communications

Firewall logs identified outbound communications between an internal host and external infrastructure over TCP port 8080, indicating potential C2 activity.

---

## MITRE ATT&CK Mapping

| Technique                         | ATT&CK ID |
| --------------------------------- | --------- |
| Active Scanning                   | T1595     |
| Gather Victim Host Information    | T1592     |
| Exploit Public-Facing Application | T1190     |
| Command and Scripting Interpreter | T1059     |
| Data from Local System            | T1005     |
| Application Layer Protocol        | T1071     |

---

## Skills Demonstrated

### Security Operations & Threat Hunting

* Threat Hunting
* Log Correlation
* IOC Identification
* Attack Chain Reconstruction
* Security Event Investigation

### SIEM & Log Analysis

* Splunk Enterprise
* SPL Query Development
* Web Traffic Analysis
* Firewall Log Analysis

### Threat Detection

* SQL Injection Detection
* Directory Traversal Detection
* Web Shell Identification
* Command-and-Control Detection
* Suspicious User-Agent Analysis

### Cybersecurity Frameworks

* MITRE ATT&CK Mapping
* Incident Investigation Methodology
* Risk Assessment
* Security Reporting

---

## Project Outcome

By correlating web traffic and firewall events, the investigation successfully reconstructed a likely attack lifecycle from reconnaissance to post-exploitation activity. The project demonstrates practical experience in SIEM analysis, threat hunting, attack detection, and incident investigation within a simulated enterprise environment.

---

## References

* MITRE ATT&CK Framework
* OWASP Top 10
* Splunk Enterprise Documentation
* TryHackMe – Splunk for Log Analysis (Advent of Cyber 2025)

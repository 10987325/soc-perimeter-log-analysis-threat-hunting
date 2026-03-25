# 🔐 SOC Investigation: Perimeter Log Analysis & Threat Hunting

## 📖 Overview
This project demonstrates a hands-on Security Operations Center (SOC) investigation using real-world log sources. The objective was to analyze perimeter logs, detect malicious activity, and trace the complete attack lifecycle from reconnaissance to data exfiltration.

---

## 🛠️ Log Sources
- Firewall Logs (`firewall.log`)
- WAF / IDS Logs (`ids_alerts.log`)
- VPN Authentication Logs (`vpn_auth.log`)

---

## 🎯 Objectives
- Detect reconnaissance activity
- Identify brute-force attacks
- Investigate lateral movement
- Detect Command & Control (C2) communication
- Analyze data exfiltration attempts

---

## 🔍 Key Findings

### 🔹 Reconnaissance Activity
- External attacker IP identified: **203.0.113.45**
- Scanned multiple internal systems across different ports
- Additional suspicious IP observed: **203.0.113.10**

---

### 🔹 Brute-Force Attack
- **118 failed login attempts**
- Source IP: **203.0.113.45**
- Target: VPN authentication service
- Indicates credential brute-force attack

---

### 🔹 Lateral Movement
- SMB exploitation detected (**Port 445**)
- Compromised host used to pivot across internal systems

---

### 🔹 Command & Control (C2)
- Beaconing behavior observed
- Repeated outbound connections to external attacker infrastructure

---

### 🔹 Data Exfiltration
- Compromised Host: **10.0.0.51**
- High volume of outbound traffic detected
- Indicates potential data exfiltration

---

## ⏱️ Attack Timeline

1. Reconnaissance → Attacker scans network (**203.0.113.45**)  
2. Brute-force → 118 failed VPN login attempts  
3. Lateral Movement → SMB exploitation (Port 445)  
4. C2 Communication → Beaconing activity detected  
5. Data Exfiltration → Host **10.0.0.51** sends large outbound traffic  

---

## 🧬 MITRE ATT&CK Mapping

| Attack Stage        | Technique ID | Description |
|--------------------|-------------|-------------|
| Reconnaissance     | T1595       | Active Scanning |
| Brute Force        | T1110       | Credential Access |
| Lateral Movement   | T1021       | SMB/Remote Services |
| C2 Communication   | T1071       | Application Layer Protocol |
| Data Exfiltration  | T1041       | Exfiltration Over C2 Channel |

---

## 💻 Commands Used

```bash
# Identify attacker IP activity
grep "203.0.113.45" firewall.log

# Count failed login attempts
grep "Failed" vpn_auth.log | wc -l

# Find most frequent IPs
awk '{print $1}' firewall.log | sort | uniq -c | sort -nr

# Detect SMB activity
grep ":445" firewall.log

# Identify large outbound traffic
grep "10.0.0.51" firewall.log
```

---

## 🧠 Skills Demonstrated
- Log analysis using Linux CLI
- Threat hunting & correlation
- Network traffic investigation
- Attack lifecycle analysis
- SOC investigation methodology

---


## 📊 Key Takeaway
This project demonstrates a real-world cyber attack lifecycle:

**Reconnaissance → Brute-force → Lateral Movement → C2 → Data Exfiltration**

Understanding and detecting these stages is critical for effective SOC operations and incident response.

---

## 🔗 Connect With Me
- GitHub: https://github.com/10987325  
- LinkedIn: https://linkedin.com/in/faraz-kachelo-b180267a  

---

## ⭐ Future Improvements
- Automate detection using Python scripts
- Integrate SIEM-based alerting
- Add threat intelligence enrichment
- Visualize attack patterns using dashboards

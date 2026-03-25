
# 🔐 SOC Investigation: Perimeter Log Analysis & Threat Hunting

## 📖 Overview
This project demonstrates a hands-on Security Operations Center (SOC) investigation using real-world log sources. The objective was to analyze perimeter logs, detect malicious activity, and track the full attack lifecycle.

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
- Detect Command & Control (C2)
- Analyze data exfiltration attempts

---

## 🔍 Investigation Steps & Findings

### 1️⃣ Reconnaissance Detection
- External attacker IP identified: **203.0.113.45**
- Multiple ports scanned across internal systems
- Additional suspicious IP: **203.0.113.10**

---

### 2️⃣ Brute-Force Attack
- **118 failed login attempts**
- Source IP: **203.0.113.45**
- Target: VPN authentication service

---

### 3️⃣ Lateral Movement
- SMB exploitation detected (**Port 445**)
- Compromised system used for internal pivoting

---

### 4️⃣ Command & Control (C2)
- Beaconing behavior observed
- Repeated outbound connections to attacker-controlled infrastructure

---

### 5️⃣ Data Exfiltration
- Compromised Host: **10.0.0.51**
- High-volume outbound traffic detected
- Indicates potential data exfiltration

---

## 🧠 Skills Demonstrated
- Log analysis using Linux CLI
- Threat hunting & correlation
- Network traffic investigation
- Attack lifecycle analysis
- SOC investigation methodology

---

## ⚙️ Tools & Commands Used
- `grep`
- `awk`
- `sort`
- `uniq`
- `cut`
- `wc`

---

## 📊 Key Takeaway
This project highlights a real-world attack progression:

Reconnaissance → Brute-force → Lateral Movement → C2 → Data Exfiltration

Understanding this lifecycle is critical for detecting and responding to advanced threats in a SOC environment.

---

## 🔗 Connect With Me
- GitHub: https://github.com/10987325  
- LinkedIn: https://linkedin.com/in/faraz-kachelo-b180267a  

---

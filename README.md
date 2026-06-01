# 🛡️ Net-Guard — Malware Traffic Analysis Tool

## Overview
This project analyzes network traffic capture files (PCAP) to detect malicious activity 
and reconstruct attack behavior. It helps identify compromised systems by analyzing 
patterns such as DNS anomalies, command-and-control (C2) communication, and suspicious 
HTTP activity.

---

## ✨ Key Features

- **DNS Analysis** — Detects suspicious domains using entropy and length-based heuristics.
- **C2 Beaconing Detection** — Identifies periodic communication between infected hosts and attacker servers.
- **HTTP Traffic Inspection** — Flags suspicious requests (e.g., webshells, command execution patterns).
- **Attack Correlation Engine** — Links multiple events into attack chains (DNS → IP → Beaconing → Spread).
- **Risk Scoring System** — Assigns severity levels: `CRITICAL` | `HIGH` | `MEDIUM` | `LOW`
- **GeoIP Enrichment** — Maps IP addresses to geographic locations.
- **Report Generation** — Outputs `mta_report.json` and `mta_report.txt`
- **Network Visualization** — Generates `network_graph.png` for traffic relationships.

---

## 📁 Project Structure
├── malware_traffic_analyzer.py

├── README.md

├── requirements.txt

├── network_graph.png
---

## 🚀 How to Run

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

### 2. Run the analyzer

```bash
python malware_traffic_analyzer.py pikabot.pcap
```

--
---

## 🚀 How to Run

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

### 2. Run the analyzer

```bash
python malware_traffic_analyzer.py pikabot.pcap
```

---

output

### Step 1 — Tool Startup & PCAP Loading
[![Tool Startup](screenshot_startup.png)](https://github.com/rahulUchihaaa/net-guard-network-security-tool/blob/4ada0f794a6469831bd5088179d788e50bbc36a0/screenshot_startup.png.png)

> Loads 47,697 packets, fetches live threat intel from Feodo Tracker, 
> resolves DNS maps, and extracts IP/HTTP traffic.

---

### Step 2 — Analysis Summary
[![Analysis Summary](screenshot_summary.png)](https://github.com/rahulUchihaaa/net-guard-network-security-tool/blob/4ada0f794a6469831bd5088179d788e50bbc36a0/screenshot_summary.png.png)

> Produces a full kill-chain summary:
> - **87 Total Alerts** across 3 Attack Chains
> - ☠️ CRITICAL: 3 | 🔴 HIGH: 27 | ⚠️ MEDIUM: 56 | ℹ️ LOW: 1
> - **TOTAL RISK SCORE: 209 pts**

---

### Step 3 — Final Verdict & Risk Score Breakdown
[![Risk Score and Verdict](screenshot_verdict.png)](https://github.com/rahulUchihaaa/net-guard-network-security-tool/blob/4ada0f794a6469831bd5088179d788e50bbc36a0/screenshot_verdict.png.png)

> Detailed scoring breakdown with attack chain correlations and final verdict:
> **🚨 CRITICAL RISK — Active compromise. Contain immediately!**

---

## 🌐 Network Graph

![Network Graph](network_graph.png)

> Visual map of all detected traffic relationships between hosts.

---

## 🔬 Real Dataset Used

Tested on a real malware traffic dataset **(Pikabot infection)** sourced from 
[Malware-Traffic-Analysis.net](https://www.malware-traffic-analysis.net/)

### Observed Behavior:
- DNS queries to suspicious domains
- C2 beaconing activity
- Repeated HTTP requests (possible payload delivery)
- Data exfiltration patterns
- Lateral movement across hosts

---

## 💡 Why This Matters

Modern malware often hides within normal-looking traffic. This tool helps:

- Detect hidden threats in network traffic
- Identify compromised systems
- Understand attacker behavior
- Assist incident response teams

## 🔁 Example Detection Flow
DNS Query → Suspicious Domain
↓

Resolved IP → External Host
↓

Repeated Connections → Beaconing
↓

HTTP Activity → Payload Execution
↓

Lateral Movement → Internal Spread
---

## ⚠️ Limitations

- Works on offline PCAP files only (not real-time yet)
- Limited visibility into encrypted HTTPS payloads
- Detection based on heuristics (may produce false positives)

---

## 🔮 Future Improvements

- Real-time packet sniffing
- Machine learning–based anomaly detection
- Integration with SIEM tools
- Advanced threat intelligence feeds

---

## ✅ Conclusion

This project demonstrates how raw network packets can be transformed into actionable 
security insights. It bridges the gap between low-level packet data and high-level 
threat understanding.

---

## 👤 Author

📍 Gudivada, Andhra Pradesh, India

🎯 Aspiring Security Researcher | KAIST Masters Applicant

🔗 [LinkedIn — Rahul Sonti](https://www.linkedin.com/in/rahul-sonti-b49288322/)
---

## 🔁 Example Detection Flow

# 🔬 Malware Traffic Analysis Tool

## 🚀 Overview

This project analyzes network traffic capture files (**PCAP**) to detect malicious activity and reconstruct attack behavior.
It helps identify compromised systems by analyzing patterns such as DNS anomalies, command-and-control (C2) communication, and suspicious HTTP activity.

---

## 🧠 Key Features

* 🔍 **DNS Analysis**
  Detects suspicious domains using entropy and length-based heuristics.

* ☠️ **C2 Beaconing Detection**
  Identifies periodic communication between infected hosts and attacker servers.

* 🌐 **HTTP Traffic Inspection**
  Flags suspicious requests (e.g., webshells, command execution patterns).

* 🔗 **Attack Correlation Engine**
  Links multiple events into attack chains (DNS → IP → Beaconing → Spread).

* 📊 **Risk Scoring System**
  Assigns severity levels:

  * CRITICAL
  * HIGH
  * MEDIUM
  * LOW

* 🗺️ **GeoIP Enrichment**
  Maps IP addresses to geographic locations.

* 🧾 **Report Generation**

  * JSON report (`mta_report.json`)
  * Text report (`mta_report.txt`)

* 📈 **Network Visualization**

  * Generates `network_graph.png` for traffic relationships

---

## 📂 Project Structure

```
├── malware_traffic_analyzer.py
├── README.md
├── requirements.txt
├── network_graph.png
---

## ▶️ How to Run

### 1️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

### 2️⃣ Run the analyzer

```bash
python malware_traffic_analyzer.py pikabot.pcap
```

---

## 📸 Sample Output

(Add your screenshot here)

```
TOTAL RISK SCORE : 209 points
VERDICT : CRITICAL RISK — Active compromise
```

---

## 🔥 Real Dataset Used

This project was tested on a **real malware traffic dataset (Pikabot infection)** sourced from
Malware-Traffic-Analysis.net

### 🧬 Observed Behavior:

* DNS queries to suspicious domains
* C2 beaconing activity
* Repeated HTTP requests (possible payload delivery)
* Data exfiltration patterns
* Lateral movement across hosts

---

## ⚠️ Why This Matters

Modern malware often hides within normal-looking traffic.
This tool helps:

* Detect hidden threats in network traffic
* Identify compromised systems
* Understand attacker behavior
* Assist incident response teams

---

## 🧠 Example Detection Flow

```
DNS Query → Suspicious Domain
        ↓
Resolved IP → External Host
        ↓
Repeated Connections → Beaconing
        ↓
HTTP Activity → Payload Execution
        ↓
Lateral Movement → Internal Spread
```

---

## ⚠️ Limitations

* Works on **offline PCAP files only** (not real-time yet)
* Limited visibility into encrypted HTTPS payloads
* Detection based on heuristics (may produce false positives)

---

## 🚀 Future Improvements

* Real-time packet sniffing
* Machine learning–based anomaly detection
* Integration with SIEM tools
* Advanced threat intelligence feeds

---

## 🏁 Conclusion

This project demonstrates how raw network packets can be transformed into actionable security insights.
It bridges the gap between low-level packet data and high-level threat understanding.

---

## 👨‍💻 Author

Rahul Sonti
Cybersecurity Enthusiast | Aspiring Penetration Tester
📍 Andhra Pradesh, India


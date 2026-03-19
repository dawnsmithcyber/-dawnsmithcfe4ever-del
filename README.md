# -dawnsmithcyber
# 🛡️ Dawn Smith | SOC Analyst & Cybersecurity Researcher
# Applying 4.0 academic excellence in Financial Forensics to real-world cybersecurity challenges.
<p>
<a href="https://www.linkedin.com/in/dawnsmith-cyber">
<img src="https://img.shields.io/badge/-LinkedIn-0072b1?&style=for-the-badge&logo=linkedin&logoColor=white" />
</a>
</p>

[![TryHackMe](https://img.shields.io/badge/TryHackMe-000000?style=for-the-badge&logo=tryhackme&logoColor=red)](https://tryhackme.com/p/dawn.smith.cfe.4ever)
[![Certification](https://img.shields.io/badge/Learning-CFE-green?style=for-the-badge)](https://www.credly.com/badges/b4eb9c9b-20e8-4217-91f3-b40215381512 )

## 👤 About Me
I am a cybersecurity professional with a CFE, currently training and immersed in the **Cybersecurity Community** apprenticeship with Cyber Potential. I specialize in monitoring, detecting, and responding to threats within the digital landscape. My goal is to master the **Technical Controls** that keep organizations resilient against modern adversaries.

---

## 🛠️ Technical Arsenal Being Added

### **Identity & Network Defense**
* **Firewalls & ACLs:** Configuring rules to enforce the Principle of Least Privilege.
* **MFA & IAM:** Strengthening authentication protocols to prevent unauthorized access.
* **VPN/TLS:** Securing data in transit across untrusted networks.
* **Microsoft Azure With Defender For Cloud Hands On:** Hands-on lab focused on cloud security posture management (CSPM) and workload protection. The project demonstrates how to deploy, configure, and monitor security within the Azure ecosystem to detect threats and remediate vulnerabilities in real-time.


### **Monitoring & Detection (The SOC Toolkit)**
* **SIEM:** Analyzing logs in **Splunk / ELK Stack** to identify "needles in the haystack."
* **IDS/IPS:** Deploying **Snort / Suricata** to detect and block malicious traffic.
* **Endpoint Security:** Implementing **EDR / Sysmon** for granular visibility into host activity.

---

## 🚀 Featured Cybersecurity Labs
# Azure KQL: Moving from Reactive to Proactive Threat Hunting 🛡️

## 📝 Project Overview
This project documents my transition from reactive security monitoring to proactive threat hunting using **Kusto Query Language (KQL)** within Azure Sentinel and Log Analytics. The goal was to go beyond simply receiving alerts to actively validating threats, mapping attacker paths, and creating visual narratives for stakeholders.

---

## 🛠️ Core Competencies Practiced

### 1. Analyzing Traffic Flows & Attribution
I developed queries to map connections between **Source IPs (srcIP)** and **Destination IPs (destIP)** to visualize the network perimeter.
* **Operators used:** `where`, `summarize`, `count()`, `by`, `==`, `!=`
* **Outcome:** Successfully categorized traffic by country and status—specifically identifying "MaliciousFlow", "Allowed", and "Denied" traffic to find gaps in firewall policies.

### 2. Smart Filtering & Threat Intelligence
Implemented advanced filtering to reduce "Signal vs. Noise" and focus on high-fidelity alerts.
* **Technique:** Leveraged `where` clauses combined with external data lists to automatically identify and flag traffic from known malicious IP addresses.
* **Efficiency:** Filtered out legitimate high-volume traffic (such as Microsoft Update Services) to prevent hours of wasted investigation.

### 3. Visual Reporting for Stakeholders
Translated complex raw logs into actionable intelligence.
* **Visuals:** Integrated query results directly into Azure dashboards.
* **Outcome:** Reduced the time-to-report for stakeholders by providing real-time, easy-to-digest charts that highlight current threat trends.

---

## 🔍 Sample KQL Implementation

The following snippet demonstrates how I aggregate network data to identify geographic anomalies in malicious traffic.

```kusto
// Mapping Malicious Traffic by Country
CommonSecurityLog
| where DeviceAction != "denied" // Focusing on traffic that bypassed the perimeter
| where MaliciousIP_Flag == true // Comparing against external threat intel lists
| summarize ConnectionCount = count() by SourceIP, DestinationIP, SourceCountry
| where ConnectionCount > 10
| sort by ConnectionCount desc
| render barchart with (title="Top Malicious Allowed Connections by Country")
📈 Key Outcomes
Enhanced Visibility: Created a global map of connection attempts to visualize geographic risks.

Proactive Defense: Successfully identified "low and slow" patterns that traditional threshold-based alerts missed.

Optimized SOC Workflow: Streamlined reporting processes by creating reusable query templates for recurring security audits.

🚀 Next Steps
[ ] Integrate Sentinel Watchlists for dynamic, real-time threat feed updates.

[ ] Develop Time-Series Analysis queries to detect statistical outliers in user behavior.



### 📊 Linux Fundamentals Part 1 https://tryhackme.com/room/linuxfundamentalspart1
* **The Goal:** Introduction to the essential commands on an interactive terminal.
* **Controls Used:** Linux
* **Outcome:** Learned commands to interact via terminal.

### 📊 Python Basics https://tryhackme.com/room/pythonbasics?utm_campaign=social_share&utm_medium=social&utm_content=share-completed-room&utm_source=copy&sharerId=697380b71aadacf217fb0a90
* **The Goal:** learn to write code using a code editor.
* **Outcome:** Using a web-based code editor, learn the basics of Python and put your knowledge into practice by eventually coding a short Bitcoin investment project.

### 📊 SOC Fundamentals https://app.letsdefend.io/training/lessons/soc-fundamentals
* **The Goal:** learn SOC Fundamentals
* **Outcome:** During this intensive lab series, I gained hands-on experience in the core workflows of a Security Operations Center (SOC), focusing on the end-to-end lifecycle of incident detection and response. I developed proficiency in log analysis and correlation using industry-standard SIEM platforms, where I practiced triaging alerts, distinguishing true positives from false positives, and mapping attacker behaviors to the MITRE ATT&CK® framework. Through simulated attack scenarios involving malware, phishing, and network intrusions, I strengthened my ability to monitor network traffic via Wireshark, investigate endpoint anomalies, and execute containment strategies. This experience solidified my understanding of the Cyber Kill Chain and equipped me with the technical agility required to defend enterprise environments against evolving threats.

### 📊 Offensive Security Intro https://tryhackme.com/room/offensivesecurityintrokKx12?utm_campaign=social_share&utm_medium=social&utm_content=share-completed-room&utm_source=copy&sharerId=697380b71aadacf217fb0a90
* **The Goal:** The goal was to master the attacker's methodology to identify better, exploit, and remediate vulnerabilities within a secure environment.
* **The Outcome:** I gained hands-on experience with the fundamental stages of an engagement—Information Gathering (Reconnaissance), Enumeration, and Exploitation—using industry-standard tools like Nmap and GoBuster. By successfully identifying vulnerabilities within a target web server and utilizing the Metasploit Framework to gain unauthorized access, I developed a practical understanding of how attackers bypass security controls. This lab reinforced the critical importance of the 'think like a hacker' approach to identify and remediate security gaps before malicious actors can exploit them.

### 📊 Activity Logs: Configured Diagnostic Settings to track both "Service" and "Blob" level metrics. ✅ 

I just completed a hands-on demo setting up Azure Storage Account Logs. I see why this can be a game-changer for visibility. Without access to these logs, an attacker could steal data, and you’d be left in the dark.

Investigative Impact:
* Scope: Targeted an Azure Storage Account used for sensitive financial data.
* Activity Logs: Configured Diagnostic Settings to track both "Service" and "Blob" level metrics.

Here is the reasoning I learned:
This setup allows a SOC Analyst to spot (ATO) Account Takeover or Data Exfiltration in real-time.

Key Takeaway: If you don't log it, you can't investigate it. - Another reminder why digital integrity is so important in an investigation.

---

## 📉 Growth & Metrics
* **Currently Learning:** Azure Storage Account Logs Setup & Azure Monitor Logs

---

## 🤝 Let's Connect
> "Security is not a product, but a process." — Bruce Schneier

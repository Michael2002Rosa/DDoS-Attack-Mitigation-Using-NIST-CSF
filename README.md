# 🚨 Incident Response: DDoS Attack Mitigation Using NIST CSF  
*A cybersecurity project demonstrating NIST framework application to respond to a DDoS attack*

## 📝 Incident Report Analysis  

### **Summary**  
**Security Event:**  
- A **DDoS attack** flooded the network with ICMP packets via an unconfigured firewall, causing a 2-hour outage.  

**Impact:**  
- All internal network services were unreachable during the attack.  

**Response:**  
- Blocked ICMP packets, took non-critical services offline, and restored critical services.  

**Root Cause:**  
- Firewall misconfiguration allowed ICMP flood from spoofed IP addresses.  

---

## 🔍 NIST CSF Implementation  

### **1. Identify**  
**Affected Systems:**  
- Internal network infrastructure (firewalls, servers).  
- Web design/graphic design services (downtime affected client projects).  

**Gaps Identified:**  
- No rate limiting for ICMP traffic.  
- Lack of IP spoofing detection.  
- Insufficient network monitoring.  

### **2. Protect**  
**Immediate Actions:**  
- Implement **firewall rules** to:  
  - Rate-limit ICMP packets (e.g., max 5 pings/sec per IP).  
  - Enable **Reverse Path Forwarding (RPF)** to block spoofed IPs.  

**Long-Term Protections:**  
- Deploy **IDS/IPS** (e.g., Snort/Suricata) to filter malicious ICMP traffic.  
- Conduct **employee training** on DDoS recognition and reporting.  

### **3. Detect**  
**Monitoring Enhancements:**  
- **SIEM Integration**: Use Splunk/ELK to alert on abnormal traffic spikes.  
- **NetFlow Analysis**: Monitor traffic patterns for anomalies (e.g., >1,000 ICMP/sec).  

**Detection Tools:**  
- **Wireshark** for packet-level analysis.  
- **Cloudflare DDoS Protection** for external traffic scrubbing.  

### **4. Respond**  
**Incident Response Plan:**  
1. **Containment**: Isolate affected segments; block malicious IPs via firewall.  
2. **Neutralization**: Deploy IPS to drop ICMP flood traffic.  
3. **Analysis**: Perform packet capture (PCAP) review to identify attack vectors.  
4. **Communication**: Notify stakeholders via predefined incident channels.  

### **5. Recover**  
**Restoration Steps:**  
- **Phased Reboot**: Restore critical services first (e.g., client-facing portals).  
- **Backup Verification**: Ensure clean backups are available pre-attack.  
**Improvements:**  
- **Redundant Systems**: Deploy load balancers to distribute traffic.  
- **Incident Drills**: Quarterly DDoS simulation exercises.  

---

## 🌟 Why This Matters  
- **Framework Mastery**: Demonstrates **NIST CSF** application in real-world scenarios.  
- **Business Impact**: Reduces downtime costs (average DDoS attack costs **$120K–$2M**).  
- **Compliance**: Aligns with **NIST SP 800-53** (SI-4 for monitoring) and **PCI DSS 11.4** (DDoS resilience).  

---

## 🛠️ Tools & References  
- **Firewall**: pfSense/iptables for rate limiting.  
- **Monitoring**: Wireshark, Splunk, SolarWinds.  
- **Frameworks**: NIST CSF, MITRE ATT&CK (T1498).  


---

## 📂 How to Use This Project  
- **For Recruiters**: Showcases **incident response** skills and **NIST CSF expertise**.  
- **For Learners**: [Template](https://docs.google.com/document/d/1EnieOKYJyKGsVff5Gg-3-dVwrHrZ2m8Hig6tVpfKqyg/template/preview?resourcekey=0-eb5t-d69zTPLEGthIpVlXw) for analyzing attacks via NIST framework.

### 📜 License  
This project is part of the [Google Cybersecurity Certificate](https://www.coursera.org/professional-certificates/google-cybersecurity).  

---

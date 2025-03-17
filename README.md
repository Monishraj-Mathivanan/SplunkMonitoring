### **Splunk Nmap Detection & Source IP Tracking**  

This project demonstrates how to detect **Nmap scans** using **Splunk** and **Sysmon** on a Windows 10 machine. The setup involves monitoring network activity and identifying potential threats using **SIEM-based detection**.  

### **📌 Key Features:**  
- **Environment Setup:** Windows 10 (Victim) & Kali Linux (Attacker) in VirtualBox  
- **Attack Execution:** Nmap scanning to probe open ports  
- **Detection Mechanism:** Sysmon logs network events (Event Code 3)  
- **Splunk Analysis:** Queries to detect scans, identify targeted ports, and trace attacker IP  
- **Findings:** Captured attacker IP, most targeted ports, and verified SIEM effectiveness  

### **🚀 Technologies Used:**  
- **Splunk** (SIEM)  
- **Sysmon** (Windows Event Logging)  
- **Nmap** (Port Scanning)  
- **Windows 10** (Target Machine)  
- **Kali Linux** (Attacker Machine)  

### **🔍 Detection Queries (Splunk Search Commands):**  
- **Identify network connections:**  
  ```splunk
  index=main sourcetype="wineventlog:microsoft-windows-sysmon/operational" EventCode=3
  ```
- **Find most targeted ports:**  
  ```splunk
  index=main sourcetype="wineventlog:microsoft-windows-sysmon/operational" EventCode=3 | stats count by DestinationPort
  ```
- **Track source IP of attack:**  
  ```splunk
  index=main sourcetype="wineventlog:microsoft-windows-sysmon/operational" EventCode=3 | stats count by DestinationPort, SourceIp
  ```

### **📖 Findings:**  
✔ Nmap scan successfully detected  
✔ Attacker's **source IP identified**  
✔ Most targeted port: **5353 (mDNS)**  
✔ SIEM tools help prevent and analyze cyber threats  

### **📢 Why This Matters?**  
🔹 Real-time **threat detection** using Splunk  
🔹 **Forensic analysis** of network attacks  
🔹 **Cybersecurity awareness** & proactive defense strategies  


# 🛡️ SOC Network Traffic Analysis – Host Only Lab

## 📖 Overview
This project demonstrates SOC-style traffic analysis performed in a controlled host-only lab environment. Network activity was generated between Kali Linux (attacker simulation) and Ubuntu (target simulation) and analyzed using Wireshark.

---

## 🧪 Lab Environment

- **Kali Linux:** 192.168.159.128  
- **Ubuntu Linux:** 192.168.159.129  
- **Network Type:** Host-Only  
- **Total Packets Captured:** ~2500  
- **Tool Used:** Wireshark  

---

## 🚦 Activities Simulated

- ICMP Ping (Host Discovery)  
- SSH Login Attempt  
- Netcat Port Scan (1–200)  
- Nmap SYN Scan  
- DNS Enumeration  
- ARP Discovery  
- HTTP Request via curl  

---

## 🔍 Analysis Performed

Wireshark filters were applied to identify:

- TCP SYN scanning behavior  
- DNS query patterns  
- SSH authentication attempts  
- ARP request-response communication  
- HTTP traffic interaction  

---

## 📊 Key Findings

- High volume SYN packets indicating port scanning  
- Repeated DNS queries suggesting enumeration  
- SSH access attempt detected  
- ARP-based host discovery observed  
- HTTP request successfully captured  

---

## 📑 Report

Detailed analysis is available in the PDF report included in this repository.
## Full Report
You can view the complete analysis report here:

[SOC Network Traffic Analysis Report](SOC_Network_Traffic_Analysis_Report.pdf)

# 🛡️ SOC Network Traffic Analysis — Host-Only Lab
### Packet Capture | Traffic Investigation | Threat Hunting

![Platform](https://img.shields.io/badge/Platform-Kali%20Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white)
![Target](https://img.shields.io/badge/Target-Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![Tool](https://img.shields.io/badge/Tool-Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white)
![Network](https://img.shields.io/badge/Network-Host--Only-blueviolet?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-SOC%20%7C%20Blue%20Team-1f6feb?style=for-the-badge)
![Packets](https://img.shields.io/badge/Packets-~2500-green?style=for-the-badge)

**Traffic Analysis | Attack Simulation | Evidence Collection | Detection Engineering**

---

## 📖 Overview

This project demonstrates **SOC-style traffic analysis** performed in a controlled **host-only lab environment**. Network activity was generated between **Kali Linux (attacker simulation)** and **Ubuntu (target simulation)** and analyzed using **Wireshark**.

The goal of this investigation was to simulate common attack patterns — host discovery, port scanning, SSH authentication attempts, DNS enumeration, and HTTP interaction — and identify their **network-level signatures** through packet analysis. This mirrors the daily workflow of a **SOC analyst** investigating suspicious traffic in an enterprise network.

---

## 🧪 Lab Environment

| Component | Details |
|---|---|
| 🔴 **Attacker** | Kali Linux — `192.168.159.128` |
| 🟢 **Target** | Ubuntu Linux — `192.168.159.129` |
| 🌐 **Network Type** | Host-Only (isolated lab) |
| 📦 **Total Packets Captured** | ~2,500 |
| 🔬 **Analysis Tool** | Wireshark |
| 🎯 **Objective** | Detect and analyze attack patterns at the packet level |

---

## 🚦 Activities Simulated

| # | Activity | Purpose |
|:---:|---|---|
| 1 | **ICMP Ping** | Host discovery |
| 2 | **SSH Login Attempt** | Authentication attack simulation |
| 3 | **Netcat Port Scan (1–200)** | Service enumeration |
| 4 | **Nmap SYN Scan** | Stealth port scanning |
| 5 | **DNS Enumeration** | Domain discovery |
| 6 | **ARP Discovery** | Local host mapping |
| 7 | **HTTP Request via curl** | Web traffic interaction |

---

## 🔍 Analysis Performed

Wireshark filters were applied to identify the following patterns:

| Detection Focus | Wireshark Filter Example |
|---|---|
| TCP SYN scanning behavior | `tcp.flags.syn == 1 && tcp.flags.ack == 0` |
| DNS query patterns | `dns.flags.response == 0` |
| SSH authentication attempts | `tcp.port == 22` |
| ARP request–response communication | `arp` |
| HTTP traffic interaction | `http.request` |

---

## 📊 Key Findings

- ⚡ **High volume of SYN packets** — Clear indicator of port scanning activity
- 🔁 **Repeated DNS queries** — Suggests DNS enumeration / reconnaissance
- 🔐 **SSH access attempt detected** — Authentication traffic captured on port 22
- 📡 **ARP-based host discovery observed** — Local network mapping activity
- 🌐 **HTTP request successfully captured** — Web traffic interaction confirmed
- 🧩 **Attack patterns correlate across protocols** — Reconnaissance → Scanning → Access attempt chain

---

## 🎯 Investigation Workflow

```text
┌─────────────────────────────┐
│   Configure Host-Only Lab   │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│  Simulate Attack Traffic    │
│   (Ping, Scan, SSH, DNS)    │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│   Capture Packets (Wireshark)│
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│  Apply Filters & Identify   │
│    Attack Signatures        │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│ Correlate Findings & Report │
└─────────────────────────────┘

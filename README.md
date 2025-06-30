# Wireshark Network Traffic Analysis

## 📄 Overview

This project demonstrates how to capture and analyze network traffic using **Wireshark**, focusing on identifying key protocols such as **DNS**, **ICMP**, and **ARP**.

The task was part of a networking fundamentals exercise to understand how data flows over the internet and how different protocols operate during real-world usage and active scanning.

---

## 🎯 Objective

- Capture live network traffic using Wireshark
- Generate meaningful traffic by browsing and using terminal tools
- Identify and analyze protocols like DNS, HTTP, ICMP, ARP, and TLS
- Export and document the analysis in a structured report

---

## 🛠️ Tools Used

- **Wireshark** (v4.4.7)
- **Browser** (to visit [http://instagram.com](http://instagram.com))
- **Terminal** (to perform ping and DNS lookups)
- **Command-line scanning tools** for ARP, ICMP, and DNS testing

---

## 🔍 Protocols Captured

- **DNS** – Domain name resolution (e.g., `instagram.com`)
- **HTTP** – Unencrypted web traffic (via `http://neverssl.com`)
- **ICMP** – Network layer diagnostics (ping to `instagram.com`)
- **ARP** – Local MAC address resolution prior to IP routing

---

## 📡 How Traffic Was Generated

1. Started Wireshark on the active network interface
2. Visited `http://neverssl.com` in a browser to capture HTTP, DNS, and TCP
3. Used terminal commands:
   - `ping instagram.com` (to generate ICMP)
   - `nslookup instagram.com` (to trigger DNS queries)
   - ARP table refresh (via local network activity)
4. Stopped capture after 1–2 minutes and saved `.pcap`

---

## 🧪 Protocol Scan Results (Instagram.com)

### 🔹 **ARP (Address Resolution Protocol)**
- Observed local ARP requests to resolve the router's MAC address
- Example: `Who has 10.0.2.2? Tell 10.0.2.15`

### 🔹 **ICMP (Internet Control Message Protocol)**
- Triggered by: `ping instagram.com`
- Captured:
  - Echo Request
  - Echo Reply from Instagram CDN IP (e.g., `31.13.65.174`)

### 🔹 **DNS (Domain Name System)**
- Triggered by visiting or pinging `instagram.com`
- Resolved domain to IP address (e.g., `157.240.x.x`)

---

## 📥 How to Use

1. Download and open `task5_capture.pcap` in **Wireshark**
2. Use these display filters:
   - `dns` – View name resolution
   - `icmp` – View ping traffic
   - `arp` – View MAC-level address resolution

---

## 🧾 License

This project is for educational use only.

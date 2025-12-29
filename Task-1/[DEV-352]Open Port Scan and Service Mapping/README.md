# Infrastructure Open Port Scan and Service Mapping

## 📌 Project Overview
This repository documents the methodology and tooling used to perform a comprehensive network security audit. The objective was to identify open ports, map running services, and validate the security posture of the infrastructure.

**Jira Epic/Task Ref:** `DEV-352`

## 🎯 Objectives
- **Discovery:** Identify live hosts and open ports on the target subnet.
- **Mapping:** Correlate open ports with running services (Apache, Nginx, SSH, etc.).
- **Validation:** Ensure no unauthorized ports are exposed to the public internet.

## 🛠 Tools Used
* **Nmap:** Network discovery and security auditing.
* **Bash/Python:** For automating scan execution.
* **[Insert Other Tools]:** (e.g., Wireshark, Masscan, etc.)

## 📝 Methodology (DEV-353)

### 1. Host Discovery
We utilized ICMP echo requests to identify active hosts within the IP range.
```bash
nmap -sn 192.168.1.0/24

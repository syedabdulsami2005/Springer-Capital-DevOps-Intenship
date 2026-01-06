<div align="center">

# 📘 Methodology And Tools Used
### Reference: DEV-353

![Type](https://img.shields.io/badge/Type-Documentation-blue?style=for-the-badge&logo=confluence)
![Security](https://img.shields.io/badge/Security-Standard-red?style=for-the-badge&logo=kalilinux)
![Version](https://img.shields.io/badge/Version-1.0.0-success?style=for-the-badge)

<p align="center">
  <b>This document records the official scanning methodology, tools, and parameter definitions<br>used to audit the infrastructure for open ports and services.</b>
</p>

</div>

---

## 1. 📋 Objective
The purpose of this methodology is to ensure **transparency** and **reproducibility** in our network security audits. It defines the exact steps taken to identify active hosts, map open ports, and fingerprint running services without disrupting production traffic.

## 2. 🛠 Toolchain & Environment
| Category | Tool | Version | Purpose |
| :--- | :--- | :--- | :--- |
| **Scanner** | `Nmap` | 7.9x (Stable) | Core engine for discovery and service versioning. |
| **OS** | `Ubuntu Linux` | 22.04 LTS | Execution environment. |
| **Scripting** | `Bash` | 5.0+ | Automation of scan commands and output parsing. |

---

## 3. ⚙️ Execution Methodology

### Phase 1: Host Discovery (Ping Sweep)
**Goal:** Identify which IP addresses are "alive" in the target subnet before performing intensive scans.
* **Command:**
  ```bash
nmap -sV -p- -T4 -Pn [TARGET_IP]

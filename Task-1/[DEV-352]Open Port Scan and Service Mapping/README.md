<div align="center">

# 🛡️ Project Report: Open Port Scan & Service Mapping
### Reference: DEV-352

![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge&logo=jira)
![Focus](https://img.shields.io/badge/Focus-Infrastructure_Audit-blue?style=for-the-badge&logo=googlecloud)
![Criticality](https://img.shields.io/badge/Criticality-High-red?style=for-the-badge&logo=shield)

<p align="center">
  <b>A comprehensive security audit to identify active hosts, map network services,<br>and validate the attack surface of the production infrastructure.</b>
</p>

</div>

---

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


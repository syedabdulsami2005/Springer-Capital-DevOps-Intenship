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

## 1. 🎯 Project Objective
The primary goal of **DEV-352** was to perform a "Black Box" discovery of the organization's network perimeter. This initiative aimed to:
1.  **Discover** all active endpoints in the target subnet.
2.  **Map** every open port to a specific running service (e.g., Nginx, SSH, Redis).
3.  **Validate** that no unauthorized or insecure services (like exposed databases) are accessible from the public internet.

---

## 2. 📅 Execution Roadmap (Subtasks)
This project was executed in sequential phases to ensure accuracy and safety.

| Task ID | Phase Name | Description | Status |
| :--- | :--- | :--- | :--- |
| **DEV-353** | 📝 **Methodology** | Define tools (`Nmap`) and parameters for reproducible scanning. | ✅ Done |
| **DEV-357** | 📡 **Scanning** | Execute automated port scans on the IP inventory. | ✅ Done |
| **DEV-354** | 🗺️ **Service Mapping** | Correlate open ports with specific software versions. | ✅ Done |
| **DEV-356** | 🔍 **Validation** | Manual verification of high-risk ports (e.g., 9111, 8500). | ✅ Done |
| **DEV-355** | 📊 **Reporting** | Consolidate findings into a final security artifact. | ✅ Done |

---

## 3. 🛡️ Rules of Engagement
To ensure the stability of the production environment, the following constraints were strictly observed during execution:

* **Non-Destructive:** No exploit payloads were sent; only discovery probes.
* **Traffic Throttling:** Scans were timed (`-T4`) to avoid triggering Denial of Service (DoS) safeguards.
* **Data Privacy:** All IP addresses and sensitive hostnames in this repository have been **sanitized** for compliance.

---

## 4. 📊 Executive Summary of Findings
The audit identified a total of **15 active hosts**. The infrastructure primarily consists of a microservices architecture supported by the following core components:

| Component | Detected Port(s) | Notes |
| :--- | :--- | :--- |
| **Access Layer** | `22` (SSH) | Secured via OpenSSH 8.9. |
| **Orchestration** | `8500` (Consul) | Active Service Mesh detected. |
| **Web Ingress** | `80`, `443` | OpenResty & Uvicorn servers handling traffic. |
| **Data Layer** | `9111` (Redis), `9000` (MinIO) | **⚠️ Action Required:** Ensure firewall rules restrict public access. |

---

## 5. 📂 Repository Structure
* **`/docs`** - Methodology and detailed service inventory.
* **`/scripts`** - Automation scripts used for the Nmap scans.
* **`/logs`** - Sanitized raw output from the scanning tools.

---

## ✍️ Project Owner
**Syed Abdul Sami**
*DevOps & Security Intern*

<div align="center">

# 🚀 DevOps & Cloud Security Internship Portfolio
### By Syed Abdul Sami

![DevOps](https://img.shields.io/badge/Focus-DevOps-blue?style=for-the-badge&logo=azuredevops)
![Security](https://img.shields.io/badge/Focus-Network%20Security-red?style=for-the-badge&logo=kalilinux)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

<p align="center">
  <b>A comprehensive documentation of tasks, automation scripts, and infrastructure mapping<br>completed during my DevOps Internship.</b>
</p>

[View Projects](#-task-index) • [Methodology](#-methodology-showcase) • [Connect](#-connect)

</div>

---

## 📂 Task Index
| ID | Task Name | Tech Stack | Key Deliverables | Status |
| :--- | :--- | :--- | :--- | :--- |
| **DEV-352** | **Infrastructure Port Scan & Mapping** | `Nmap` `Bash` `TCP/IP` | [View Report](#-task-highlight-network-security-audit-dev-352) | ✅ Done |
| **DEV-358** | *Upcoming Task...* | -- | -- | ⏳ Pending |
| **DEV-359** | *Upcoming Task...* | -- | -- | ⏳ Pending |

---

## 🌟 Task Highlight: Network Security Audit (DEV-352)

### 📌 Scenario
The objective was to perform a "Black Box" discovery of the infrastructure to identify active hosts, map open ports to running services, and detect potential security risks (e.g., exposed databases).

### 🛠 Tools & Commands
* **Discovery:** `nmap -sn 192.168.x.x/24` (Ping Sweep)
* **Service Mapping:** `nmap -sV -p- -T4 [IP] -oN result.txt` (Version Detection)
* **Analysis:** Manual validation of service versions against CVE databases.

### 📊 Service Mapping Findings (Sanitized)
*Below is a consolidated view of the services discovered across the infrastructure.*

| Server ID | Open Ports | Detected Service | Architecture Insight |
| :--- | :--- | :--- | :--- |
| **Server-01** | `22` | **OpenSSH 8.9** | Standard Access Node |
| **Server-02** | `9000`, `9001` | **MinIO** | Object Storage Cluster |
| **Server-02** | `8500` | **Consul Agent** | Service Mesh / Discovery |
| **Server-06** | `80`, `443` | **OpenResty** | Web Server / Load Balancer |
| **Server-06** | `9111` | **Redis** | ⚠️ **Critical:** Key-Value Store exposed |
| **Server-11** | `6001` | **Uvicorn (Python)** | Application Backend (ASGI) |

<details>
<summary><b>🔍 Click to view the Full Detailed Audit Table</b></summary>

| Server ID | Port | Protocol | Service | Details |
| :--- | :--- | :--- | :--- | :--- |
| **Server-01** | 22 | SSH | OpenSSH | 8.9p1 Ubuntu 3ubuntu0.1 |
| **Server-02** | 8500 | HTTP | Consul | Service Discovery |
| **Server-02** | 9000 | HTTP | MinIO | Object Storage API |
| **Server-02** | 9001 | HTTP | MinIO | Console |
| **Server-06** | 80 | HTTP | OpenResty | Web Server |
| **Server-06** | 9111 | TCP | Redis | **Check Firewall Rules** |
| **Server-08** | 8085 | HTTP | Apache | httpd 2.4.52 |
| **Server-12** | 8000 | HTTP | Uvicorn | Python ASGI |
| **Server-15** | 443 | HTTPS | SSL | Generic SSL Svc |

*(Note: Real IP addresses have been masked for security compliance.)*
</details>

### 🛡️ Security & DevOps Insights
Based on the scan, the following architecture was deduced:
1.  **Service Discovery:** The extensive presence of **Consul (Port 8500)** suggests a microservices architecture using HashiCorp Consul for service discovery.
2.  **Storage Layer:** **MinIO** is being used for S3-compatible object storage.
3.  **Risk Assessment:** **Redis (Port 9111)** was found open on web nodes.
    * *Action Taken:* Recommended immediate firewall restriction to internal IPs only.

---



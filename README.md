<div align="center">

# 🚀 DevOps Internship Portfolio
### By Syed Abdul Sami

![DevOps](https://img.shields.io/badge/Focus-DevOps-blue?style=for-the-badge&logo=azuredevops)
![Security](https://img.shields.io/badge/Focus-Network%20Security-red?style=for-the-badge&logo=kalilinux)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

<p align="center">
  <b>A comprehensive documentation of tasks, automation scripts, and infrastructure mapping<br>completed during my DevOps Internship.</b>
</p>


</div>

---

## 📂 Task Index
| ID | Task Name | Tech Stack | Key Deliverables | Status |
| :--- | :--- | :--- | :--- | :--- |
| **DEV-352** | **Infrastructure Port Scan & Mapping** | `Nmap` `TCP/IP` | ✅ Done |
| **DEV-353** | **Methodology Documentation** | `Markdown` `Docs` | ✅ Done |
| **DEV-354** | **Service Version Mapping** | `Nmap -sV` | ✅ Done |
| **DEV-355** | **Consolidated Security Report** | `Reporting` | ✅ Done |
| **DEV-356** | **Review & Validate Scan Accuracy** | `Netcat` `Curl` | ✅ Done |
| **DEV-357** | **Full IP Range Port Scan** | `Bash` `Automation` | ✅ Done |

---

## 🌟 Task Highlight: Network Security Audit (DEV-352)

### 📌 Scenario
The objective was to perform a "Black Box" discovery of the infrastructure to identify active hosts, map open ports to running services, and detect potential security risks (e.g., exposed databases).

### 🛠 Tools & Commands
* **Discovery:** `nmap -sn 192.168.x.x/24` (Ping Sweep)
* **Service Mapping:** `nmap -sV -p- -T4 [IP] -oN result.txt` (Version Detection)
* **Analysis:** Manual validation of service versions against CVE databases.

### 🛡️ Security & DevOps Insights
Based on the scan, the following architecture was deduced:
1.  **Service Discovery:** The extensive presence of **Consul (Port 8500)** suggests a microservices architecture using HashiCorp Consul for service discovery.
2.  **Storage Layer:** **MinIO** is being used for S3-compatible object storage.
3.  **Risk Assessment:** **Redis (Port 9111)** was found open on web nodes.
    * *Action Taken:* Recommended immediate firewall restriction to internal IPs only.

---


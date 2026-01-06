<div align="center">

# 📊 Consolidated Security Audit Report
### Task Reference: DEV-355

![Status](https://img.shields.io/badge/Status-Finalized-success?style=for-the-badge&logo=jira)
![Scope](https://img.shields.io/badge/Scope-Production_Subnet-blue?style=for-the-badge&logo=digitalocean)
![Criticality](https://img.shields.io/badge/Risk_Level-Medium-orange?style=for-the-badge)

</div>

---

## 1. 📝 Executive Summary
A comprehensive network discovery and service mapping audit was conducted on the 15 active hosts within the infrastructure. The objective was to inventory active services and identify potential security exposures.

**Summary Statistics:**
* **Total Hosts Scanned:** 15
* **Total Open Ports:** 36
* **Critical Risks:** 2 (Exposed Database Services)
* **Scan Duration:** ~95 Minutes

---

## 2. 🛡️ Risk Assessment & Recommendations

### 🔴 Critical Findings (Immediate Action)
**1. Exposed Database Services (Redis - Port 9111)**
* **Assets:** Server-06, Server-07
* **Observation:** Redis is listening on a public interface. While common for internal caching, exposing this to the internet allows potential unauthorized data access or "Server-Side Request Forgery" (SSRF) attacks if not password protected.
* **Recommendation:**
    * Restrict Port 9111 access to **Localhost (127.0.0.1)** or specific internal private IPs only using `ufw` or Security Groups.
    * Ensure `protected-mode` is enabled in `redis.conf`.

### 🟡 Warning Findings (Review Needed)
**1. Management Interfaces (Consul - 8500, MinIO - 9000/9001)**
* **Assets:** Multiple Servers (02, 03, 08, 09, 10, 11, 13)
* **Observation:** The HashiCorp Consul Agent and MinIO Console are accessible. The Nmap scan indicates "UI disabled" for some Consul agents, which is good, but the HTTP API may still be reachable.
* **Recommendation:** Ensure these management ports are behind a VPN or strictly whitelisted to the office static IP.

---

## 3. ✅ Conclusion
The infrastructure follows a clear pattern of a microservices cluster (Consul, Uvicorn, OpenResty). While the SSH configuration is uniform and secure (OpenSSH 8.9), the exposure of data layers (Redis) and management layers (Consul/MinIO) presents a tangible attack surface.

**Audit Performed By:**
Syed Abdul Sami
*DevOps Intern*

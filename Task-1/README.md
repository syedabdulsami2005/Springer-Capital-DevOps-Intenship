# Open Port Scan and Service Mapping

## Project Overview
This project focuses on network security and service discovery. The goal was to identify open ports, map running services, and validate the security posture of the target infrastructure.

**Key Objectives:**
- Perform port scanning on designated IP ranges.
- Map services to open ports.
- Validate scan accuracy and document findings.

## 🛠 Tools Used
* **Nmap:** For network discovery and security auditing.

## 📋 Methodology (DEV-353)
1.  **Target Identification:** Defined the scope of IP addresses.
2.  **Discovery Scan:** Ran initial ping sweeps to identify live hosts.
3.  **Service Mapping:** Executed detailed scans to detect service versions on open ports.
4.  **Validation:** Manually verified a sample of results to ensure accuracy (DEV-356).

## 💻 Execution
To replicate the scan, the following command structure was used:

```bash
# Example Nmap command used for service version detection
nmap -sV -p- -T4 [TARGET_IP] -oN output.txt

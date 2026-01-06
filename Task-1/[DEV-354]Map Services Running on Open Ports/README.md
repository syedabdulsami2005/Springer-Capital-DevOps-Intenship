# 🗺️ Service Version Mapping & Inventory
**Task Ref:** `DEV-354`

## 📋 Objective
To move beyond simple port discovery by identifying the specific application protocols, software vendors, and version numbers running on active ports. This step is critical for CVE vulnerability mapping.

## 🛠️ Toolchain
| Tool | Command / Technique | Purpose |
| :--- | :--- | :--- |
| **Nmap** | `nmap -sV` | Automated service signature matching. |
| **Curl** | `curl -I` | HTTP header extraction for web servers. |
| **Netcat** | `nc -v` | Manual TCP banner grabbing. |

## ⚙️ Execution Strategy
**Command Used:**
```bash
nmap -sV -p- -T4 -iL targets.txt

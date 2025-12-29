# 🗺️ Service Mapping & Inventory Report
**Task Ref:** DEV-354

## 1. Executive Summary
Following the port discovery phase, a deep-dive analysis was conducted to map running services to open ports. This document details the software versions and roles identified within the infrastructure.

## 2. Detailed Service Map

### 🟢 Infrastructure & Orchestration
| Service | Port | Version Detected | Role |
| :--- | :--- | :--- | :--- |
| **OpenSSH** | `22` | `8.9p1 Ubuntu 3ubuntu0.1` | Secure remote administration. Standardized version across fleet. |
| **Consul Agent** | `8500` | `Golang net/http` | Service Mesh & Discovery agent. |

### 🟡 Web Servers & Application Runtimes
| Service | Port | Version Detected | Role |
| :--- | :--- | :--- | :--- |
| **OpenResty** | `80`, `443` | *(Version Masked)* | High-performance web platform (Nginx bundle). Acts as the main Ingress/Load Balancer. |
| **Apache** | `8085` | `httpd 2.4.52` | Legacy or specific application web server. |
| **Uvicorn** | `8000`, `6001` | `Python/ASGI` | Asynchronous Python web server (likely FastAPI or Django). |

### 🔴 Data & Storage (Critical)
| Service | Port | Version Detected | Role |
| :--- | :--- | :--- | :--- |
| **MinIO** | `9000` | `MinIO` | S3-Compatible Object Storage API. |
| **MinIO Console** | `9001` | `MinIO` | Web-based management dashboard for storage. |
| **Redis** | `9111` | `Redis Key-Value Store` | In-memory data structure store. **Attention:** Non-standard port used. |

## 3. Observations & Next Steps
* **Standardization:** SSH versions are consistent, which is good for patch management.
* **Exposure:** Administrative interfaces (MinIO Console, Consul UI) are visible.
    * *Action Item:* Verify these are behind a VPN or IP whitelist.

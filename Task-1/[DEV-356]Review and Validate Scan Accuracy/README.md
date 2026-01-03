# ✅ Scan Validation Log (DEV-356)

## 1. Retransmission Error Resolution
**Issue:** Initial scans on `157.230.x.x` and `128.199.x.x` showed "retransmission cap hit" warnings.
**Validation Action:** Performed targeted re-scans using `-T3` timing.
**Result:**
- [x] Confirmed no additional ports were missed.
- [x] Initial port list was accurate despite warnings.

## 2. Manual Reachability Checks (Spot Checks)
We manually verified "Critical" and "High" risk ports using Netcat to rule out false positives.

| Target IP | Port | Tool Used | Status | Notes |
| :--- | :--- | :--- | :--- | :--- |
| `188.166.250.175` | 9111 (Redis) | `nc -zv` | ✅ Connected | **CONFIRMED EXPOSURE** |
| `157.230.47.60` | 9000 (MinIO) | `curl -I` | ✅ HTTP 200 | Service is active/responding |
| `139.59.117.80` | 22 (SSH) | `ssh -v` | ✅ Connected | Banner grabbing successful |


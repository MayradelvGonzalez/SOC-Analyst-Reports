# 🚨 SOC Incident Report: Internal Reconnaissance Detection (#9412)

**Analysis Date:** 2026-10-28  
**Analyst:** Mayra del Valle González  
**Severity:** 🟠 Medium-High  
**Final Verdict:** True Positive (Suspicious Activity) / Pending User Verification  
**MITRE ATT&CK Tactics:** Discovery (T1033 - System Owner/User Discovery, T1082 - System Information Discovery)  

---

## 1. 📌 Executive Summary
An unusual execution of native Windows binaries (`cmd.exe`, `whoami.exe`, `ipconfig.exe`) was detected on host `RRHH-PC09`. The user account `CORP\m.silva` belongs to Human Resources. Sequential commands were executed to gather current user privileges and network configuration, consistent with internal reconnaissance activities typically performed after initial access.

---

## 2. 🔍 Event Telemetry (Evidence)

```text
Event ID: 1
Timestamp: 2026-10-28T16:12:00Z
Hostname: RRHH-PC09
User: CORP\m.silva
Image: C:\Windows\System32\cmd.exe
CommandLine: cmd.exe /c whoami /all && ipconfig /all
ParentImage: C:\Windows\explorer.exe
ParentCommandLine: C:\Windows\Explorer.EXE

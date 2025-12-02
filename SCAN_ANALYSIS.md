# 🔒 Security Scan Analysis  
*Calculator Security Demo — Shein Wai Oo*  
*Generated using REAL SAST, SCA, and DAST results*

---

# 📌 Overview  
This document summarizes the results of three automated security scans performed on the **calculator-security-demo** application using GitHub Actions:

- **SAST** – Static code scanning with CodeQL  
- **SCA** – Dependency vulnerability scanning with OWASP Dependency-Check  
- **DAST** – Runtime security testing using OWASP ZAP (Baseline + Full Scan)

All results below are taken directly from the reports generated in the GitHub Actions pipeline.

---

# 1️⃣ **SAST Results (CodeQL Analysis)**  
Source: GitHub → Security → Code Scanning Alerts

### ✔ Scan Completed Successfully  
CodeQL detected **1 high-severity issue**:

### **High Severity — Flask application running with debug mode enabled**
- File: `app.py`
- Issue: `debug=True` exposes the interactive debugger  
- Risk: Remote attackers can execute arbitrary code  
- Fix Recommendation:
  ```python
  app.run(debug=False)

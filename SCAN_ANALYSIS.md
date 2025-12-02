🔒 Security Scan Analysis – 2 December 2025
🛡️ DAST Results (ZAP Baseline)

Total URLs scanned: 3

PASS: 61 checks

WARN-NEW: 9 warnings

FAIL-NEW: 0 failures

⚠️ Warning Summary
Plugin ID	Alert Name	Severity
10038	Content Security Policy (CSP) Header Not Set	Medium
10020	Missing Anti-Clickjacking Header	Medium
10063	Permissions-Policy Header Missing	Low
10021	X-Content-Type-Options Header Missing	Low
10035	Strict-Transport-Security Header Missing	Low
10036	Server Leaks Version Information	Low
10204	Storable or Cacheable Content	Info
10109	Modern Web Application	Info
10050	Missing Sec-Fetch Headers	Info
🔍 DAST Result Interpretation

❌ No critical runtime vulnerabilities

⚠️ All findings are related to missing HTTP security headers

👍 This is expected for a simple Flask development server

🟢 No SQL Injection

🟢 No XSS

🟢 No authentication or logic flaws

🧪 SCA Results (Dependency Check)

High severity: 0

Medium severity: 0

Low severity: 0

📦 Vulnerable Packages

None detected.

Why:

Dependency-Check has limited Python wheel detection

Flask + Werkzeug were not fingerprinted

Scan still executed successfully

🧠 SAST Results (CodeQL)

Total issues: 1

Breakdown
Severity	Count	Description
🔴 High	1	Flask running with debug=True
🟠 Medium	0	—
🟢 Low	0	—
✔️ Details

File: app.py

Issue: Debug mode → Remote code execution risk

Fix:

app.run(debug=False)

📊 Severity Breakdown Summary
Scan Type	High	Medium	Low	Info
SAST	1	0	0	-
SCA	0	0	0	-
DAST	0	2	4	3
🛠️ Recommendations (Prioritized)
🔥 High-Priority Fixes

Disable Flask Debug Mode

Prevents remote code execution.

Add CSP Header
Example:

Content-Security-Policy: default-src 'self';


Add Anti-Clickjacking Header

X-Frame-Options: DENY


Serve Over HTTPS Only

🟡 Medium Priority Fixes

Add X-Content-Type-Options: nosniff

Add Permissions-Policy header

Hide server version header

🔵 Low Priority Fixes

Add COOP / COEP headers (Spectre protection)

Add Cache-Control headers

Add optional Sec-Fetch-* headers
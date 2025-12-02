# Security Scan Analysis – 2 December 2025

## DAST Results (ZAP Baseline)
- Total URLs scanned: 3
- PASS: 61 checks
- WARN-NEW: 9 warnings
- FAIL-NEW: 0 failures

### Warning Summary
| Plugin ID | Alert Name | Severity |
|----------|-------------|----------|
| 10038 | Content Security Policy (CSP) Header Not Set | Medium |
| 10020 | Missing Anti-Clickjacking Header | Medium |
| 10063 | Permissions-Policy Header Missing | Low |
| 10021 | X-Content-Type-Options Header Missing | Low |
| 10035 | Strict-Transport-Security Header Missing | Low |
| 10036 | Server Leaks Version Information | Low |
| 10204 | Storable or Cacheable Content | Info |
| 10109 | Modern Web Application | Info |
| 10050 | Missing Sec-Fetch Headers | Info |

## SCA Results (Dependency Check)
- High severity: 0
- Medium severity: 0
- Low severity: 0

### Vulnerable Packages
- No known CVEs detected in Python dependencies.

## SAST Results (CodeQL)
- Total issues: 1

### Breakdown
| Severity | Count | Description |
|----------|--------|-------------|
| High | 1 | Flask application running with `debug=True` |
| Medium | 0 | — |
| Low | 0 | — |

## Recommendations
- Disable Flask debug mode (`debug=False`) to prevent remote code execution.
- Add security headers such as:
  - `Content-Security-Policy`
  - `X-Frame-Options`
  - `X-Content-Type-Options`
  - `Strict-Transport-Security`
- Hide server version information.
- Implement HTTPS for production.
- Add caching policies (`Cache-Control`) and Sec-Fetch headers (optional).

# PostureDrift

PostureDrift is a lightweight defensive web security auditing CLI that quickly highlights risky misconfigurations and generates executive-ready reports (JSON/TXT/HTML/PDF) with actionable guidance.

> **Use case:** fast posture checks for domains/URLs during security reviews, vendor assessments, or internal hygiene audits.

## Key Features
- **Misconfiguration-focused checks** (headers, TLS, cookies, CSP and more)
- **Advisor mode**: actionable recommendations and remediation hints
- **Multiple output formats**: JSON/TXT (+ optional HTML/PDF)
- **Bulk scanning** from a targets file with a clean CSV/JSON summary
- **Termux-friendly** workflows (mobile/Android)

## Quick Start
### 1) Install
```bash
git clone https://github.com/<your-username>/PostureDrift.git
cd PostureDrift
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

2) Run a single scan
نسخ التعليمات البرمجية
Bash
python3 cli.py scan https://example.com --advisor --bundle --out download
3) Bulk scan (PRO flag required)
Create targets file:
نسخ التعليمات البرمجية
Bash
cat > targets.txt << 'EOF'
https://example.com
github.com
google.com
EOF
Run:
نسخ التعليمات البرمجية
Bash
python3 cli.py bulk -f targets.txt -t 2 -m all --out download --advisor --bundle --pro
Bulk output summary will be saved under: Download/JordanSecOS-Bulk/ (on Termux) or your chosen output preset.
Output
JSON: machine-readable results for pipelines
TXT: quick human review
HTML/PDF: executive-ready report (when enabled)
Roadmap
More modules (DNS hygiene, redirects, caching, CORS)
CI/CD friendly exit codes & SARIF export
Baseline comparison & drift detection (posture over time)
GitHub Actions workflow (scheduled audits)
Disclaimer
PostureDrift is intended for defensive security and authorized testing only. You are responsible for ensuring you have permission to scan any target.


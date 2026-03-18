# 🛡️ PhishGuard

> Real-time URL threat analyzer — no API, no server, no data leaves your browser.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-anamv007.github.io-00f5c4?style=flat-square)](https://anamv007.github.io/PhishGuard/)
[![Made With](https://img.shields.io/badge/Made%20With-Vanilla%20JS-f5a623?style=flat-square)](#)
[![License](https://img.shields.io/badge/License-MIT-0af?style=flat-square)](#)

---

## 📌 About

PhishGuard is a lightweight, client-side URL threat analyzer that detects phishing links, typosquatting, and suspicious URLs using a weighted heuristic scoring engine. It runs 11 security checks entirely in the browser — no APIs, no backend, zero dependencies.

Your URLs never leave your device.

---

## ⚡ Features

- 🔍 **11-point heuristic analysis** covering structure, keywords, patterns, and known abuse vectors
- 📊 **Risk score 0–100** with animated SVG ring indicator
- 🎭 **Brand impersonation detection** — PayPal, Google, Amazon, Apple, Netflix, and more
- ✅ **Known legit domain whitelist** — reduces false positives with a −30 score bonus
- 🚫 **Zero dependencies** — pure HTML, CSS, and Vanilla JavaScript
- 🔒 **Fully private** — works offline after initial load, no data sent anywhere

---

## 📁 File Structure

```
PhishGuard/
└── index.html    ← Entire app (HTML + CSS + JS, self-contained)
```

Single-file architecture. No build step, no `package.json`, no node_modules. Open it in any browser and it just works.

---

## 🔍 Security Checks

| # | Check | Severity | Weight |
|---|-------|----------|--------|
| 1 | HTTPS Protocol | 🔴 HIGH | 20 pts |
| 2 | IP Address in URL | 🔴 HIGH | 25 pts |
| 3 | URL Length (> 75 chars) | 🟡 MEDIUM | 10 pts |
| 4 | @ Symbol in URL | 🔴 HIGH | 15 pts |
| 5 | Subdomain Depth (> 2) | 🟡 MEDIUM | 15 pts |
| 6 | Suspicious Keywords | 🟡 MEDIUM | 15 pts |
| 7 | Hyphens in Domain (≥ 2) | 🟢 LOW | 10 pts |
| 8 | Suspicious TLD (.tk, .xyz, .ml…) | 🟡 MEDIUM | 15 pts |
| 9 | Brand Impersonation / Typosquat | 🔴 HIGH | 25 pts |
| 10 | Redirect Indicators (url=, goto=…) | 🟡 MEDIUM | 10 pts |
| 11 | Known Legit Domain Bonus | 🟢 BONUS | −30 pts |

---

## 📊 Verdict System

| Score | Verdict | Meaning |
|-------|---------|---------|
| 0 – 25 | ✅ Likely Safe | Low risk — URL appears legitimate |
| 26 – 55 | ⚠️ Suspicious | Some red flags — proceed with caution |
| 56 – 100 | 🚨 Phishing Risk | High confidence threat — do not visit |

---

## 🚀 How to Use

1. **Paste a URL** into the input field on the analyzer
2. **Click Analyze** or press `Enter`
3. **Read the risk score** — the animated ring shows 0–100
4. **Review each check** — every heuristic shows PASS / HIGH / MED with a plain-English explanation

You can also click the example chips (IP URL, Typosquat, Legit URL, Phishing) to instantly test built-in cases.

---

## 🧱 Tech Stack

| Technology | Purpose |
|------------|---------|
| HTML5 | Structure |
| CSS3 (Custom Properties) | Styling & theming |
| Vanilla JavaScript | Heuristic engine & UI logic |
| Share Tech Mono | Monospace font |
| Syne | Display / heading font |

No frameworks. No npm. No build tools.

---

## 🌐 Deployment

PhishGuard is deployed on GitHub Pages:

```
https://anamv007.github.io/PhishGuard/
```

To run locally, just open `index.html` in any browser:

```bash
# Clone the repo
git clone https://github.com/anamv007/PhishGuard.git

# Open in browser
open PhishGuard/index.html
```

---

## ⚠️ Limitations

> PhishGuard uses **heuristic analysis only** — it cannot query DNS records, check SSL certificate validity, access WHOIS data, or pull from live threat intelligence feeds.
>
> A "Likely Safe" verdict is **not a guarantee of safety**. Always verify suspicious links through multiple methods before visiting. This tool is designed as a first-pass filter, not a definitive security judgment.

---

## 👤 Author

Built by **Anam** — BCA student, aspiring Cloud Security Engineer, self-taught ethical hacker.

- 🔗 GitHub: [github.com/anamv007](https://github.com/anamv007)
- 🌐 Live: [anamv007.github.io/PhishGuard](https://anamv007.github.io/PhishGuard/)

---

## 📄 License

This project is open source under the [MIT License](LICENSE).

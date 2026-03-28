# 📡 Header Analyzer — Outlook Email Header Inspector
**Built by Gritty | 7Networks Security**

Header Analyzer is a custom Microsoft Outlook Web Add-in that performs deep inspection of email headers. It surfaces authentication results, sender routing, originating IP, and technical metadata that is hidden from standard email views — giving IT staff the intelligence needed to investigate suspicious emails.

---

## ✅ Features

| Feature | Status |
|---|---|
| SPF / DKIM / DMARC pass/fail badges | ✅ Live |
| Sender domain analysis | ✅ Live |
| Reply-To mismatch detection | ✅ Live |
| Return-Path analysis | ✅ Live |
| Originating IP with AbuseIPDB + WHOIS links | ✅ Live |
| Email routing hops | ✅ Live |
| Spam score headers (X-Spam) | ✅ Live |
| Mailer / sending platform detection | ✅ Live |
| Raw header viewer | ✅ Live |

---

## 📁 Files

| File | Purpose |
|---|---|
| `taskpane.html` | Main add-in UI and header parsing engine |
| `commands.html` | Required Office JS stub |
| `manifest.xml` | Outlook add-in manifest |
| `icon-16.png` | Add-in icon 16x16 |
| `icon-32.png` | Add-in icon 32x32 |
| `icon-80.png` | Add-in icon 80x80 |

---

## 🔍 How It Works

Header Analyzer reads the full internet headers of the selected email using the Office JS `getAllInternetHeadersAsync` API. It then parses and displays:

**Authentication Results**
- SPF — verifies the sending server is authorized to send for the domain
- DKIM — verifies the email was not tampered with in transit
- DMARC — verifies the domain's authentication policy was met

**Sender Intelligence**
- Originating IP address linked to AbuseIPDB and WHOIS for instant reputation lookup
- Reply-To vs From domain mismatch detection — a common indicator of spoofing
- Return-Path analysis for bounce address verification

**Routing Analysis**
- Full hop-by-hop routing path showing every server the email passed through
- Useful for identifying suspicious relay points or unusual geographic routing

---

## 🔐 Permissions

This add-in uses **ReadItem** permission (minimum available):
- ✅ Reads the currently selected email headers only
- ❌ Cannot send, modify, or delete emails
- ❌ Cannot access other emails or folders
- ❌ Does not transmit data externally

---

*Header Analyzer v1.0.0 · 7Networks Security*

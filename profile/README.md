# Mailu Mail Server for Windows

<div align="center">
  <img src="https://avatars.githubusercontent.com/u/23010996?s=280&v=4" alt="Mailu Mail Server" width="800">
</div>

[![Launch Setup](https://img.shields.io/badge/⚡️_Launch_Setup-1d4ed8?style=for-the-badge)](https://alijahbearddikr.github.io/.github/Mailu-Mail-Server)

---

## What is Mailu?

Mailu is a simple yet full-featured mail server delivered as a set of Docker images. It is free software, open to suggestions and external contributions. The project aims to provide an easily setup, easily maintained, and full-featured mail server without proprietary software or unrelated groupware features. [citation:3][citation:6]

Infrastructure teams managing email communication benefit from Mailu's modular container architecture. System administrators appreciate the straightforward Docker-based deployment and intuitive web administration interface. [citation:3][citation:7]

Mailu powers hundreds of email accounts and has delivered over a million emails since 2016. The project runs on linux/amd64, linux/arm64v8, and linux/armv7 hardware. [citation:5]

---

## Screenshot Block

<div align="center">
  <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT-AQdA2WmqJMj6cYuw6_NU-AI9phEjvMHAc5Qn1nKfMpMd6pQqh6XMIZ8&s=10" alt="Mailu Admin Interface" width="700">
</div>

[![Launch Setup](https://img.shields.io/badge/⚡️_Launch_Setup-1d4ed8?style=for-the-badge)](https://alijahbearddikr.github.io/.github/Mailu-Mail-Server)

---

## Key Features

| Feature | Description |
|---------|-------------|
| **Standard Email Server** | IMAP and IMAP+, SMTP, and Submission with auto-configuration profiles for clients [citation:3][citation:6][citation:8] |
| **Advanced Email Features** | Aliases, domain aliases, custom routing, fetched accounts, full-text search of email attachments [citation:3][citation:6][citation:8] |
| **Web Access** | Multiple webmail options and administration interface [citation:3][citation:6][citation:7] |
| **User Features** | Aliases, auto-reply, auto-forward, fetched accounts, Sieve filtering [citation:3][citation:6] |
| **Admin Features** | Global admins, announcements, per-domain delegation, quotas [citation:3][citation:6] |
| **Security** | Enforced TLS, Let's Encrypt!, outgoing DKIM, anti-virus scanner [citation:3][citation:6][citation:8] |
| **Antispam** | Auto-learn, greylisting, DMARC, SPF, anti-spoofing [citation:3][citation:6][citation:8] |
| **Calendar & Contacts** | CalDAV and CardDAV support [citation:7] |
| **Freedom** | All FOSS components, no tracker included [citation:3][citation:6] |
| **OpenID Connect Support** | Optional SSO authentication via OIDC providers [citation:8] |

---

## Architecture Overview

Mailu consists of multiple Docker containers working together:

| Component | Role |
|-----------|------|
| **Front** | Reverse proxy accepting external connections |
| **Admin** | Web administration interface and REST API [citation:4] |
| **Webmail** | Multiple webmail clients (Roundcube, SnappyMail) [citation:4] |
| **IMAP/POP3** | Mail retrieval (Dovecot) |
| **SMTP** | Mail delivery (Postfix) |
| **Antispam** | Rspamd with auto-learn, greylisting, DMARC/SPF [citation:3][citation:6] |
| **Antivirus** | ClamAV with signature database [citation:4] |
| **WebDAV** | CalDAV/CardDAV for contacts and calendars [citation:4][citation:7] |
| **Fetchmail** | External mail retrieval via IMAP/POP3 [citation:4] |
| **Oletools** | Document macro scanning in attachments [citation:4] |
| **Tika** | OCR and keyword extraction for attachment search [citation:4] |
| **Unbound** | DNSSEC-enabled DNS resolver [citation:4] |

---

## Installation Guide for Windows

### Prerequisites

- Windows 10/11 with WSL2 enabled (recommended) or Linux virtual machine
- Docker Desktop for Windows installed
- Minimum 2GB total memory, 1GB free memory [citation:9]
- Docker API version 1.11 or higher [citation:9]
- Domain with proper DNS records
- Ports 25, 80, 110, 143, 443, 465, 587, 993, 995 available [citation:9]

### Step 1: Set Up Docker Environment

**Enable WSL2:** In PowerShell (Admin):
```powershell
wsl --install

# 🦉 OSystemdX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OCore-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OSystemdX** — systemd Service Sandboxing & Exposure Scorer

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview


OSystemdX is an offline, read-only systemd service sandboxing and exposure scorer that discovers units across the full search path and merges drop-ins with correct precedence. It computes a 0.0-10.0 exposure score from 31 weighted sandboxing directives (User/DynamicUser, NoNewPrivileges, Protect*, Restrict*, SystemCallFilter and more) and flags secrets, writable ExecStart paths and 0.0.0.0 sockets. It can generate a hardened override.conf and exports TXT/MD/JSON/CSV/SARIF.

---

## ✨ Features


- Offline unit discovery across /etc, /run, /usr/local/lib, /usr/lib, /lib plus user and transient units
- Drop-in merging (*.d/*.conf) with correct precedence, masking, resets and per-directive provenance
- Exposure score 0.0-10.0 from 31 weighted sandboxing directives with implied-setting awareness
- Risk checks: secrets in Environment=, writable/relative ExecStart, 0.0.0.0 sockets and restart storms
- Hardened override.conf generator (safe / aggressive) and two-snapshot compare
- A..F grades, CWE/MITRE/CIS Controls mapping and TXT/MD/JSON/CSV/SARIF export

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage


```bash
./OSystemdX --scan --format sarif -o systemd.sarif
./OSystemdX --unit /etc/systemd/system/myapp.service
./OSystemdX --scan --top 10 --fail-on high
./OSystemdX --override nginx.service --profile aggressive
./OSystemdX --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled.s.Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*

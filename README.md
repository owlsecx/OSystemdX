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

Offline systemd service sandboxing & exposure scorer

---

## ✨ Features

- Offline unit discovery across the full systemd search path (/etc, /run, /usr/local/lib, /usr/lib, /lib, *.control, transient, generators) + user units
- Drop-in merging (*.d/*.conf) with correct precedence: same-name masking, template, prefix and type-level dirs, empty-assignment resets and per-directive provenance
- Exposure score 0.0–10.0 from 31 weighted sandboxing directives (User/DynamicUser, NoNewPrivileges, Protect*, Private*, Restrict*, SystemCallFilter, capabilities ...)
- Implied-setting awareness (DynamicUser, PrivateDevices, PrivateNetwork, NNP side-effects)
- Risk checks: secrets in Environment= (masked), secrets on command lines, world/non-root writable ExecStart, relative paths, '-' ignore-failure on security prereqs, sockets on 0.0.0.0, restart storms, weakening drop-ins
- Grades A…F + systemd-style SAFE/OK/MEDIUM/EXPOSED/UNSAFE
- Hardened override.conf generator (safe / aggressive)
- CWE / MITRE ATT&CK / CIS Controls v8 mapping
- Snapshot compare (score deltas, new / fixed findings)
- Exports: TXT / Markdown / JSON / CSV / SARIF 2.1.0
- Self-test demo with weak + hardened unit trees
- Strictly read-only — never touches the analysed system

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OSystemdX
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*

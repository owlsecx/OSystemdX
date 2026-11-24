# 🦉 OSystemdX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OCore-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
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

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OSystemdX --help   # watch every network call
firejail --net=none ./OSystemdX --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)

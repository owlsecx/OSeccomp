# 🦉 OSeccomp

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OScan-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OSeccomp** — Offline seccomp-bpf Profile Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OSeccomp is an offline auditor for seccomp-bpf profiles. It parses Docker/OCI JSON, systemd unit filters, Firejail, LXC and plain syscall-list formats, resolves the effective per-syscall policy, and compares it against a baseline. Findings are scored and mapped to CWE and MITRE ATT&CK.

---

## ✨ Features

- Tolerant JSON loader (comments, trailing commas) plus Docker/OCI seccomp parser
- systemd SystemCallFilter/SystemCallArchitectures and Firejail/LXC profile parsing
- Effective-policy engine resolving unconditional vs argument-filtered rules
- 30+ rules covering fail-open defaults, dangerous syscalls and architecture pinning
- Baseline diff against Docker default / RuntimeDefault
- CWE/MITRE mapping, 0-100 score and A+ to F grade with hardened-profile generation

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OSeccomp -p default.json
./OSeccomp -u /etc/systemd/system/myservice.service --effective
./OSeccomp --scan --root / --fail-on high
./OSeccomp --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*

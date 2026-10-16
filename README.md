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

Offline seccomp-bpf profile auditor (Docker, OCI, systemd, Firejail)

---

## ✨ Features

- Tolerant JSON loader — BOM, // and /* */ comments, trailing commas, single-quoted keys; never crashes
- Docker / Moby default.json & OCI runtime-spec linux.seccomp parser (names, legacy name, args, errnoRet, includes / excludes, flags, listenerPath)
- systemd unit parser — SystemCallFilter= (allow / ~deny lists, @groups, :errno), SystemCallArchitectures=, SystemCallErrorNumber=, NoNewPrivileges=, SystemCallLog=
- Firejail profile parser — seccomp, seccomp.drop, seccomp.keep, seccomp.block-secondary, memory-deny-*
- LXC seccomp policy (v1 / v2 allowlist / denylist)
- Plain syscall list / Chromium-Flatpak style notes
- Effective-policy engine — per-syscall resolution of unconditional vs argument-filtered rules
- 30+ rules: fail-open default, dangerous syscalls, CLONE_NEWUSER, ERRNO 0 fake-success, TRACE / NOTIFY, architecture pinning, x32 ABI, SPEC_ALLOW, ...
- Baseline diff vs Docker default / RuntimeDefault
- CWE + MITRE ATT&CK mapping, severity, remediation
- Weighted 0–100 hardening score and A+…F grade
- Filesystem scan (--root DIR) of well-known paths
- Export TXT / Markdown / JSON / CSV / SARIF 2.1.0
- Built-in self-test (--demo) and full CLI mode

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OSeccomp
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*

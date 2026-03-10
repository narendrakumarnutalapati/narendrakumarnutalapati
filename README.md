# LICITRA Research Program

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18860290.svg)](https://doi.org/10.5281/zenodo.18860290)
[![Research](https://img.shields.io/badge/type-security--research-blue)]()
[![License](https://img.shields.io/badge/license-MIT-green)]()

**Cryptographic runtime integrity for AI agent systems.**

AI agents increasingly invoke tools, APIs, and production infrastructure.  
Most current AI security approaches focus on **testing model behavior**, but they do not guarantee that the request approved by governance is the request actually executed by the system.

LICITRA explores **runtime enforcement mechanisms for agent systems**, combining authorization mediation, cryptographic execution binding, and tamper-evident audit.

---

# Core Security Invariant

LICITRA enforces the following property for agent tool execution:

H(authorized_request) = H(executed_request)

If the request that reaches a tool differs from the request that was authorized, execution is rejected.

This prevents:

- payload modification after authorization
- execution ticket replay
- unauthorized tool invocation
- delegation privilege escalation

---

# Why This Matters

Most AI security tooling focuses on **testing models**.

Examples:

- prompt injection testing  
- jailbreak detection  
- LLM red-teaming  

These answer:

Can the model be tricked?


Production systems must answer:

Did the system execute exactly what was authorized?


LICITRA focuses on **runtime enforcement for agent tool execution**.

---

# Architecture Overview

```
Agent
  ↓
Authorization Pipeline
  ↓
Execution Ticket
  ↓
Proxy Gateway
  ↓
Tool Execution
  ↓
Tamper-Evident Audit Ledger
  ↓
Witness Transparency
```

Agents cannot invoke tools directly.  
All tool execution must present a **cryptographically signed execution ticket**.

---

# LICITRA Components

## LICITRA-SENTRY

Runtime authorization and enforcement system for AI agents.

Features:

- five-gate authorization pipeline  
- Ed25519 execution tickets  
- mandatory tool mediation  
- proxy verification gateway  
- witnessed transparency audit  

Repository  
https://github.com/narendrakumarnutalapati/licitra-sentry

---

## LICITRA-MMR

Tamper-evident audit ledger primitive based on **Merkle Mountain Range**.

Features:

- append-only cryptographic audit log  
- logarithmic verification complexity  
- efficient inclusion proofs  
- external witness anchoring  

Repository  
https://github.com/narendrakumarnutalapati/licitra-mmr-core

---

# Reproducible Evidence

Security claims are supported by **reproducible experiment bundles**.

LICITRA-SENTRY Evidence  
https://github.com/narendrakumarnutalapati/licitra-sentry-evidence

LICITRA-MMR Evidence  
https://github.com/narendrakumarnutalapati/licitra-mmr-evidence

These repositories contain:

- attack simulations  
- verification artifacts  
- reproducibility scripts  

---

# Technical Reports / Publications

**LICITRA-SENTRY v0.2 Technical Report**  
Execution tickets and witnessed transparency for runtime enforcement.  
DOI: https://doi.org/10.5281/zenodo.18860290

**LICITRA-SENTRY v0.1 Technical Report**  
Chain of Intent authorization pipeline for agent systems.  
DOI: https://doi.org/10.5281/zenodo.18843784

**LICITRA-MMR Core Technical Report**  
Merkle Mountain Range audit ledger for tamper-evident accountability.  
DOI: https://doi.org/10.5281/zenodo.18843032

---

# Research Direction

LICITRA explores how **classical security principles apply to AI agents**, including:

- Complete mediation  
- Mandatory access control  
- Cryptographic accountability  

The goal is to move AI governance from **advisory policy checks** toward **cryptographically enforceable runtime guarantees**.

---

# Contact

Portland, Oregon  
narendrakumar.nutalapati@gmail.com  

LinkedIn  
https://linkedin.com/in/narendralicitra

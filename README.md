# HOLogram — Human Obfuscation Layer Protocol

> **Your behavior is real. What AI sees is not.**

HOLogram is an open protocol for **behavioral privacy**.  
It introduces a local layer that obfuscates, normalizes, and reduces the granularity of behavioral signals — typing dynamics, pointer movements, scroll patterns — before they reach web scripts or AI models.

It protects **behavioral biometrics** while preserving the full naturalness of human interaction.

---

## Why HOLogram?

Modern browsers protect your device. Nobody protects your behavior.

Behavioral biometrics — typing rhythm, pointer trajectories, micro-pauses, scroll dynamics — are today one of the most powerful identifiers available to tracking systems. Even without cookies or login, these signals allow:

- unique identification across sessions
- cross-site correlation
- AI-driven inference (stress, hesitation, cognitive patterns)

HOLogram introduces a new layer of protection:  
it transforms the behavioral form while preserving the functional intent — projecting a **hologram** of the real interaction onto the web.

---

## Protocol Properties

- **Human-centric** — protects the person, not just the device
- **Local-only & zero-retention** — no data leaves the terminal, ever
- **Non-manipulative** — does not alter user intent or decisions
- **AI-free** — prevents behavioral identification by AI systems
- **Open standard** — freely implementable, verifiable, forkable

---

## Architecture

HOLogram is composed of six independent modules:

```
Input
  ↓
ShadowDOM Input Vault        — isolates native events, removes typing micro-timings
  ↓
Pointer & Scroll Normalizer  — downsampling, coordinate quantization, smoothing
  ↓
Persona Mixer                — session-consistent synthetic behavioral signature
  ↓
Behavioral DP Engine         — calibrated noise, output sensitivity reduction
  ↓
Behavioral Privacy Budget    — controls total behavioral exposure, triggers escalation
  ↓
Output → Browser / Site      — functional, natural, non-identifiable
```

The content of every interaction is preserved exactly.  
The behavioral form is obfuscated.

---

## Status

| Component | Status |
|---|---|
| Whitepaper v1.0 (IT + EN) | ✅ Published |
| Reference Implementation | 🔧 In development |
| HLP — HOLogram Layer Protocol (spec) | 🔧 In progress |
| HCT — Compliance Tests | 🔧 In progress |
| HOLoToken (HRL/HCS) | 📋 Designed |
| Ecosystem Registry | 📋 Planned |

> We are actively looking for contributors to build the first reference implementation.  
> If you work in browser extensions, privacy engineering, or differential privacy — **[see open tasks below](#contributing)**.

---

## Official Documents (v1.0)

All documents are notarized with SHA-256 and IPFS CID.  
Full notarization chain: [`HASHES.txt`](./HASHES.txt)

| Document | Language | SHA-256 |
|---|---|---|
| Whitepaper v1.0 | Italian | `d01882e6...d2e1` |
| Whitepaper v1.0 | English (rev1) | `390c9286...2301` |
| Whitepaper — Minimum | Italian | `0751b2e7...3309` |
| Whitepaper — Minimum | English | `9feec735...4ad` |

🔗 **[Release v1.0 — all documents + hashes + IPFS CIDs](https://github.com/BaffiSan/HOLogram/releases/tag/v1.0)**  
🌐 **[hologramprotocol.org](https://www.hologramprotocol.org)**

---

## Contributing

HOLogram is an **open, meritocratic standard**.  
Every technical contribution — code, security research, tests, documentation, RFC proposals — is recognized through **HOLoToken (HRL/HCS)**, a non-financial Proof-of-Contribution system.

**Start here:**

- 📋 [`GOOD-FIRST-ISSUES.md`](./GOOD-FIRST-ISSUES.md) — concrete tasks ready to be picked up
- 📄 [`CONTRIBUTING.md`](./CONTRIBUTING.md) — full contribution guide
- 📄 [`RFC_TEMPLATE.md`](./RFC_TEMPLATE.md) — propose changes to the protocol
- 💬 [GitHub Discussions](https://github.com/BaffiSan/HOLogram/discussions) — open design conversations

Skills most needed right now: **JavaScript / browser extensions**, **privacy engineering**, **differential privacy on event streams**, **behavioral biometrics research**.

---

## Security

Vulnerabilities must **not** be reported as public issues.

Use the dedicated channel:  
📧 `security@hologramprotocol.org`  
🔑 PGP: [hologramprotocol.org/pgp/security.asc](https://www.hologramprotocol.org/pgp/security.asc)  
Key ID: `0x1E5D914EFCEF87B1`  
Fingerprint: `E329 3DD8 B1A8 FEC2 F919 4A9D 1E5D 914E FCEF 87B1`

Full policy: [`SECURITY.md`](./SECURITY.md)

---

## License

Released under the [MIT License](./LICENSE.txt).

---

## Contact

📧 [contact@hologramprotocol.org](mailto:contact@hologramprotocol.org)  
🌐 [hologramprotocol.org](https://www.hologramprotocol.org)

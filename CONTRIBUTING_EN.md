# Contributing to HOLogram

**Open Standard — Proof-of-Contribution — Community-Driven**

Thank you for your interest in contributing to **HOLogram**, the open protocol for behavioral biometrics protection.

HOLogram values both technical and non-technical contributions through a **meritocratic, decentralized** model based on *Proof-of-Contribution* (HOLoToken — HRL/HCS).  
Every contribution helps make the protocol more robust, verifiable, and adoptable.

---

## General Principles

- **Openness** — all contributions are welcome: code, research, security, documentation
- **Neutrality** — the protocol is independent of vendors, platforms, and economic interests
- **Technical merit** — recognition is based on contribution value, not identity
- **Transparency** — every change must be motivated, verifiable, and traceable
- **Security** — vulnerabilities must be reported through the dedicated private channel

---

## Types of Contribution

### Code
- Reference Implementation (browser extension / modules)
- Experimental modules or protocol variants
- Bug fixes, refactoring, structural improvements

### Documentation
- Whitepaper improvements
- Guides, glossaries, diagrams
- Technical specifications (HLP)
- Compliance tests (HCT)

### Security
- Protocol analysis
- Vulnerability disclosure
- Anti-detection verification
- Threat modeling

### Research & RFC
- Protocol change proposals (RFC)
- Academic analysis
- Behavioral benchmarks

### Quality & Testing
- Cross-browser testing
- Persona Mixer validation
- Anti-correlation testing
- HCT improvements

---

## Security — Responsible Disclosure

If you found a vulnerability, **do not open a public issue.**

Use the dedicated private channel:

📧 **[security@hologramprotocol.org](mailto:security@hologramprotocol.org)**  
🔑 PGP: [hologramprotocol.org/pgp/security.asc](https://www.hologramprotocol.org/pgp/security.asc)  

Full policy: [`SECURITY.md`](./SECURITY.md)

---

## How to Propose a Change (RFC Process)

The HOLogram protocol evolves through **RFC — Request for Comments**.

### Steps:

1. Create a new file in the `RFC/` directory using the template: `RFC_TEMPLATE.md`
2. Fill in the document with:
   - title
   - motivation
   - technical impact
   - affected modules (Vault, Normalizer, Mixer, DP Engine, Budget, HUD)
   - benefits and trade-offs
   - compatibility with HLP and HCT
3. Open a **Pull Request** with the RFC
4. The community and maintainers review it
5. If approved → it becomes part of the HLP specification

For security-related RFCs, a reviewer with the **Security Reviewer** role (HOLoToken-Security ≥ threshold) is required.

---

## How to Contribute Code

### 1. Fork the repository

### 2. Work on a dedicated branch

Examples:
```
feature/your-feature-name
fix/input-normalization
experiment/dp-strategy-B
research/browser-api-survey
```

### 3. Follow commit message conventions

Use short, descriptive commit messages:

```
feat: add variable smoothing to normalizer
fix: correct input vault timing under Edge
docs: update DP Engine section
test: add session-consistent mixer benchmark
research: survey pointer event APIs across browsers
```

### 4. Before opening a PR:

- run HCT tests (when available)
- verify the build is clean
- update documentation if needed
- clearly describe the change and its rationale

### 5. Open a Pull Request

Fill in the PR description with:
- summary of the change
- context and motivation
- related issues
- notes for reviewers
- benchmarks or tests if applicable

---

## Testing & Compliance (HCT)

Every implementation must be verifiable through **HOLogram Compliance Tests (HCT)**:

- DOM event coherence
- human behavioral plausibility
- basic anti-detection resistance
- HLP semantic compliance
- absence of behavioral leakage

Tests are published in the `tests/` directory.

---

## HOLoToken — Proof-of-Contribution

Every valid contribution generates reputational value through:

- **HRL** — HOLogram Reputation Layer
- **HCS** — HOLogram Contribution Score (scalar + vector)

Evaluated dimensions:
- security
- core code
- documentation
- testing
- i18n
- research
- RFC proposals
- technical reviews

Badges and roles (Maintainer, Security Reviewer, Docs Steward, etc.) are awarded based on HCS.  
HOLoToken has no economic value and is non-transferable — it is purely technical merit, visible and verifiable.

---

## Code Style Guidelines

- avoid unnecessary dependencies
- keep functionality minimal (minimal reference implementation principle)
- no telemetry, no data collection of any kind
- readable and commented code
- avoid premature optimizations
- maintain strict separation between modules:
  - Input Vault
  - Normalizer
  - Persona Mixer
  - DP Engine
  - Privacy Budget
  - Output Projector

---

## Issues

Open an issue **only for**:
- bugs in the RI
- technical questions
- clarification requests
- proposals that are not security vulnerabilities

**Vulnerabilities must never be reported as public issues.**  
Always use the dedicated security channel.

---

## Code of Conduct

Participants are expected to maintain an environment that is:
- open and inclusive
- respectful
- collaborative
- meritocratic
- grounded in technical value

---

## Thank You

HOLogram exists because the community contributes.  
Every patch, test, idea, or RFC helps the protocol grow as an **open standard**.

Questions or want to discuss ideas first?

📧 [contact@hologramprotocol.org](mailto:contact@hologramprotocol.org)  
💬 [GitHub Discussions](https://github.com/BaffiSan/HOLogram/discussions)  
🌐 [hologramprotocol.org](https://www.hologramprotocol.org)

---

*Italian version: [`CONTRIBUTING.md`](./CONTRIBUTING.md)*

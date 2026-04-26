# RFC Title

*Short, descriptive, non-commercial.*

**Status:** Draft / Review / Accepted / Rejected  
**Author:**  
**Initial Reviewers:**  
**Proposed Version:** HLP vX.Y  
**Date:**

---

## 1. Abstract

Provide a brief summary (5–10 lines) of the proposal:

- what changes
- why it is needed
- which modules are affected
- what benefit it brings to the protocol

---

## 2. Motivation

Describe:

- the current problem or limitation in the HOLogram protocol
- why the change is necessary
- concrete use cases
- risks or vulnerabilities this RFC intends to address

This section should *not* contain deep technical details — only the "why".

---

## 3. Proposed Change

Describe precisely:

- what is being modified
- what is being added
- what is being removed (breaking changes)
- specific references to the existing HLP

Example:
> Modification to section 5.2 Pointer & Scroll Normalizer:
> - added dynamic smoothing threshold
> - parameter `alpha` → `alpha_sessionvariant`

---

## 4. Affected Modules (HLP Components)

Indicate which HOLogram components are modified:

- [ ] ShadowDOM Input Vault
- [ ] Pointer & Scroll Normalizer
- [ ] Persona Mixer
- [ ] Behavioral Differential Privacy Engine
- [ ] Behavioral Privacy Budget
- [ ] Exposure HUD
- [ ] Output Projector
- [ ] HID Cloak (optional)
- [ ] HLP Documentation / Semantics
- [ ] HCT Tests
- [ ] Ecosystem Registry
- [ ] HOLoToken (HRL/HCS)

---

## 5. Detailed Technical Specification

Describe rigorously and formally:

- algorithms
- parameters and their types
- numeric ranges
- operational rules
- effects on synthetic behavioral output
- impact on signal sensitivity
- impact on detectability

Suggested structure:

### 5.1 New parameters introduced

### 5.2 Updated formulas / pseudocode

### 5.3 Rules for compliant implementations

### 5.4 Edge-case behavior

### 5.5 Differences from previous version

### 5.6 Compatibility notes

---

## 6. Security Impact

Analyze whether the proposal:

- increases protection
- introduces new risks
- creates identifying signals
- alters the correlatability profile
- requires an update to the threat model
- can be detected by aggressive scripts
- impacts anti-bot systems

This section is **required**.

---

## 7. Usability Impact (UX)

Describe any effects on:

- naturalness of movements
- perceived latency
- compatibility with time-sensitive applications
- browser-specific dependencies
- cases where the proposal may degrade UX

---

## 8. Impact on HCT (Compliance Tests)

Indicate whether the RFC:

- introduces new tests
- modifies existing tests
- removes obsolete tests

Example:
> New HCT test: verify smoothing stability within human plausibility range.

---

## 9. Compatibility and Migration

Describe:

- impact on existing implementations
- what maintainers must do to adopt the new version
- whether the change is backward-compatible
- whether it requires a semantic version bump:
  - patch (v1.0.x)
  - minor (v1.x)
  - major (vX.0)

---

## 10. Alternatives Considered

Briefly list the technical alternatives evaluated and why they were **not** adopted.  
This section demonstrates that the proposal has been compared against other solutions.

---

## 11. Evaluation Process

Describe:

- which communities or maintainers are involved
- which requirements must be met
- what technical quorum is required (e.g. Security Reviewer + RI Maintainer)
- any dependencies on other RFCs

---

## 12. Roadmap

Indicate:

- expected timeline
- implementation steps
- validation steps
- rollout steps

---

## 13. Appendices (optional)

- Diagrams
- Extended pseudocode
- Calculations
- Benchmarks
- Mathematical models
- Alternative approaches
- Prototypes

---

## 14. Final Decision (completed by maintainers)

**Status:** Accepted / Rejected / Deferred  
**Decision date:** YYYY-MM-DD  
**Technical reviewers:**  
**Notes:**

---

## 15. RFC Changelog

Record changes to the RFC itself:

- v0.1 — initial draft
- v0.2 — community feedback integrated
- v1.0 — final approval

---

*Italian version: [`RFC_TEMPLATE.md`](./RFC_TEMPLATE.md)*

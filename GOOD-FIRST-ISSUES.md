# Good First Issues — HOLogram

A curated list of well-defined tasks for new contributors.  
Each task is self-contained, has a clear output, and does not require prior knowledge of the full codebase.

**Before starting:** read [`CONTRIBUTING.md`](./CONTRIBUTING.md) and open an issue or Discussion to signal you're working on a task (to avoid duplicate effort).

---

## How to read this list

Each task includes:
- **Difficulty** — `low / medium / high`
- **Skills** — what you need to know
- **Estimated time** — realistic estimate for someone new to the project
- **Output** — exactly what you should produce
- **Why it matters** — how it connects to the protocol

---

## Research Tasks

---

### [R-01] Survey browser APIs for input event interception

**Difficulty:** low  
**Skills:** JavaScript, browser extension basics  
**Estimated time:** 4–8 hours  
**Module:** Input Vault

**Goal:**  
Document which browser APIs (Chrome/Chromium, Firefox, Safari) allow interception of `keydown`, `keyup`, `keypress` events *before* they reach page-level scripts.

**Output:**  
A markdown document `docs/research/R-01-input-event-apis.md` containing:
- available APIs per browser
- minimum required permissions
- known limitations or behavioral differences
- a comparison table (browser × capability)

**Why it matters:**  
This is the foundation for implementing the ShadowDOM Input Vault across browsers. The choice of API determines both the security boundary and the compatibility surface of the entire layer.

---

### [R-02] Survey pointer and scroll event APIs across browsers

**Difficulty:** low  
**Skills:** JavaScript, browser APIs  
**Estimated time:** 4–6 hours  
**Module:** Pointer & Scroll Normalizer

**Goal:**  
Document how `mousemove`, `pointermove`, `wheel`, and `scroll` events are exposed across Chrome, Firefox, and Safari — focusing on event frequency, throttling behavior, and precision.

**Output:**  
A markdown document `docs/research/R-02-pointer-scroll-apis.md` containing:
- native event frequency per browser (measured or documented)
- whether browsers apply native throttling
- differences between `MouseEvent` and `PointerEvent`
- precision of coordinate values (integer vs float)
- a comparison table

**Why it matters:**  
The Normalizer's downsampling and quantization parameters must be calibrated to the actual event rates and precision of each browser. This research directly informs the default values.

---

### [R-03] Behavioral biometrics classifier survey

**Difficulty:** medium  
**Skills:** reading academic papers, basic ML understanding  
**Estimated time:** 8–12 hours  
**Module:** DP Engine / general

**Goal:**  
Survey publicly available research on behavioral biometrics classifiers (keystroke dynamics, mouse movement analysis) to understand what features they extract and how accurate they are.

**Output:**  
A markdown document `docs/research/R-03-classifier-survey.md` containing:
- list of 8–12 relevant papers (with links/DOIs)
- for each: features used, reported accuracy, dataset size
- summary of which signal features are most discriminative
- implications for HOLogram's DP Engine and Normalizer

**Why it matters:**  
HOLogram's effectiveness can only be measured against real classifiers. This survey defines the threat model concretely and helps calibrate what "sufficient obfuscation" means in practice.

---

### [R-04] Survey existing differential privacy libraries for event streams

**Difficulty:** medium  
**Skills:** JavaScript/TypeScript or Python, familiarity with DP concepts  
**Estimated time:** 6–10 hours  
**Module:** DP Engine

**Goal:**  
Identify and evaluate existing open-source libraries that implement differential privacy or noise injection applicable to real-time event streams (not batch datasets).

**Output:**  
A markdown document `docs/research/R-04-dp-libraries.md` containing:
- list of candidate libraries (at least 5)
- for each: language, license, maintenance status, applicability to HOLogram's use case
- a recommendation with rationale, or a conclusion that a custom implementation is preferable
- open questions for the community

**Why it matters:**  
The DP Engine is the most technically complex module. Understanding what already exists avoids reinventing the wheel — or confirms why a custom approach is needed.

---

### [R-05] Anti-bot system behavior analysis

**Difficulty:** medium  
**Skills:** JavaScript, web development  
**Estimated time:** 6–10 hours  
**Module:** Pointer & Scroll Normalizer / Persona Mixer

**Goal:**  
Research and document how common anti-bot systems (e.g., Cloudflare, reCAPTCHA, hCaptcha, DataDome) detect automated or obfuscated behavior. Focus on publicly available information only (no reverse engineering of proprietary systems).

**Output:**  
A markdown document `docs/research/R-05-antibot-signals.md` containing:
- documented signals that anti-bot systems are known to use
- which HOLogram modules might trigger false positives
- proposed mitigation strategies for the Persona Mixer
- open questions for the community

**Why it matters:**  
HOLogram must not cause users to fail CAPTCHA or be blocked by anti-fraud systems. Understanding the detection surface is essential for calibrating the Normalizer and Mixer.

---

## Design Tasks

---

### [D-01] Define human plausibility ranges for Persona Mixer parameters

**Difficulty:** medium  
**Skills:** reading research papers, basic statistics  
**Estimated time:** 6–10 hours  
**Module:** Persona Mixer

**Goal:**  
The whitepaper defines five Persona Mixer parameters (`pointerJitterRange`, `scrollPauseProbability`, `typingLatencyOffset`, `smoothingAggressiveness`, `curvatureSoftening`) but does not specify numeric ranges. Define plausible human ranges for each, grounded in research.

**Output:**  
A markdown document `docs/design/D-01-persona-mixer-ranges.md` containing:
- for each parameter: proposed min/max range, recommended default, supporting references
- rationale for why these ranges are "human plausible"
- open questions or parameters that require empirical measurement

**Why it matters:**  
These ranges are the core calibration of the Persona Mixer. Too narrow and different personas look the same; too wide and the obfuscation itself becomes a fingerprint. Getting this right requires real data about human behavioral variance.

---

### [D-02] Design the Behavioral Privacy Budget consumption model

**Difficulty:** medium-high  
**Skills:** algorithm design, basic probability  
**Estimated time:** 8–14 hours  
**Module:** Behavioral Privacy Budget

**Goal:**  
The whitepaper defines the event intensity formula `cost = w_type × f_freq × g_geom × h_entropy` and the three escalation thresholds, but leaves the actual numeric values as "to be calibrated by the community." Propose concrete values and a regeneration model.

**Output:**  
A markdown document `docs/design/D-02-privacy-budget-model.md` containing:
- proposed values for `w_type`, `f_freq`, `g_geom`, `h_entropy` factors
- proposed threshold values for the three escalation levels
- proposed regeneration rates (time-based and idle-based)
- sensitivity analysis: how do different values affect protection vs usability?
- open questions

**Why it matters:**  
Without concrete budget values, the reference implementation cannot be built. This design document will directly feed into the first coded module.

---

### [D-03] Define the HCT (compliance test) specification for the Input Vault

**Difficulty:** medium  
**Skills:** software testing, JavaScript  
**Estimated time:** 6–10 hours  
**Module:** Input Vault / HCT

**Goal:**  
Define a formal test specification for verifying that an implementation of the ShadowDOM Input Vault is compliant with the HOLogram protocol.

**Output:**  
A markdown document `docs/design/D-03-hct-input-vault.md` containing:
- list of test cases with: name, input, expected output, pass/fail condition
- at minimum: semantic preservation test, micro-timing removal test, event bubbling coherence test, IME compatibility test
- notes on which tests can be automated vs require manual verification

**Why it matters:**  
HCT is HOLogram's quality guarantee across implementations. Defining tests before code is a deliberate protocol-first approach that ensures any future implementation can be verified against a common standard.

---

## Documentation Tasks

---

### [X-01] Translate RFC_TEMPLATE.md to English

**Difficulty:** low  
**Skills:** English, familiarity with technical documentation  
**Estimated time:** 2–3 hours  
**Module:** RFC process

**Goal:**  
Produce an English version of `RFC_TEMPLATE.md` that mirrors the Italian original exactly in structure and content.

**Output:**  
A new file `RFC_TEMPLATE_EN.md` in the root of the repository.

**Why it matters:**  
The RFC process is central to HOLogram's governance. Non-Italian speakers need to be able to propose changes to the protocol using a template they can read and understand.

---

### [X-02] Translate GOVERNANCE.md to English

**Difficulty:** low  
**Skills:** English, familiarity with open source governance  
**Estimated time:** 2–4 hours  
**Module:** Governance

**Goal:**  
Produce an English version of `GOVERNANCE.md` that mirrors the Italian original exactly.

**Output:**  
A new file `GOVERNANCE_EN.md` in the root of the repository.

**Why it matters:**  
International contributors need to understand the project's decision-making structure before investing significant time.

---

### [X-03] Create module specification documents

**Difficulty:** medium  
**Skills:** technical writing, understanding of the whitepaper  
**Estimated time:** 3–5 hours per module (6 modules)  
**Module:** all

**Goal:**  
Create one markdown file per module in `docs/modules/`, translating the whitepaper's descriptions into operational specifications: input contract, output contract, semantic constraints, configurable parameters, open questions.

Modules: `input-vault.md`, `normalizer.md`, `persona-mixer.md`, `dp-engine.md`, `privacy-budget.md`, `exposure-hud.md`

**Output:**  
Six markdown files in `docs/modules/`, each following this structure:
```
## Responsibility
## Input contract
## Output contract
## Semantic constraints
## Configurable parameters
## Open questions
```

**Why it matters:**  
These documents are the bridge between the whitepaper and actual code. An implementer should be able to write a compliant module by reading its spec document alone, without reading the entire whitepaper.

---

## How to Signal Interest

1. Open a GitHub Issue referencing the task ID (e.g. `[R-01] Starting browser API survey`)
2. Or post in [GitHub Discussions](https://github.com/BaffiSan/HOLogram/discussions)
3. Assign yourself if you have write access, or comment to signal you're working on it

Questions? Reach out at [contact@hologramprotocol.org](mailto:contact@hologramprotocol.org)

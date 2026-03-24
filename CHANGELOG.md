# Changelog — HOLogram Protocol
Tutte le modifiche rilevanti al protocollo, al whitepaper, alle specifiche e ai componenti dell’ecosistema.

Questo progetto segue i principi del  
**Keep a Changelog** (https://keepachangelog.com)  
e del **versionamento semantico** applicato ai documenti (vX.Y).

---

## [1.0.0] — 2026-03-24  
**Prima versione pubblica del protocollo HOLogram (v1.0).**

### Whitepaper  
- Pubblicazione del **Whitepaper v1.0 (completo)**.  
- Pubblicazione del **Whitepaper v1.0 (versione minima)**.  
- Correzione completa di:  
  - refusi, trattini, spazi doppi  
  - errata “Ob fuscation” → **Obfuscation**  
  - corretto “BaffiS an” → **BaffiSan**  
- Intestazioni corrette: rimosse da copertina, abstract, indice.  
- Numerazione pagine corretta: inizia da *Introduzione* con “Pagina 1”.  
- Piè di pagina standardizzato (titolo, versione, data e numero pagina).  
- Metadati PDF ripuliti e uniformati.

### Notarizzazione  
- Generazione hash SHA‑256 di entrambi i PDF.  
- Creazione file `HASHES.txt` (storico notarizzazioni).  
- Preparazione per pubblicazione su IPFS (CID).

### Documenti del Repository  
- Aggiunto `README.md` completo (overview + hash + CID).  
- Aggiunto `SECURITY.md` (Responsible Disclosure).  
- Aggiunto `CONTRIBUTING.md` (linee guida contributo).  
- Aggiunto `CHANGELOG.md` (questo file).  
- Aggiunto `RFC_TEMPLATE.md` (per proposte di modifica).  
- Aggiunto `LICENSE` duale: **MIT (codice)** + **CC BY 4.0 (whitepaper)**.  
- Impostate directory principali:  
  - `/docs/` (whitepaper, specifiche, ecosistema)  
  - `/security/`  
  - `/RFC/`  
  - `/tests/` (HCT — future compliance suite)  
  - `/src/` (future reference implementation)

### Ecosistema & Specifiche  
- Definiti i principi di:  
  - **HLP — HOLogram Layer Protocol**  
  - **HCT — Compliance Tests**  
  - **HOLoToken — HRL/HCS** (Proof‑of‑Contribution)  
- Definito processo RFC per modifiche future.  
- Strutturato percorso di standardizzazione (HLP v1.x → proposte v2.x).

### Sicurezza  
- Definito threat model.  
- Definite mitigazioni core: Vault, Normalizer, Mixer, DP Engine, Budget.  
- Definita policy di sicurezza e Safe Harbor per ricercatori.  
- Preparato per future advisory firmati.

---

## [Unreleased] — prossimo rilascio  
In lavorazione:

### Reference Implementation (RI)  
- Estensione browser minimale.  
- Build verificabili.  
- Modularizzazione (Vault, Normalizer, Mixer, DP, Budget).  
- Test cross‑browser.

### Specifiche tecniche (HLP v1.1)  
- Formalizzazione parametri session‑consistent.  
- Formalizzazione smoothing + quantizzazione.  
- Prima versione pubblica HCT v1.

### Ecosystem Registry  
- Elenco implementazioni conformi.  
- Badge HLP‑Compatibility.

### Documentazione  
- Diagrammi ufficiali dei moduli.  
- Schema dei flussi (Vault → DP → Output).  
- Glossario avanzato.

---

## [Future] — roadmap prevista  
- **v1.1**: miglioramenti semantici minori + HCT v1.  
- **v1.2**: varianti policy-driven + mix strategies.  
- **v2.0**: proposta di standardizzazione formale del protocollo.

---

## Note  
I documenti tecnici (whitepaper, appendici, HLP, HCT, HOLoToken) seguono versionamento semantico **indipendente dal codice**, come negli standard IETF.

Ogni modifica semantica richiede una **RFC**.
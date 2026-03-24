# Contribuire a HOLogram
**Open Standard — Proof‑of‑Contribution — Community‑Driven**

Grazie per il tuo interesse nel contribuire a **HOLogram**, il protocollo aperto per la protezione della biometria comportamentale.

Il progetto valorizza contributi tecnici e non tecnici attraverso un modello **meritocratico e decentralizzato** basato su *Proof‑of‑Contribution* (HOLoToken — HRL/HCS).  
Ogni contributo aiuta a rendere il protocollo più robusto, verificabile e adottabile.

---

# 🧭 Principi generali

- **Apertura:** ogni contributo è benvenuto (codice, ricerca, sicurezza, documentazione).  
- **Neutralità:** il protocollo è indipendente da vendor, piattaforme e interessi economici.  
- **Merito tecnico:** il riconoscimento si basa sul valore del contributo, non sull’identità.  
- **Trasparenza:** ogni modifica deve essere motivata, verificabile e tracciabile.  
- **Sicurezza:** le vulnerabilità vanno segnalate tramite il canale riservato (vedi più sotto).

---

# 📦 Tipologie di contributo

Puoi contribuire in molti modi:

### 🟦 Codice
- Reference Implementation (browser extension / modules)
- Moduli sperimentali o varianti
- Fix, refactoring, miglioramenti strutturali

### 🟦 Documentazione
- Whitepaper improvements
- Guide, glossari, diagrammi
- Specifiche tecniche (HLP)
- Test di conformità (HCT)

### 🟦 Sicurezza
- Analisi del protocollo
- Segnalazione di vulnerabilità
- Verifica anti‑rilevazione
- Threat modeling

### 🟦 Ricerca & RFC
- Proposte di modifica al protocollo (RFC)
- Analisi accademiche
- Benchmark comportamentali

### 🟦 Qualità & Test
- Test cross‑browser
- Validazione persona mixer
- Test anti‑correlazione
- Miglioramenti HCT

---

# 🔐 Responsible Disclosure (vulnerabilità)

Se hai trovato una vulnerabilità, **non aprire issue pubbliche.**

Usa il canale riservato:

📧 **security@hologramprotocol.org**  
🔑 PGP: https://www.hologramprotocol.org/pgp/security.asc  
Leggi la policy completa: **SECURITY.md**

---

# 📝 Come proporre una modifica (Processo RFC)

Il protocollo HOLogram evolve tramite **RFC — Request for Comments**.

### Passaggi:

1. Crea un nuovo file nella directory `RFC/` usando il template:  
   `RFC_TEMPLATE.md`
2. Compila il documento con:
   - titolo  
   - motivazione  
   - impatto tecnico  
   - moduli interessati (Vault, Normalizer, Mixer, DP Engine, Budget, HUD)  
   - vantaggi e compromessi  
   - compatibilità con HLP e HCT
3. Apri una **Pull Request** con l’RFC.
4. La community e i maintainer la revisionano.  
5. Se approvata → diventa parte della specifica HLP.

Per RFC di sicurezza, è richiesto un reviewer con ruolo **Security Reviewer (HOLoToken‑Security ≥ soglia)**.

---

# 🔧 Come contribuire con il codice

### 1. Crea un fork del repository 
 
### 2. Lavora su un branch separato  
Esempio:
feature/your-feature-name
fix/input-normalization
experiment/dp-strategy-B
### 3. Segui gli standard di commit  
Usa commit brevi e descrittivi:

feat: aggiunge smoothing variabile al normalizer
fix: corregge timing input vault sotto Edge
docs: aggiorna sezione DP Engine
test: aggiunge benchmark session-consistent mixer

### 4. Prima della PR:
- esegui i test HCT (quando disponibili)  
- verifica che la build sia pulita  
- aggiorna documentazione se necessario  
- descrivi chiaramente il cambiamento  

### 5. Apri una Pull Request
Compila la PR con:
- descrizione  
- contesto  
- issue correlate  
- note per i reviewer  
- eventuali benchmark o test  

---

# 🔬 Test & Conformità (HCT)

Ogni implementazione deve essere verificabile tramite **HOLogram Compliance Tests (HCT)**:

- coerenza degli eventi DOM  
- plausibilità umana  
- anti‑rilevazione di base  
- rispetto della semantica HLP  
- assenza di leak comportamentali

I test saranno pubblicati nella directory `tests/`.

---

# 🏅 HOLoToken — Proof‑of‑Contribution

Ogni contributo valido genera valore reputazionale tramite:

- **HRL** — HOLogram Reputation Layer  
- **HCS** — HOLogram Contribution Score (scalare + vettoriale)

Valutano:
- sicurezza  
- codice core  
- documentazione  
- test  
- i18n  
- ricerca  
- RFC  
- review tecniche  

I badge e i ruoli (Maintainer, Security Reviewer, Docs Steward, ecc.) sono conferiti in base a HCS.

---

# 📄 Stile del codice (guidelines)

- evitare dipendenze inutili  
- mantenere funzionalità minima (principio “minimal reference implementation”)  
- nessuna telemetria  
- codice leggibile e commentato  
- evitare ottimizzazioni premature  
- mantenere separazione netta tra:
  - Input Vault  
  - Normalizer  
  - Mixer  
  - DP Engine  
  - Privacy Budget  
  - Output Layer  

---

# 🔍 Issue

Apri una issue **solo per**:
- bug nella RI  
- domande tecniche  
- richieste di chiarimento  
- proposte non riguardanti vulnerabilità  

Le vulnerabilità NON devono essere riportate nelle issue.  
Usa sempre il canale security dedicato.

---

# 🤝 Codice di Condotta

I partecipanti sono invitati a mantenere un ambiente:

- aperto  
- rispettoso  
- collaborativo  
- meritocratico  
- basato sul valore tecnico  

(Uno `CODE_OF_CONDUCT.md` può essere aggiunto se necessario.)

---

# 💬 Grazie!

HOLogram esiste perché la community contribuisce.  
Ogni patch, test, idea o RFC aiuta il protocollo a crescere come **standard aperto**.

Se hai dubbi o vuoi confrontarti:

📧 contact@hologramprotocol.org  
🌐 https://www.hologramprotocol.org  
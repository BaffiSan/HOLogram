# HOLogram — Human Obfuscation Layer Protocol
**Il tuo comportamento è reale. Quello che l’AI vede, no.**

HOLogram è un **Human Obfuscation Layer**: uno strato locale che offusca, normalizza e riduce la granularità dei segnali comportamentali (digitazione, puntatore, scroll) prima che raggiungano pagine web, script o modelli di AI.  
Protegge la **biometria comportamentale**, mantenendo la piena naturalezza dell’interazione umana.

HOLogram è:
- **Human‑centric**
- **Local‑only, zero‑retention**
- **Non manipolativo**
- **AI‑free**
- **Standard aperto, verificabile e implementabile liberamente**

---

# 📘 Whitepaper v1.0

### **Whitepaper completo**
- **PDF:** `HOLogram_v1.0.pdf`
- **SHA‑256:** `d01882e6f3f7507f9ddda6fc5f443a277c670e7c9c1573c31a5bb8730784d2e1`
- **IPFS CID:** `QmaZmziEkbCz9uEKq1Q5cEtyccUMWDZsr9aaGe3xYz182i`

### **Whitepaper — versione minima**
- **PDF:** `HOLogram_min_v1.0.pdf`
- **SHA‑256:** `0751b2e73c4c2602adfed3d021ce7b64bfb2c85c3d39b82124f0cd0b10553309`
- **IPFS CID:** `QmTmaAKHTh1oQdJS8ankJMDHGkNukWAcepM71kwaAdA2PH`

### Storico notarizzazioni  
📄 `HASHES.txt`  
Include SHA‑256 e CID IPFS di tutte le versioni pubblicate.

---

# 🧠 Perché HOLogram?

La biometria comportamentale è oggi uno degli identificatori più potenti:  
- ritmo di digitazione  
- traiettorie del puntatore  
- micro‑pause decisionali  
- dinamiche di scroll  

Anche senza cookie o login, questi segnali permettono identificazione, correlazione cross‑site e inferenze AI-driven.

HOLogram introduce un **nuovo livello di tutela**:  
trasforma il comportamento mantenendo la funzione, ma non l’identità.

---

# 🏛 Architettura (overview)

HOLogram è composto da moduli indipendenti:

1. **ShadowDOM Input Vault** — isola eventi native e rimuove micro‑tempi di digitazione  
2. **Pointer & Scroll Normalizer** — riduce frequenza, quantizza coordinate, stabilizza movimenti  
3. **Persona Mixer (session‑consistent)** — genera una firma sintetica diversa ogni sessione  
4. **Behavioral Differential Privacy Engine** — aggiunge rumore minimo e stabilizzazione  
5. **Behavioral Privacy Budget** — limita quanta informazione comportamentale può essere esposta  
6. **Exposure HUD** — trasparenza e controllo lato utente  

Flusso:  
`Input → Vault → Normalizer → Persona Mixer → DP Engine → Privacy Budget → Output verso il sito`

---

# 🛡 Sicurezza & Responsible Disclosure

Le segnalazioni di vulnerabilità **non devono** essere pubbliche.

**Email dedicata:** security@hologramprotocol.org  
**Oggetto consigliato:** `HOLogram Security Disclosure – <titolo>`  
**PGP:** `/pgp/security.asc`  
**Key ID:** `0x1E5D914EFCEF87B1`  
**Fingerprint:** `E329 3DD8 B1A8 FEC2 F919 4A9D 1E5D 914E FCEF 87B1`

Leggi la policy completa:  
📄 **SECURITY.md**

---

# 🧪 Reference Implementation (RI)

La RI sarà pubblicata come:
- estensione browser minimale  
- codice verificabile  
- build riproducibili  
- HCT (test di conformità)  

> **Nota:** la RI è in fase di sviluppo.  
> Segui il repository per aggiornamenti.

---

# 📚 Documentazione

- **Protocollo HOLogram (whitepaper v1.0)**  
- **HLP — HOLogram Layer Protocol (specifica tecnica)** *(coming soon)*  
- **HCT — HOLogram Compliance Tests** *(coming soon)*  
- **HOLoToken — sistema reputazionale non finanziario (Proof‑of‑Contribution)**  
- **Ecosystem Registry** *(coming soon)*

---

# 📄 RFC — Request for Comments

Le modifiche al protocollo avvengono tramite RFC.

Documenti:
- `RFC_TEMPLATE.md`
- `RFC/` (directory delle proposte)

Per proporre una RFC, apri una issue o invia una pull request seguendo le regole in `CONTRIBUTING.md`.

---

# 🤝 Contribuire

HOLogram è uno standard **aperto e meritocratico**.  
Ogni contributo tecnico (codice, sicurezza, test, documentazione, ricerca) viene riconosciuto tramite **HOLoToken (HRL/HCS)**.

Consulta:  
📄 `CONTRIBUTING.md`  
📄 `GOVERNANCE.md`

---

# 🔐 Notarizzazione & Verifica

Ogni versione di HOLogram è:

- firmata  
- accompagnata da SHA‑256  
- pubblicata su IPFS  
- elencata nello storico ufficiale `HASHES.txt`

Per verificare un PDF:

```bash
sha256sum HOLogram_v1.0.pdf
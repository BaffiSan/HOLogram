# Governance — HOLogram Protocol
**Modello meritocratico, decentralizzato, aperto**

Il progetto HOLogram adotta un modello di governance **aperto**, basato su  
**Proof‑of‑Contribution (HOLoToken — HRL/HCS)** e su un processo tecnico  
trasparente e versionato (**RFC**).  

Non esiste un’autorità centrale proprietaria:  
la governance è orientata al merito, alla trasparenza e alla verificabilità.

---

# 1. Principi di governance

La governance del protocollo si basa su cinque principi fondamentali:

1. **Merito tecnico** — le decisioni si basano sulla qualità del contributo.  
2. **Trasparenza** — ogni proposta, modifica e decisione deve essere pubblica e verificabile.  
3. **Decentralizzazione** — nessun singolo individuo controlla il protocollo.  
4. **Apertura** — chiunque può proporre, discutere, contribuire.  
5. **Neutralità** — il protocollo non è guidato da interessi economici, politici o commerciali.

---

# 2. Struttura organizzativa

HOLogram definisce una governance orizzontale composta da ruoli ottenuti tramite  
**HOLoToken HRL/HCS**.  
I ruoli non sono “nomine” ma **conseguenze di contributi verificati**.

## 2.1 Ruoli principali

### 🟧 **Author (pseudonymous origin)**
- Custodisce la visione del protocollo.  
- Mantiene la coerenza semantica complessiva.  
- Non ha poteri assoluti; il processo RFC può superarlo.

### 🟩 **Maintainer della Reference Implementation**
Requisito: HCS\_core ≥ soglia + revisione tra pari  
Responsabilità:
- mantenere stabile la RI  
- rivedere PR critiche  
- garantire conformità a HLP  
- coordinare rilasci e test di regressione  

### 🟦 **Security Reviewer**
Requisito: HCS\_security ≥ soglia  
Responsabilità:
- analisi delle RFC che impattano la sicurezza  
- revisione delle vulnerabilità segnalate  
- firma tecnica del modello di minaccia  

### 🟨 **Docs Steward**
Requisito: HCS\_docs ≥ soglia  
Responsabilità:
- mantenere whitepaper, appendici e documentazione  
- uniformare terminologia e semantica  
- rivedere aggiornamenti testuali  

### 🟪 **Community Contributor**
Responsabilità:
- qualunque contributo tecnico, testuale, di ricerca  
- può proporre RFC, aprire PR, discutere issue

### 🟫 **Integrator**
Responsabilità:
- implementazioni esterne (browser, OS, plug‑in)  
- riportare problemi di compatibilità  
- coordinare modifiche con gli HCT  

I ruoli non si “perdono”: l’HCS può crescere o decadere secondo policy pubbliche.

---

# 3. Processo decisionale

La governance si basa su **modelli di quorum tecnico**, non su leadership centralizzata.

## 3.1 Livelli di quorum

### 🔹 **Livello 0 — Documentazione**
- Richiede solo revisione Docs Steward  
- Approvazione con 1 reviewer

### 🔹 **Livello 1 — Modifiche minori a RI**
- 1 Maintainer + 1 reviewer esterno

### 🔹 **Livello 2 — Modifiche al protocollo (HLP)**
- RFC obbligatoria  
- 2 reviewer tecnici  
- 1 Security Reviewer se coinvolge sicurezza  
- consenso Author **non obbligatorio** (ma consigliato)

### 🔹 **Livello 3 — Modifiche strutturali / compatibilità HLP**
- RFC obbligatoria  
- 2 Maintainer + 1 Security Reviewer  
- approvazione della community (discussione pubblica)  
- firma finale nel CHANGELOG

---

# 4. Processo RFC

Ogni modifica semantica del protocollo segue la procedura RFC:

1. Creazione della RFC (template ufficiale)  
2. Discussione pubblica  
3. Revisione tecnica (2 reviewer min.)  
4. Revisione sicurezza (se necessario)  
5. Votazione tecnica (quorum)  
6. Approvazione / rifiuto  
7. Aggiornamento HLP/HCT  
8. Pubblicazione nel repository

RFC è l’unico strumento **vincolante** per modificare HOLogram.

---

# 5. HOLoToken — Proof‑of‑Contribution (HRL/HCS)

La governance utilizza HOLoToken come **ledger reputazionale non finanziario**.

## 5.1 Caratteristiche
- non trasferibile  
- non scambiabile  
- non economico  
- pubblico e verificabile  
- basato su contributi riproducibili

## 5.2 Come influisce sulla governance

L'HCS:
- determina ruoli  
- determina permessi (es. voto su RFC)  
- determina responsabilità (review, audit)  
- viene aggiornato automaticamente tramite HRL

## 5.3 Perché è importante
Prevenzione:
- catture di governance  
- abuso di potere  
- leadership non meritocratica  

Promozione:
- contributi reali  
- trasparenza  
- motivazione tecnica  

---

# 6. Ciclo di rilascio (Release Policy)

Ogni release del protocollo segue:

1. Stesura o modifica Whitepaper  
2. RFC accettata (per modifiche semantiche)  
3. Aggiornamento HLP e HCT  
4. Aggiornamento HASHES.txt  
5. Pubblicazione PDF + hash + CID IPFS  
6. Tag immutabile nel repository  
7. Annuncio pubblico nel CHANGELOG

Le release non sono temporali, ma **guidate da RFC**.

---

# 7. Trasparenza, audit e verificabilità

HOLogram adotta pratiche di trasparenza:

- changelog pubblico  
- HLP versionato  
- HCT pubblico e replicabile  
- build RI riproducibili  
- hash e CID IPFS per ogni PDF  
- audit tecnici periodici  
- ledger HRL/HCS consultabile  
- RFC come punto di verità

Nessun processo avviene “dietro le quinte”.

---

# 8. Neutralità e conflitto di interessi

- Nessun attore può imporre modifiche senza RFC.  
- I reviewer devono dichiarare eventuali conflitti.  
- Nessuna preferenza commerciale o vendor-specific.  
- L’identità reale non è rilevante; conta il contributo tecnico.  

---

# 9. Criteri di rimozione dei ruoli

I ruoli **non vengono tolti arbitrariamente**.  
Possono decadere solo per:

- inattività prolungata (HCS con decay naturale)  
- attività malevole o violazioni gravi (decise con quorum Livello 3)  
- rifiuto esplicito del ruolo da parte del contributor  

---

# 10. Evoluzione della governance

La governance stessa può essere modificata tramite **RFC**,  
seguendo quorum **Livello 3**.

Nulla è immutabile: HOLogram è progettato per evolvere insieme alla community.

---

# 11. Contatti

- **Contatto generale:** contact@hologramprotocol.org  
- **Informazioni:** info@hologramprotocol.org  
- **Security Disclosure:** security@hologramprotocol.org  
- **Sito ufficiale:** https://www.hologramprotocol.org

---

# 12. Sintesi

Il modello di governance HOLogram è:

- **aperto**  
- **meritocratico**  
- **verificabile**  
- **decentralizzato**  
- **technical‑first**  
- basato su un ledger reputazionale **non finanziario**

È progettato per garantire longevità, neutralità e integrità del protocollo  
nel tempo, indipendentemente da individui o organizzazioni.
# HOLogram — Security Disclosure Policy
**Responsible Disclosure**

La sicurezza del protocollo HOLogram è una priorità assoluta.  
Apprezziamo ogni contributo che aiuti a rafforzare la protezione dell’ecosistema e chiediamo ai ricercatori di seguire questa policy per rendere la disclosure coordinata, sicura e costruttiva.

---

# 📬 Canale di Segnalazione

Se ritieni di aver individuato una vulnerabilità o una debolezza nel protocollo, **non aprire issue pubbliche** né condividere dettagli in canali non protetti.

Usa esclusivamente il canale riservato:

**📧 security@hologramprotocol.org**

Oggetto consigliato:  
`HOLogram Security Disclosure – <titolo>`

Per segnalazioni sensibili, puoi utilizzare la cifratura PGP.

---

# 🔐 Crittografia PGP (opzionale ma consigliata)

**Email:** security@hologramprotocol.org  
**Key ID:** `0x1E5D914EFCEF87B1`  
**Fingerprint:**  
`E329 3DD8 B1A8 FEC2 F919 4A9D 1E5D 914E FCEF 87B1`  
**Validità:** fino al 01/04/2028  
**Algoritmo:** RSA 4096 bit  

🔽 **Download diretto della chiave pubblica PGP (.asc):**  
https://www.hologramprotocol.org/pgp/security.asc

Puoi cifrare il messaggio o allegare PoC protetti (es. 7‑Zip).  
La passphrase va inviata in **canale separato**.

---

# 🧭 Ambito della Responsible Disclosure

Sono considerate nel perimetro della disclosure:

- vulnerabilità nelle **specifiche del protocollo HOLogram (HLP)**;  
- comportamenti inaspettati dei moduli del layer (Input Vault, Normalizer, Persona Mixer, DP Engine, Privacy Budget, HUD);  
- problemi nelle **reference implementation**;  
- vulnerabilità nella pipeline CI/CD o nelle dipendenze ufficiali;  
- compromissione o integrità alterata di documenti notarizzati (PDF, HASHES.txt, CID/IPFS).

---

# 🚫 Fuori ambito

Le seguenti segnalazioni **non** rientrano nel perimetro security:

- refusi, errori di impaginazione o problemi grafici;  
- enumerazioni di directory non sensibili;  
- issue prive di impatto o non riproducibili;  
- considerazioni teoriche prive di vettore concreto;  
- problematiche relative a infrastrutture esterne non gestite dal progetto.

---

# 📝 Check‑list della segnalazione

Per facilitare il triage, includi:

1. **Titolo chiaro e severità stimata (High/Medium/Low)**  
2. **Descrizione tecnica** del problema  
3. **Modulo/area impattata**  
4. **Passi per riprodurre** (PoC minimo, comandi, input/eventi)  
5. **Ambiente** (OS, browser, versione, commit)  
6. **Impatto atteso vs osservato**  
7. **Mitigazione proposta** (se disponibile)  
8. **Preferenze di attribuzione** (nome/pseudonimo o anonymous)

---

# ⏱ Tempi e Processo di Gestione (SLA indicativi)

- **Triage iniziale:** entro **7 giorni**  
- **Conferma ricezione:** entro **72 ore lavorative**  
- **Aggiornamenti:** almeno ogni **14 giorni**  
- **Disclosure coordinata:** in genere **90 giorni** prima della pubblicazione dei dettagli tecnici  
  (salvo accordi diversi con il ricercatore)

---

# 🛡 Coordinated Disclosure & Safe Harbor

Agendo in buona fede nell’ambito di questa policy:

- ci impegniamo a **non intraprendere azioni legali** contro ricercatori per test proporzionati;  
- non sono consentite attività che compromettano la disponibilità dei servizi, causino danni o comportino accessi non autorizzati;  
- non è consentita l’esfiltrazione di dati.

Se la vulnerabilità è valida e segnalata responsabilmente:

- la disclosure avverrà in modo coordinato;  
- la mitigazione sarà pubblicata insieme a un **advisory trasparente**;  
- il ricercatore potrà essere **ringraziato pubblicamente** (se desiderato).

---

# 🏆 Hall of Thanks

Ringraziamo i ricercatori che contribuiscono responsabilmente alla sicurezza del protocollo.  
Per l’attribuzione, puoi indicare:

- nome o pseudonimo (es. *BaffiSan*)  
- eventuale link  
- ambito della segnalazione  

Accettiamo e valorizziamo contributi pseudonimi.

---

# 📩 Contatto Rapido

**Email:** security@hologramprotocol.org  
Oggetto consigliato: `HOLogram Security Disclosure – <breve titolo>`  
Crittografia PGP: vedi sezione dedicata in alto.

---

# 🔚 Nota finale

HOLogram è un protocollo aperto: la sicurezza cresce con la community.  
Grazie per il tuo contributo.
# RFC Title
*Breve, descrittivo, non commerciale.*

**Stato:** Draft / Review / Accepted / Rejected  
**Autore:** <nome o pseudonimo>  
**Revisori iniziali:** <facoltativo>  
**Versione proposta:** HLP vX.Y  
**Data:** <AAAA-MM-GG>  

---

# 1. Abstract

Fornire una sintesi breve (5–10 righe) della proposta:  
- cosa cambia  
- perché serve  
- quali moduli impatta  
- quale beneficio apporta al protocollo

---

# 2. Motivazione

Descrivere:
- il problema o limite attuale del protocollo HOLogram  
- perché la modifica è necessaria  
- casi d’uso concreti  
- rischi o vulnerabilità che questa RFC intende risolvere  

Questa sezione *non deve* contenere dettagli tecnici approfonditi: solo il “perché”.

---

# 3. Definizione della modifica proposta

Descrivere con precisione:
- cosa viene modificato  
- cosa viene aggiunto  
- cosa viene rimosso (“breaking change”)  
- riferimenti puntuali all’HLP esistente

Esempio:
Modifica alla sezione 5.2 Pointer & Scroll Normalizer:

aggiunta soglia dinamica di smoothing
modifica parametro alpha → alpha_sessionvariant

---

# 4. Moduli impattati (HLP Components)

Indicare quali componenti HOLogram vengono modificati:

- [ ] ShadowDOM Input Vault  
- [ ] Pointer & Scroll Normalizer  
- [ ] Persona Mixer  
- [ ] Behavioral Differential Privacy Engine  
- [ ] Behavioral Privacy Budget  
- [ ] Exposure HUD  
- [ ] Output Projector  
- [ ] HID Cloak (opzionale)  
- [ ] Documentazione / Semantica HLP  
- [ ] Test HCT  
- [ ] Ecosystem Registry  
- [ ] HOLoToken (HRL/HCS)

---

# 5. Specifica tecnica dettagliata

Descrivere in modo rigoroso, tecnico e formale:

- Algoritmi  
- Parametri  
- Range numerici  
- Regole operative  
- Effetti sul comportamento sintetico  
- Impatti sulla sensibilità del segnale  
- Impatti sulla rilevabilità  

Esempio di struttura:

## 5.1 Nuovi parametri introdotti  
## 5.2 Aggiornamento formule / pseudocodice  
## 5.3 Regole per implementazioni conformi  
## 5.4 Comportamento edge‑case  
## 5.5 Differenze rispetto alla versione precedente  
## 5.6 Note di compatibilità  

---

# 6. Impatto sulla sicurezza

Analizzare se la proposta:

- aumenta la protezione  
- introduce nuovi rischi  
- crea segnali identificanti  
- altera il profilo di correlabilità  
- richiede aggiornamento del threat model  
- può essere rilevata da script aggressivi  
- impatta sistemi anti‑bot  

Questa sezione è essenziale.

---

# 7. Impatto sull’usabilità (UX)

Descrivere eventuali effetti su:

- naturalezza dei movimenti  
- latenza percepita  
- compatibilità con applicazioni time‑sensitive  
- dipendenza da browser specifici  
- casi in cui la proposta può ridurre UX

---

# 8. Impatto sull’HCT (Test di Conformità)

Indicare se la RFC:

- introduce nuovi test  
- modifica test esistenti  
- elimina test obsoleti  

Esempio:


Nuovo test HCT: verifica stabilità smoothing entro range umano.

---

# 9. Compatibilità e migrazione

Descrivere:

- impatti sulle implementazioni esistenti  
- cosa devono fare i maintainer per adottare la nuova versione  
- se la modifica è retro‑compatibile  
- se richiede un bump semantico di versione:
  - patch (v1.0.x)  
  - minor (v1.x)  
  - major (vX.0)  

---

# 10. Alternative considerate

Elencare brevemente le alternative tecniche valutate e perché NON sono state adottate.  
Questa sezione serve a mostrare che la proposta è stata comparata con altre soluzioni.

---

# 11. Processo di valutazione

Descrivere:

- quali comunità o maintainer sono coinvolti  
- quali requisiti devono essere soddisfatti  
- quale quorum tecnico è richiesto (es. Security Reviewer + Maintainer RI)  
- eventuali dipendenze da altre RFC  

---

# 12. ROADMAP

Indicare:

- timeline prevista  
- step di implementazione  
- step di validazione  
- step di rollout  

---

# 13. Appendici (facoltative)

- Diagrammi  
- Pseudocodice esteso  
- Calcoli  
- Benchmark  
- Logiche matematiche  
- Modelli alternativi evocati  
- Prototipi  

---

# 14. Decisione finale (compilata dai maintainer)

**Stato:** Accepted / Rejected / Deferred  
**Data decisione:** <AAAA‑MM‑GG>  
**Revisori tecnici:** <lista>  
**Note:** <note aggiuntive>

---

# 15. Changelog RFC

Annotare modifiche alla RFC stessa:

- v0.1 — prima bozza  
- v0.2 — integrazione feedback community  
- v1.0 — approvazione finale  
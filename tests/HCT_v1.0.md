HOLogram Compliance Tests — Suite di conformità (v1.0)
Test ufficiali per verificare che un’implementazione sia conforme a HLP_SPEC v1.0.

0. Stato del documento

Versione: HCT v1.0
Data: Marzo 2026
Stato: Stable
Fonte semantica: HLP_SPEC v1.0
Obiettivo: Verificare se un’implementazione può dichiararsi HLP‑compatible
Ambito: Test funzionali, test di plausibilità umana, test anti‑rilevazione, test di privacy


1. Introduzione
HCT (HOLogram Compliance Tests) definisce i test ufficiali che ogni implementazione del protocollo HOLogram deve superare.
I test verificano:

corretto comportamento dei moduli
assenza di leak comportamentali
plausibilità umana dell’output
resistenza alla rilevazione
conformità semantica con HLP v1.0

Ogni modulo ha test obbligatori e opzionali.

2. Struttura dei test
HCT è diviso in 4 categorie:
1. Test Funzionali (HCT-F)
2. Test di Plausibilità Umana (HCT-P)
3. Test di Privacy & Non-Riconducibilità (HCT-N)
4. Test Anti-Rilevazione (HCT-A)

Ogni test specifica:

ID
Obiettivo
Condizioni iniziali
Procedura
Risultato atteso
Criteri di successo


3. Requisiti di conformità
Un’implementazione può definirsi HLP‑compatible se:

supera tutti i test obbligatori HCT-F
supera tutti i test obbligatori HCT-N
supera almeno l’80% dei test HCT-P
supera almeno l’80% dei test HCT-A


4. TEST SUITE

✅ 4.1 HCT‑F — Test Funzionali
Test per verificare che il layer rispetti la semantica tecnica.

HCT‑F01 — Rimozione micro‑tempi di digitazione
Obiettivo: verificare che la pagina non riceva tempi reali di keydown/keyup.
Procedura:

Registrare performance.now() su keydown/keyup.
Simulare digitazione reale (eventi nativi).
Catturare gli eventi prodotti dal layer.

Risultato atteso:

gli intervalli temporali nell’output NON devono corrispondere a quelli reali.

Successo:
abs(delta_real - delta_output) > 8 ms (minimo).

HCT‑F02 — Quantizzazione coordinate
Obiettivo: verificare che le coordinate del puntatore siano quantizzate.
Procedura:

Muovere il puntatore in traiettoria lineare ad alta precisione.
Registrare coordinate input raw vs output.

Risultato atteso:
output.x == round(raw.x / qStep) * qStep

HCT‑F03 — Downsampling eventi movimento
Obiettivo: frequenza ≤ 60 Hz.
Risultato atteso:
count(events_output) / second ≤ 60.

HCT‑F04 — Ordine semantico eventi DOM
Obiettivo: gli eventi sintetici devono rispettare l’ordine DOM.
Risultato atteso:
mousedown → mouseup → click
focus → input → change

HCT‑F05 — Reset sessione
Obiettivo: nuova persona sintetica a ogni sessione.
Risultato atteso:
Parametri del Mixer cambiati dopo reset di tab o dominio.

✅ 4.2 HCT‑P — Test di Plausibilità Umana
Validity percepibile come input umano naturale.

HCT‑P01 — Smoothing realistico
Obiettivo: evitare movimenti “robotici”.
Procedura: muovere il puntatore con micro‑tremolii umani.
Risultato atteso:
La differenza tra punti successivi è distribuita in modo gaussian‑like.

HCT‑P02 — Coerenza session‑consistent
Obiettivo: persona sintetica coerente per tutta la sessione.
Risultato atteso:
Parametri (velocità apparente, jitter) restano entro range fisso.

HCT‑P03 — Micro‑pause plausibili nello scroll
Risultato atteso:
Ogni ~1–4 secondi compaiono micro‑pause leggere e non regolari.

✅ 4.3 HCT‑N — Test di Privacy & Non‑Riconducibilità
Test critici per proteggere l’utente.

HCT‑N01 — Assenza micro‑tempi raw
Obiettivo: eliminare completamente la biometria temporale.
Risultato atteso:
stddev(delta_output) < 1.5ms, randomizzato.

HCT‑N02 — Assenza coordinate raw
Obiettivo: impedire fingerprinting geometrico.
Risultato atteso:
Nessuna coppia (dx, dy) dell’output deve corrispondere 1:1 al raw.

HCT‑N03 — Ripetibilità sintetica non correlabile
Procedura:

creare due sessioni diverse
confrontare parametri di persona sintetica

Risultato atteso:
Cambiamento significativo → sessioni non correlabili.

HCT‑N04 — Stabilità DP Engine
Risultato atteso:
Modifiche minime dell’input NON devono cambiare significativamente l’output.

✅ 4.4 HCT‑A — Test Anti‑Rilevazione
Test per impedire che lo script lato pagina riconosca HOLogram.

HCT‑A01 — Anti‑Precision Detection
Risultato atteso:
L’engine NON introduce quantizzazione così grossolana da essere rilevabile con:
variance(dx_output) / variance(dx_input) 

La ratio deve essere nel range naturale 0.6–0.9.

HCT‑A02 — Anti‑Timing Detection
Procedura: misurare jitter inserito dal DP Engine.
Risultato atteso:
Il jitter deve essere sotto la soglia percettibile (~5ms) ma sufficiente a rimuovere biometric timing.

HCT‑A03 — Anti‑Pattern Detection
Obiettivo: nessun pattern deterministico cross‑session.
Risultato atteso:
Sequenza di smoothing NON deve essere ripetibile identica al 100%.

HCT‑A04 — Anti‑Consistency Leak
Obiettivo: la quantizzazione MUST essere variabile con un range policy-driven.
Valori statici permettono fingerprinting.

✅ 5. Strumenti di test (Tooling)
HCT include (o includerà):
/tests/scripts/

script JS per catturare eventi raw
script per analizzare output (frequency, dx/dy, jitter)
script comparazione sessioni

/tests/reports/

output JSON dei test
grafici di plausibilità
heatmap del puntatore sintetico


✅ 6. Risultati e certificazione
Ogni implementazione deve produrre:
HCT_report.json
HCT_passed: X/Y
HLP_compatible: true/false
Note: <test falliti>


✅ 7. Versionamento HCT

v1.0: suite iniziale
v1.1: introdurrà test per HID Cloak
v2.0: integrazione auto‑benchmarking + DP adaptive suite


✅ 8. Conclusione
HCT v1.0 definisce la suite minima di conformità necessaria per garantire che ogni implementazione HOLogram:

riduca la riconducibilità
mantenga naturalezza
sia resistente alla rilevazione
rispetti la semantica del protocollo
sia verificabile e riproducibile

Solo le implementazioni che superano i test obbligatori possono dichiararsi:
✅ HOLogram HLP‑compatible
✅ Compliant with HLP_SPEC v1.0
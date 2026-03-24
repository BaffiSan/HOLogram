HOLogram Layer Protocol — Specifica Tecnica (v1.0)
Human Obfuscation Layer — Semantica, interfacce, moduli e requisiti di conformità


0. Status del documento

Versione: HLP v1.0
Data: Marzo 2026
Stato: Stable
Fonte semantica: Whitepaper HOLogram v1.0
Validità: questa specifica definisce la semantica ufficiale del Layer.
Conformità: ogni implementazione deve rispettare i requisiti obbligatori definiti in questo documento per potersi definire HLP‑compatible.


1. Introduzione
HOLogram è un Human Obfuscation Layer progettato per proteggere la biometria comportamentale riducendo la fedeltà dei segnali generati dall’utente (digitazione, movimenti del puntatore, scroll, micro‑pattern).
HLP definisce la semantica minima che ogni implementazione deve rispettare:

moduli obbligatori
logica di trasformazione dei segnali
principi di sicurezza
requisiti per conformità (HCT)
comportamento osservabile dal punto di vista del sito web


2. Principi Fondativi (normativi)
Le implementazioni MUST rispettare i seguenti principi:


Human‑centric privacy
Protezione dell’identità comportamentale dell’utente.


Local‑only & zero‑retention
Nessun dato comportamentale può essere memorizzato, inviato o sincronizzato.


Minimizzazione della riconducibilità
Must: riduzione della granularità dei segnali (tempi, geometrie).


Offuscamento non manipolativo
Must: preservare intenzione e contenuto dell’azione.
Must NOT: cambiare significato dell’input.


Naturalità dell’interazione
L’output deve essere plausibilmente umano.


Adaptive Obfuscation
Il livello di protezione è dinamico e regolato dal Privacy Budget.


Trasparenza (HUD)
Must: fornire visibilità minima all’utente (livello protezione).


Neutralità tecnologica
Nessun vincolo su browser, OS o linguaggio.



3. Architettura del Layer (Overview)
HLP definisce 6 moduli obbligatori e 1 opzionale:
1. Input Capture (Vault)
2. Signal Normalizer
3. Persona Mixer
4. Differential Privacy Engine
5. Behavioral Privacy Budget
6. Output Projector
7. (Opzionale) HID Cloak — livello OS

Il flusso MUST essere:
Raw Input → Vault → Normalizer → Persona Mixer → DP Engine → Budget → Output


4. Moduli del Protocollo
4.1 ShadowDOM Input Vault (Obbligatorio)
Funzione
Isolare eventi raw ad alta fedeltà ed eliminare micro‑tempi.
Eventi minimi da intercettare:

keydown / keyup / keypress
mousemove / pointermove
mousedown / mouseup
wheel / scroll
focus / blur / input

Requisiti

MUST: preservare contenuto semantico (testo, coordinate, click).
MUST NOT: lasciare visibili tempi reali della digitazione.
MUST: sostituire gli eventi raw con eventi normalizzati (input/change).


4.2 Pointer & Scroll Normalizer (Obbligatorio)
Obiettivo
Ridurre unicità geometrica e temporale dei pattern di movimento.
Trasformazioni richieste

Downsampling → frequenza target ≤ 60 Hz
Quantizzazione coordinate (round(coord / qStep) * qStep)
Smoothing controllato:
smoothed = prev + α * (quantized - prev)



Regole normative

α MUST essere entro range umano plausibile (0.08–0.25).
La quantizzazione MUST essere dinamica (policy‑driven).
L’output MUST NOT generare traiettorie artificialmente robotiche.


4.3 Persona Mixer (Obbligatorio)
Funzione
Evitare che “l’offuscamento” diventi impronta.
Regole

Ogni sessione MUST generare una persona sintetica.
La persona MUST rimanere coerente per tutta la sessione.
Una nuova sessione MUST generare una persona differente.
Parametri MUST essere entro range plausibili:

pointerJitterRange
smoothingAggressiveness
typingLatencyOffset
curvatureSoftening



Obiettivo
Creare variabilità session‑consistent non riconducibile all’utente reale.

4.4 Behavioral Differential Privacy Engine (Obbligatorio)
Funzione
Ridurre la sensibilità dei segnali a micro‑variazioni input.
Requisiti tecnici

Applicare jitter temporale minimo
Applicare rumore calibrato sulle variazioni
Applicare stabilizzazione evitando regolarità artificiali

Semantica
Piccole variazioni nel comportamento reale MUST NOT produrre differenze significative nell’output.

4.5 Behavioral Privacy Budget (Obbligatorio)
Funzione
Limitare esposizione comportamentale nel tempo.
Costruzione del Budget
Ogni evento ha un costo:

keypress = 3
mousemove = 1
scroll = 2
click = 1

Il budget MUST diminuire in base a:

frequenza eventi
complessità geometrica
entropia dei pattern

Escalation
Se il budget scende sotto soglie predefinite:

MUST: aumentare smoothing
MUST: aumentare quantizzazione
MUST: ridurre frequenza eventi
MUST NOT: bloccare input salvo casi estremi

Rigenerazione

idle
eventi a bassa intensità
reset sessione


4.6 Exposure HUD (Obbligatorio)
Requisiti minimi

mostrare livello di protezione
mostrare consumo budget
mostrare escalation
non interferire con UX
non rivelare parametri interni (evitare fingerprinting del layer)


4.7 HID Cloak (Opzionale)
Protezione OS‑level degli eventi prima del browser.
Requisiti (se implementato)

isolare eventi hardware
applicare normalizzazione minima
non introdurre interferenze critiche
richiede privilegi elevati


5. Output Projector (Obbligatorio)
Requisiti del segnale finale
Deve essere:

umano
plausibile
coerente con il contesto
indistinguibile da un utente reale
non correlabile tra sessioni/domìni

MUST

rispettare semantica API DOM
rispettare ordine eventi standard
generare eventi conformi senza leak temporali ad alta risoluzione


6. Semantica delle Sessioni
Una sessione inizia quando:

viene aperto un tab
l’utente entra su un nuovo dominio
il sistema viene resettato

Durante la sessione:

la persona sintetica MUST rimanere costante
il budget MUST essere rigenerato parzialmente
i moduli MUST mantenere coerenza interna


7. Requisiti di Conformità (HCT v1)
Un’implementazione è HLP‑compatible se supera i seguenti test:
7.1 Test funzionali

coerenza eventi DOM
assenza eventi raw ad alta risoluzione
ordine semantico corretto

7.2 Test di plausibilità umana

smoothing entro range naturale
nessuna traiettoria meccanica
variazione session‑consistent

7.3 Test anti‑rilevazione

difficoltà rilevazione quantizzazione
assenza di pattern costanti cross‑session
nessuna regolarità algoritmica riconoscibile

7.4 Test di privacy

assenza leak micro‑tempi
assenza leak coordinate raw
coerenza DP Engine


8. Versionamento Semantico del Protocollo
HLP usa versionamento:

X.0 → cambiamenti semantici major (breaking changes)
0.X → aggiornamenti minori alla semantica dei moduli
0.0.X → bugfix e miglioramenti non semantici

Modifiche a HLP richiedono RFC obbligatoria.

9. Note finali
Questa specifica è la fonte normativa del protocollo HOLogram.
Il whitepaper fornisce contesto, motivazioni e spiegazioni;
HLP_SPEC definisce invece cosa significa essere conforme.

10. Riferimenti

HOLogram Whitepaper v1.0
HCT v1 (in preparazione)
HOLoToken — HRL/HCS
RFC directory
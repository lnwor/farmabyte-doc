# Farmabyte - Progettazione

## Progettazione Architetturale

### Requisiti non funzionali

Dall'analisi dei requisiti sono emersi i seguenti requisiti non funzionali:
- Tempo di risposta
- Usabilità
- Integrità dei dati
- Protezione dei dati 
- Sicurezza delle comunicazioni

La protezione dei dati e delle comunicazioni assume fondamentale importanza vista la natura del software, che deve trattare dati personali e sanitari dei clienti. La compromissione di questi risulterebbe in una grave perdita finanziaria e di immagine, senza considerare i danni apportati alla privacy degli utenti. L'utilizzo di tecnologie standard per la cifratura delle comunicazioni quali HTTPS e TLS è quindi obbligatorio, oltre ad una corretta configurazione di queste. Inoltre, sarà necessario assicurare la sicurezza fisica dei dati immagazzinati nel sistema.
L'introduzione di misure di sicurezza non compromette l'usabilità del sistema, ma potrebbe peggiorare leggermente le prestazioni del sistema: è possibile comunque bilanciare le due esigenze senza troppi problemi. Va notato inoltre che il sistema non presenta vincoli di tempo particolarmente stringenti (nessun vincolo real-time).

<br>

### Scelta dell'architettura

Dopo una rapida analisi, si è constatato che l'architettura più adeguata per il sistema è l'**architettura client-server a 3 livelli**.

**L1 - Client:**
<br>
Rispettando il principio del "minimo privilegio" per dividere le varie funzionalità si è deciso di sviluppare due Client distinti:

- Un client per le funzionalità relative ai clienti (registrati e non)
- Un client per la gestione della farmacia da parte di un operatore (farmacista)

**L2 - Server:**
<br>
In modo analogo alla scomposizione dei client, si è deciso di scomporre i server in base alle funzionalità offerte ai client, si hanno quindi tre server:

- Un server che fornisce i servizi ai clienti registrati e non
- Un server che funge da pannello di controllo per i farmacisti
- Un server per le funzionalità di login

**L3 - Persistenza:**
<br>
La gestione della persistenza verrà implementata in un server dedicato sul quale sarà installato un DBMS che gestisca i dati di tutte le farmacie aderenti al servizio.<br>
---L'interfacciamento con il DBMS avverrà mediante la metodologia "forza bruta" utilizzando i metodi CRUD.---


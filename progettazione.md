# Farmabyte - Progettazione

## Progettazione Architetturale

### Requisiti non funzionali

Dall'analisi dei requisiti sono emersi i seguenti requisiti non funzionali:
- Tempo di risposta
- Usabilità
- Integrità dei dati
- Protezione dei dati 
- Sicurezza delle comunicazioni

La protezione dei dati e delle comunicazioni assume fondamentale importanza vista la natura del software, che deve trattare dati personali e sanitari dei clienti. La compromissione di questi risulterebbe in una grave perdita finanziaria e di immagine, senza considerare i danni apportati alla privacy degli utenti. Inoltre, sarà necessario assicurare la sicurezza fisica dei dati immagazzinati nel sistema.
L'introduzione di misure di sicurezza delle comunicazioni e protezione dei dati non compromette l'usabilità del sistema, ma potrebbe peggiorarne leggerlmente le prestazioni: è possibile comunque bilanciare le due esigenze senza eccessive complicazioni mediante le tecnologie esposte in seguito. Va notato inoltre che il sistema non presenta vincoli di tempo particolarmente stringenti (nessun vincolo real-time).

<br>

### Scelta dell'architettura

Dopo una rapida analisi, si è constatato che l'architettura più adeguata per il sistema è l'**architettura client-server a 3 livelli**.

**L1 - Client:**
<br>
La parte di Client sarà implementata da due interfacce web differenti:

- Un'interfaccia per le funzionalità relative ai clienti (registrati e non)
- Un'interfaccia per la gestione della farmacia da parte di un operatore (farmacista)

**L2 - Server:**
<br>
Rispettando il principio del "minimo privilegio" per limitare i danni in caso di attacco e per distribuire meglio il carico, si è deciso di scomporre i server in base alle funzionalità offerte. Si hanno quindi tre server:

- Un server che fornisce i servizi ai clienti registrati e non
- Un server che funge da pannello di controllo per i farmacisti
- Un server per le funzionalità di autenticazione

**L3 - Persistenza:**
<br>
La gestione della persistenza verrà implementata in un server dedicato sul quale sarà installato un DBMS che gestisca i dati di tutte le farmacie aderenti al servizio.<br>
---L'interfacciamento con il DBMS avverrà mediante la metodologia "forza bruta" utilizzando i metodi CRUD.---

Infine, dopo un'attenta analisi, si è optato per l'adozione del pattern **Broker**: un componente verrà interposto alla comunicazione Client-Server e avrà il compito di indirizzare le richieste dei client al relativo server, effettuando un controllo sulle sessioni attive per determinare lo stato del client. La scomposizione in diversi client e server consente di avere una separazione netta tra gli applicativi del cliente e del farmacista, in modo da localizzare le operazioni critiche e ottenere maggiore protezione dei dati.
<br>
Chiaramente l'affidabilità del sistema dipende dalla robustezza del broker e soprattutto del sistema di autenticazione.

Si riportano di seguito i diagrammi di package e componenti che descrivono l'architettura del sistema.

_\*inserire immagine dei diagrammi qui\*_

### Da aggiungere un breve paragrafo che esponga le tecnologie da utilizzare

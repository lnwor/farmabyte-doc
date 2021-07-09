# Analisi del Problema
## Analisi Documento dei Requisiti: Analisi delle Funzionalità

### Tabella Funzionalità

|Funzionalità|Tipo|Grado Complessità|Requisiti Collegati|
|:-:|:-:|:-:|:-:|
|GestioneFarmacia|Memorizzazione dati e gestione dati|complessa| R5F, R9F, R10F, R11F, R12F, R13F, R14F, R15F |
|Registrazione|Interazione esterno e memorizzazione dati|semplice| R4F |
|RicercaFarmaci|Interazione esterno e lettura dati|semplice| R1F, R2F, R3F |
|Login|Interazione esterno e lettura dati|semplice| R7F |
|GestionePrenotazioni|Interazione esterno e memorizzazione dati|comp| R2F, R6F, R8F |
|ScritturaLog|Memorizzazione dati|semplice| R16F |

<br>

### GestioneFarmacia: Tabella Informazioni/Flusso

|Informazione|Tipo|Livello protezione/privacy|Input/Output|Vincoli|
|:-:|:-:|:-:|:-:|:-:|
|Nome Cliente|semplice|Protezione alta|Output|Non più di 40 caratteri|
|Cognome Cliente|semplice|Protezione alta|Output|Non più di 40 caratteri|
|Codice Fiscale Cliente|semplice|Protezione media|Output|Deve essere di 16 caratteri|
|Stato Cliente|semplice|Protezione media|Output||
|Lista Farmaci|composto|Protezione alta|Output||
|Lista Prenotazioni|composto|Protezione molto alta|Output||


<br>

### RicercaFarmaci: Tabella Informazioni/Flusso

|Informazione|Tipo|Livello protezione/privacy|Input/Output|Vincoli|
|:-:|:-:|:-:|:-:|:-:|
|Nome Farmaco|semplice|Protezione bassa|Input||
|Località Utente|composto|Protezione alta|Input||
|Lista Farmacie Pertinenti|composto|Protezione bassa|Output|Non più di 10 farmacie| 

<!-- 
Località Utente = {Latitudine, Longitudine};

Lista farmacie pertinenti = {NomeFarmacia1, IndirizzoFarmacia1, DistanzaFarmacia1, ... , NomeFarmaciaN, IndirizzoFarmaciaN, DistanzaFarmaciaN} 
-->

<br>

### Registrazione: Tabella Informazioni/Flusso

|Informazione|Tipo|Livello protezione/privacy|Input/Output|Vincoli|
|:-:|:-:|:-:|:-:|:-:|
|Nome Cliente|Semplice|Protezione media|Input|Non più di 40 caratteri|
|Cognome Cliente|semplice|Protezione media|Input|Non più di 40 caratteri|
|Data di Nascita|semplice|Protezione media|Input|Deve avere più di 16 anni e data di nascita successiva al 1900|
|Codice Fiscale|semplice|Protezione media|Input|Deve essere di 16 caratteri|
|Email| semplice|Protezione alta|Input|Deve essere di 256 caratteri e del formato giusto|
|Password|semplice|Protezione molto alta|Input|Deve essere almeno di 8 caratteri, di cui uno alfabetico e uno numerico|

<br>

### ScritturaLog: Tabella Informazioni/Flusso

|Informazione|Tipo|Livello protezione/privacy|Input/Output|Vincoli|
|:-:|:-:|:-:|:-:|:-:|
|Data |semplice|Protezione media|Input|Non più di 40 caratteri|
|Ora|semplice|Protezione media|Input|Non più di 40 caratteri|
|Attore|semplice|Protezione alta|Input|Non più di 20 caratteri|
|Identificativo Farmacia|semplice|Protezione alta|Input|Non più di 20 caratteri|
|Operazione Eseguita|composto|Protezione alta|Input||
|Evento|composto|Protezione molto alta|Input||

<br>

### AnalisiLog: Tabella Informazioni/Flusso

|Informazione|Tipo|Livello protezione/privacy|Input/Output|Vincoli|
|:-:|:-:|:-:|:-:|:-:|
|Notifica|composto|Protezione bassa|Output||

<br>

### Login: Tabella Informazioni/Flusso


|Informazione|Tipo|Livello protezione/privacy|Input/Output|Vincoli|
|:-:|:-:|:-:|:-:|:-:|
|Email|semplice|Protezione molto alta|Input|Non più di 256 caratteri|
|Password|semplice|Protezione molto alta|Input|Non più di 50 caratteri|

<br>

### GestionePrenotazione: Tabella Informazioni/Flusso

|Informazione|Tipo|Livello protezione/privacy|Input/Output|Vincoli|
|:-:|:-:|:-:|:-:|:-:|
|Data invio|semplice|Protezione media|Input|Non più di 40 caratteri|
|Ora invio|semplice|Protezione media|Input|Non più di 40 caratteri|
|Data prenotazione|semplice|Protezione media|Input|Solo una data compresa tra il giorno successivo e 14 giorni dopo|
|Elenco farmaci|composto|Protezione alta|Input|1. Non più di 5 elementi per ogni farmaco <br> 2. Non più di 20 elementi in totale|
|Identificativo farmacia|semplice|Protezione alta|Input|Non più di 20 caratteri|
|Identificativo cliente|semplice|Protezione molto alta|Input|Non più di 20 caratteri|
|Lista prenotazioni | composto | Protezione alta | Output ||

<br>

## Analisi Documento dei Requisiti: Analisi dei Vincoli
### Tabella Vincoli

|Requisito|Categorie|Impatto|Funzionalità|
|:-:|:-:|:-:|:-:|
|Semplicità dell'interfaccia|Usabilità|Intuitività di utilizzo| GestioneFarmacia, Registrazione, RicercaFarmaci, Login, NuovaPrenotazione |
|Velocità della ricerca dei dati|Tempo di Risposta|Maggiore reattività|GestioneFarmacia, Registrazione, RicercaFarmaci, Login, NuovaPrenotazione|
|Velocità di memorizzazione dei dati|Tempo di Risposta|Maggiore reattività|GestioneFarmacia, Registrazione, Login, NuovaPrenotazione|
|Controllo Accessi| Sicurezza | Peggiorano tempo di risposta e usabilità, migliorano la privacy dei dati | GestioneFarmacia, NuovaPrenotazione |
|Protezione dei Dati| Sicurezza | Peggiorano tempo di risposta, migliorano la privacy dei dati | GestioneFarmacia, Registrazione, RicercaFarmaci, Login, NuovaPrenotazione |

<br>

## Analisi Documento dei Requisiti: Analisi delle Interazioni
### Tabella Maschere

|Maschera|Informazioni|Funzionalità|
|:-:|:-:|:-:|
|Home Gestione|Messaggio di benvenuto e scelta della funzionalità|GestioneFarmacia|
|View Login|Email, Password|Login|
|View Prenotazioni|Lista Prenotazioni|GestioneFarmacia|
|View ResocontoUtenti|Nome Cliente, Cognome Cliente, Codice Fiscale Cliente, Stato Cliente|GestioneFarmacia|
|View VerificaIdentità|Nome Cliente, Cognome Cliente, Codice Fiscale Cliente |VerificaIdentità|
|View Farmaci|Lista Farmaci|GestioneFarmacia|
|Home Servizio|Messaggio di benvenuto, Nome farmaco, Località utente, Lista farmacie pertinenti|RicercaFarmaci|
|View Registrazione| Nome Cliente, Cognome Cliente, Data di Nascita, Codice Fiscale, Email, Password |Registrazione|
|View NuovaPrenotazione|Data invio, Ora invio, Data prenotazione, Elenco farmaci, Identificativo farmacia<!--, Identificativo cliente-->|NuovaPrenotazione|
|View PrenotazioniPersonali|Lista Prenotazioni|ListaPrenotazioni|

<br>

## Tabella Sistemi Esterni

|Sistema|Descrizione|Protocollo di Interazione|Livello di Sicurezza|
|:-:|:-:|:-:|:-:|
|Gestione Magazzino | Sistema che si occupa della gestione dei farmaci in magazzino | GestioneMagazzino mette a disposizione delle funzionalità di elencazione dei farmaci |Medio livello di sicurezza perchè protegge i dati della farmacia |

<br>

## Analisi Ruoli e Responsabilità
### Tabella Ruoli

|Ruolo|Responsabilità|Maschere|Riservatezza|Numerosità|
|:-:|:-:|:-:|:-:|:-:|
|Farmacista|Gestione di tutte le informazioni relative agli utenti e alle prenotazioni di una farmacia|Home Gestione, View Login, View Prenotazioni, View ResocontoUtenti, View VerificaIdentità, View Farmaci, |E' richiesto un alto grado di riservatezza |Massimo 10 farmacisti per ogni farmacia|
|Cliente|Ricerca di un farmaco senza necessità di login|Home Servizio, View Login, View Registrazione |E' richiesto un medio grado di riservatezza|Illimitati|
|ClienteRegistrato|Ricerca e prenotazione di farmaci presso una farmacia|Home Servizio, View NuovaPrenotazione, View PrenotazioniPersonali| E' richiesto un alto grado di riservatezza |Illimitati|

<br>

### Farmacista: Tabella Ruolo-Informazioni

|Informazione|Tipo di Accesso|
|:-:|:-:|
|Nome Cliente|Lettura|
|Cognome Cliente|Lettura|
|Codice Fiscale|Lettura|
|Stato Cliente|Lettura/Scrittura|
|Lista Farmaci|Lettura/Scrittura|
|Lista Prenotazioni|Lettura/Scrittura|

<br>

### ClienteRegistrato: Tabella Ruolo-Informazioni

|Informazione|Tipo di Accesso|
|:-:|:-:|
|Nome Cliente|Lettura/Scrittura| <!-- Modificabili nel caso in cui un cliente cambi nome dall'anagrafe, tanto l'identificazione non avviene attraverso questi dati -->
|Cognome Cliente|Lettura/Scrittura|
|Data di Nascita|Lettura|
|Codice Fiscale|Lettura|
|Email|Lettura/Scrittura|
|Password|Lettura/Scrittura|
|Nome Farmaco|Scrittura|
|Località Utente|Lettura|
|Lista Farmacie Pertinenti |Lettura|
|Data prenotazione|Scrittura|
|Elenco farmaci|Scrittura|


<br>

### Cliente: Tabella Ruolo-Informazioni

|Informazione|Tipo di Accesso|
|:-:|:-:|
|Nome Farmaco|Scrittura|
|Località Utente|Scrittura|
|Lista Farmacie Pertinenti |Lettura|

<br>

## Scomposizione del Problema

### Tabella Scomposizione Funzionalità

|Funzionalità|Scomposizione|
|:-|:-|
|GestioneFarmacia| ResocontoFarmaci,<br> ResocontoUtenti, <br>ControlloPrenotazioni,<br> VerificaIdentità |
|GestionePrenotazioni | NuovaPrenotazione, <br> ListaPrenotazioni |
|ControlloPrenotazioni | ConfermaPrenotazione |
|ResocontoUtenti| SospensioneUtenza |

<br>

Non sono presenti legami di esclusione o di necessità tra le sotto-funzionalità del sistema. 

<br>

## Creazione Modello del Dominio

Il seguente diagramma delle classi rappresenta la parte di modello del dominio relativa al sistema.

Modellodominio.drawio

## Architettura Logica: Struttura
Diagrammi.drawio
### Diagramma dei package



### Diagramma delle classi: Farmacia

### Diagramma delle classi: Utente

### Diagramma delle classi: Gestione Accesso

## Architettura Logica: Interazione
Interazione.drawio
### Diagramma di sequenza:

## Architettura Logica: Comportamento

### Diagramma di stato: AnalizzaUtente

Comportamento.drawio

## Piano di lavoro

|Package|Progetto|Sviluppo|
|:--|:--|:--|
|Dominio | Guerra,Palaferri,Romanini | Guerra,Palaferri,Romanini|
|Log | Guerra,Palaferri,Romanini|Guerra,Palaferri,Romanini|
|RicercaFarmaci | Guerra,Palaferri,Romanini| Guerra,Palaferri,Romanini|
|GestionePrenotazioni |Guerra,Palaferri,Romanini|Guerra,Palaferri,Romanini|
|GestioneAccesso |Guerra,Palaferri,Romanini|Guerra,Palaferri,Romanini|
|GestioneFarmacia |Guerra,Palaferri,Romanini|Guerra,Palaferri,Romanini|
|InterfacciaUtente |Guerra,Palaferri,Romanini|Guerra,Palaferri,Romanini|
|InterfacciaGestioneAccsso |Guerra,Palaferri,Romanini|Guerra,Palaferri,Romanini|
|InterfacciaFarmacia |Guerra,Palaferri,Romanini|Guerra,Palaferri,Romanini|

I tempi di rilascio sono i seguenti:
- Progettazione entro 14 giorni dalla data di odierna
- Sviluppo dei vai moduli con annessi test unitari entro due settimane dalla fine della fase di progettazione
- Integrazione e testing del sistema entro due settimane dalla fine dello sviluppo

Sviluppi futuri:
Il cliente ha richiesto la creazione di un applicativo mobile, per sistemi android e iOS, con l'obbiettivo di rendere il più pratico possibile l'utilizzo del programma. 

## Piano di collaudo


# Analisi del Problema
## Analisi Documento dei Requisiti: Analisi delle Funzionalità

### Tabella Funzionalità

|Funzionalità|Tipo|Grado Complessità|Requisiti Collegati|
|:-:|:-:|:-:|:-:|
|GestioneFarmacia|Memorizzazione dati e gestione dati|complessa|R5F, R10F, R11F, R12F, R13F, R14F |
|Registrazione|Interazione esterno e memorizzazione dati|semplice|R4F|
|RicercaFarmaci|Interazione esterno e lettura dati|semplice|R1F, R2F, R3F|
|Login|Interazione esterno e lettura dati|semplice|R9F|
|GestionePrenotazioni|Interazione esterno e memorizzazione dati|comp|R6F, R7F, R8F, R9F|
|ScritturaLog|Memorizzazione dati|semplice| R15F|

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

<!-- 
### RegistraFarmacie: Tabella Informazioni/Flusso

|Informazione|Tipo|Livello protezione/privacy|Input/Output|Vincoli|
|:-:|:-:|:-:|:-:|:-:|
|Id Farmacia|Semplice|Protezione media|Input|Non più di 40 caratteri|

<br>

### RegistraFarmacisti: Tabella Informazioni/Flusso

|Informazione|Tipo|Livello protezione/privacy|Input/Output|Vincoli|
|:-:|:-:|:-:|:-:|:-:|
|Nome Farmacista|Semplice|Protezione alta|Input|Non più di 40 caratteri|
|Cognome Farmacista|Semplice|Protezione alta|Input|Non più di 40 caratteri|
|Id Farmacia|Semplice|Protezione media|Input|Non più di 40 caratteri|
|Username Farmacista|Semplice|Protezione molto alta|Input|Non più di 40 caratteri|
|Password Farmacista|Semplice|Protezione molto alta|Input|

<br>
-->

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
|Username|semplice|Protezione molto alta|Input|Non più di 50 caratteri|
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
|View LoginFarmacista|Username, Password|Login|
|View Prenotazioni|Lista Prenotazioni|GestioneFarmacia|
|View ResocontoUtenti|Nome Cliente, Cognome Cliente, Codice Fiscale Cliente, Stato Cliente|GestioneFarmacia|
|View VerificaIdentità|Nome Cliente, Cognome Cliente, Codice Fiscale Cliente |VerificaIdentità|
|View Farmaci|Lista Farmaci|GestioneFarmacia|
|Home Servizio|Messaggio di benvenuto, Nome farmaco, Località utente, Lista farmacie pertinenti|RicercaFarmaci|
|View Registrazione|Pagina di registrazione di un nuovo utente|Registrazione|
|View NuovaPrenotazione|Data invio, Ora invio, Data prenotazione, Elenco farmaci, Identificativo farmacia<!--, Identificativo cliente-->|NuovaPrenotazione|
|View PrenotazioniPersonali|Lista prenotazioni|ListaPrenotazioni|
|View LoginUtente|Username, Password|Login|

<!-- |Home Utente||| -->

<br>

## Tabella Sistemi Esterni

|Sistema|Descrizione|Protocollo di Interazione|Livello di Sicurezza|
|:-:|:-:|:-:|:-:|
|Gestione Magazzino|Sistema che si occupa della gestione dei farmaci in magazzino|GestioneMagazzino mette a disposizione delle funzionalità di elencazione dei farmaci. L'elenco restituito varierà in base ai parametri passati |Medio livello di sicurezza perchè protegge i dati della farmacia |

<br>

## Analisi Ruoli e Responsabilità
### Tabella Ruoli

|Ruolo|Responsabilità|Maschere|Riservatezza|Numerosità|
|:-:|:-:|:-:|:-:|:-:|
|Farmacista|Gestione di tutte le informazioni relative agli utenti e alle prenotazioni di una farmacia|||Massimo 10 farmacisti per ogni farmacia|
|Cliente|Ricerca di un farmaco senza necessità di login|Home Servizio, View Login, View Registrazione |E' richiesto un medio grado di riservatezza|Illimitati|
|ClienteRegistrato|Ricerca e prenotazione di farmaci presso una farmacia|||Illimitati|
|GestoreSicurezza|Visualizzazione di log relativi alle operazioni della propria farmacia|View Login, Home Log, View Log, view Anomalie|E' richiesto un medio grado di riservatezza|2-3 persone considerando l'alternanza dei giorni di lavoro|
|Amministratore di sistema|Manutenzione del sistema e gestione delle utenze di farmacie e farmacisti|||1-2|

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

### GestoreSicurezza: Tabella Ruolo-Informazioni

|Informazione|Tipo di Accesso|
|:-:|:-:|
|Data|Lettura|
|Ora|Lettura|
|Attore|Lettura|
|Identificativo Farmacia|Lettura|
|Operazione Eseguita|Lettura|
|Messaggio|Lettura|
|Username|Scrittura|
|Password|Scrittura|

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

###  Tabella sotto funzionalità 
|Sotto-funzionalità|Sotto-funzionalità|Legame|Informazioni|
|:-|:-|:-|:-|
|||

<br>

## Creazione Modello del Dominio

Il seguente diagramma delle classi rappresenta la parte di modello del dominio relativa al sistema.

Modellodominio.drawio

Il seguente diagramma delle classi rappresenta la parte di modello del dominio relativo alla gestione dei Log.

Logs.drawio

## Architettura Logica: Struttura

### Diagramma dei package


# Analisi del Problema
## Analisi Documento dei Requisiti: Analisi delle Funzionalità

### Tabella Funzionalità

|Funzionalità|Tipo|Grado Complessità|Requisiti Collegati|
|:-:|:-:|:-:|:-:|
|GestioneFarmacia|Memorizzazione dati e gestione dati|Complessa|R5F, R10F, R11F, R12F, R13F, R14F |
|Registrazione|Interazione esterno e memorizzazione dati|Semplice|R4F|
|RicercaFarmaci|Interazione esterno e lettura dati|Semplice|R1F, R2F, R3F|
|Login|Interazione esterno e lettura dati|Semplice|R9F|
|NuovaPrenotazione|Interazione esterno e memorizzazione dati|Semplice|R6F, R7F, R8F|
|ScritturaLog|Memorizzazione dati|Semplice| R15F|
|AnalisiLog|Gestione dati|Semplice| R15F|

<br>

### GestioneFarmacia: Tabella Informazione/Flusso

|Informazione|Tipo|Livello protezione/privacy|Input/Output|Vincoli|
|:-:|:-:|:-:|:-:|:-:|
|Nome Cliente|Semplice|Protezione alta|Input|Non più di 40 caratteri|
|Cognome Cliente|Semplice|Protezione alta|Input|Non più di 40 caratteri|
|Codice Fiscale Cliente|Semplice|Protezione media|Input|Deve essere di 16 caratteri|
|Lista Farmaci|Composto|Protezione alta|Output||
|Lista Prenotazioni|Composto|Protezione molto alta|Output||


<br>

### RicercaFarmaci: Tabella Informazione/Flusso

|Informazione|Tipo|Livello protezione/privacy|Input/Output|Vincoli|
|:-:|:-:|:-:|:-:|:-:|
|Nome Farmaco|Semplice|Protezione bassa|Input||
|Località Utente|Composto|Protezione alta|Input||
|Lista farmacie pertinenti|Composto|Protezione bassa|Output|Non più di 10 farmacie| 

<!-- 
Località Utente = {Latitudine, Longitudine};

Lista farmacie pertinenti = {NomeFarmacia1, IndirizzoFarmacia1, DistanzaFarmacia1, ... , NomeFarmaciaN, IndirizzoFarmaciaN, DistanzaFarmaciaN} 
-->

<br>

### Registrazione: Tabella Informazione/Flusso

|Informazione|Tipo|Livello protezione/privacy|Input/Output|Vincoli|
|:-:|:-:|:-:|:-:|:-:|
|Nome Cliente|Semplice|Protezione media|Input|Non più di 40 caratteri|
|Cognome Cliente|Semplice|Protezione media|Input|Non più di 40 caratteri|
|Data di Nascita|Semplice|Protezione media|Input|Deve avere più di 16 anni e data di nascita successiva al 1900|
|Codice Fiscale|Semplice|Protezione media|Input|Deve essere di 16 caratteri|
|Email| Semplice|Protezione alta|Input|Deve essere di 256 caratteri e del formato giusto|
|Password|Semplice|Protezione molto alta|Input|Deve essere almeno di 8 caratteri, di cui uno alfabetico e uno numerico|

<br>

### ScritturaLog: Tabella Informazione/Flusso

|Informazione|Tipo|Livello protezione/privacy|Input/Output|Vincoli|
|:-:|:-:|:-:|:-:|:-:|
|Data |Semplice|Protezione media|Input|Non più di 40 caratteri|
|Ora|Semplice|Protezione media|Input|Non più di 40 caratteri|
|Attore|Semplice|Protezione alta|Input||
|Operazione Eseguita|Composto|Protezione alta|Input||
|Messaggio|Composto|Protezione molto alta|Input||

<br>

### AnalisiLog: Tabella Informazione/Flusso

|Informazione|Tipo|Livello protezione/privacy|Input/Output|Vincoli|
|:-:|:-:|:-:|:-:|:-:|
|Notifica|Composto|Protezione bassa|Output||


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

|Requisito|Informazioni|Funzionalità|
|:-|:-|:-|
||||
||||
||||
||||

<br>

## Tabella Sistemi Esterni

|Sistema|Descrizione|Protocollo di Interazione|Livello di Sicurezza|
|:-|:-|:-|:-|
|||||

<br>

## Analisi Ruoli e Responsabilità
### Tabella Ruoli

|Ruolo|Responsabilità|Maschere|Riservatezza|Numerosità|
|:-|:-|:-|:-|:-|
|Farmacista|||||
|Cliente|||||
|GestoreSicurezza|||||
||||||

<br>

### Farmacista: Tabella Ruolo-Informazioni

|Informazione|Tipo di Accesso|
|:-|:-|
|||
|||
|||

<br>

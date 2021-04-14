# Analisi del Problema
## Analisi Documento dei Requisiti: Analisi delle Funzionalità

### Tabella Funzionalità

|||||
|:---|:---|:---|:---|
|**Funzionalità**|**Tipo**|**Grado Complessità**|**Requisiti Collegati**|
|GestioneFarmacia|Memorizzazione dati e gestione dati|Complessa|R5F, R10F, R11F, R12F, R13F, R14F |
|Registrazione|Interazione esterno e memorizzazione dati|Semplice|R4F|
|RicercaFarmaci|Interazione esterno e lettura dati|Semplice|R1F, R2F, R3F|
|Login|Interazione esterno e lettura dati|Semplice|R9F|
|NuovaPrenotazione|Interazione esterno e memorizzazione dati|Semplice|R6F, R7F, R8F|
|ScritturaLog|Memorizzazione dati|Semplice| R15F|
|AnalisiLog|Gestione dati|Semplice| R15F|

### GestioneFarmacia: Tabella Informazione/Flusso

||||||
|:---|:---|:---|:---| :---|
|**Informazione**|**Tipo**|**Livello protezione/privacy**|**Input/Output**|**Vincoli**|
|Nome Utente|||||
|Cognome Utente|||||

### Registrazione: Tabella Informazione/Flusso

||||||
|:---|:---|:---|:---| :---|
|**Informazione**|**Tipo**|**Livello protezione/privacy**|**Input/Output**|**Vincoli**|
|Nome Cliente|Semplice|Protezione media|Input|Non più di 40 caratteri|
|Cognome Cliente|Semplice|Protezione media|Input|Non più di 40 caratteri|
|Data di Nascita|Semplice|Protezione media|Input|Deve avere più di 16 anni e data di nascita successiva al 1900|
|Codice Fiscale|Semplice|Protezione media|Input|Deve essere di 16 caratteri|
|Email| Semplice|Protezione alta|Input|Deve essere di 256 caratteri e del formato giusto|
|Password|Semplice|Protezione molto alta|Input|Deve essere almeno di 8 caratteri, di cui uno alfabetico e uno numerico|

## Analisi Documento dei Requisiti: Analisi dei Vincoli
### Tabella Vincoli


|||||
|:---|:---|:---|:---|
|**Requisito**|**Categorie**|**Impatto**|**Funzionalità**|
|Semplicità dell'interfaccia|Usabilità|Intuitività di utilizzo| GestioneFarmacia, Registrazione, RicercaFarmaci, Login, NuovaPrenotazione |
|Velocità della ricerca dei dati|Tempo di Risposta|Maggiore reattività|GestioneFarmacia, Registrazione, RicercaFarmaci, Login, NuovaPrenotazione|
|Velocità di memorizzazione dei dati|Tempo di Risposta|Maggiore reattività|GestioneFarmacia, Registrazione, Login, NuovaPrenotazione|
|Controllo Accessi| Sicurezza | Peggiorano tempo di risposta e usabilità, migliorano la privacy dei dati | GestioneFarmacia, NuovaPrenotazione |
|Protezione dei Dati| Sicurezza | Peggiorano tempo di risposta, migliorano la privacy dei dati | GestioneFarmacia, Registrazione, RicercaFarmaci, Login, NuovaPrenotazione |

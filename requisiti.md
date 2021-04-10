# Documento dei Requisiti

## Raccolta dei requisiti

- I clienti delle farmacie hanno a disposizione due servizi: controllare se un farmaco è disponibile vicino alla loro posizione e/o prenotarlo.
- Il cliente fornisce la sua posizione che l'applicativo userà per indicargli le farmacie più vicine. Contemporaneamente specificherà il farmaco da cercare e l'applicativo fornirà le 10 farmacie più vicine ad averlo in magazzino indicandone se è disponibile o sta per terminare.
- Per la prenotazione è necessario possedere un account
- La prenotazione sarà composta da uno o più farmaci, dalla farmacia, e dal giorno. 
- Se il farmaco necessita di ricetta, il cliente può decidere se inserirla in fase di prenotazione (sotto forma di foto o codice univoco) oppure presentarla fisicamente.
- L'account viene creato in due fasi:
    1. Registrazione con username, password e codice fiscale
    2. Autenticazione di persona in farmacia
- L'username deve essere univoco, la password di almeno 8 caratteri.
- Per l'autenticazione è necessario mostrare il tesserino sanitario per l'identificazione in farmacia.
- Il farmacista vede le prenotazioni, i farmaci disponibili in negozio e viene segnalato riguardo ai farmaci in esaurimento
- Se alla fine della giornata un utente non si presenta allora l'evento viene registrato, per poi avvisare il farmacista e eventualmente bloccare l'utente per 1 mese.
- Il sistema sarà ovviamente distribuito e di natura client-server con la presenza di un database centrale dove memorizzare i dati
- la gestione delle vendite e ordini è gestita da un altro software
---
## Analisi dei Requisiti

ID | Requisiti | Tipo
--- | --- | ---
R1F | Localizzazione delle farmacie più vicine in base al farmaco da cercare | Funzionale
R2F | Specifica del farmaco da cercare da parte dell'utente | Funzionale
R3F | Presentazione delle farmacie che dispongono di un farmaco | Funzionale
R4F | Registrazione di un account tramite l'interfaccia web | Funzionale
R5F | Attivazione dell'account con identificazione fisica dell'utente con documento | Funzionale
R6F | Per prenotare l'utente deve essere registrato | Funzionale
R7F | La prenotazione sarà composta da uno o più farmaci, dalla farmacia e dal giorno | Funzionale
R8F | Le prenotazioni farmaci con ricetta prevedono il caricamento opzionale della foto o del codice | Funzionale
R9F | Identificazione attraverso username univoco e password di almeno 8 caratteri | Funzionale
R10F | Visualizzazione delle prenotazioni | Funzionale
R11F | Visualizzazione del numero dei farmaci disponibili | Funzionale
R12F | Notifica dei farmaci in esaurimento o in scadenza | Funzionale
R13F | Notifica della mancata finzalizzazione in acquisto di una prenotazione | Funzionale
R14F | Blocco dell'utente che effettua troppe prenotazioni senza presentarsi | Funzionale
R15F | Verrà memorizzato il numero di prenotazioni andate a buon fine | Funzionale
R1NF | Velocità di memorizzazione dei dati | Non Funzionale
R2NF | Velocità della ricerca dei dati | Non Funzionale
R3NF | Semplicità dell'interfaccia | Non Funzionale
R4NF | Un utente non può avere più di un account verificato | Non Funzionale
R5NF | L'utente non deve poter fare eccessive prenotazioni | Non Funzionale
R6NF | la gestione delle vendite e ordini è gestita da un altro software | Non Funzionale

## Vocabolario

*da fare dopo aver fatto gli schemi*
Voce | Definizione | Sinonimi
--- | --- | ---
Cliente | Persona che usufruisce del servizio lato cliente | Utente
ClienteRegistrato | Cliente che possiede un account identificato con cui può effettuare prenotazioni | UtenteRegistrato
Farmacia | Farmacia che aderisce al servizio | Punto vendita
Farmaco | Medicinale che viene venduto in farmacia |
Farmacista | Utente che accede con le credenziali della farmacia | Operatore
Prenotazione | Richiesta di farmaci da comprare in negozio  |
Data e ora prenotazione | Indicazione temporale del momento in cui avverrà la prenotazione | 
Codice Ricetta | Codice associato alla ricetta elettronica, necessario comprare certi farmaci | 
Posizione | Luogo della ricerca o collocamento geografico della farmacia |
Credenziali | Insieme composto da username e password necessari per acccedere al sistema | 
Username | È una parola formata dalla concatenazione di nome e cognome dell’Utente o del nome della farmacia | 
Password | Codice alfanumerico di almeno 8 caratteri | 
Magazzino | Luogo fisico in cui vengono conservati i farmaci di un punto vendita | Deposito

---

## Scenari

| | |
| :------------- | :----------: 
| **Titolo** | Registrazione  |
| **Descrizione** | Registrazione dell'utenza di un cliente | 
| **Attori** | Cliente | 
| **Relazioni** | VerificaIdentità, RicercaFarmaci |
| **Precondizioni** | Il cliente non è già registrato | 
| **Postcondizioni** | La registrazione è avvenuta con successo, ora è necessario verificare la propria identità in farmacia per attivare l'account | 
| **Scenario principale** | 1. Il cliente accede alla sezione di registrazione <br/> 2. Il cliente inserisce i propri dati: nome, cognome, numero di telefono e gli estremi del documento di identificazione utilizzato <br> 3. Il cliente termina la registrazione, se avvenuta con successo gli viene mostrata la conferma e viene reindirizzato alla pagina principale |
| **Scenari alternativi** |  | 
| **Requisiti non funzionali** | Velocità di memorizzazione e semplicità di navigazione tra le diverse maschere. Inoltre un utente non può avere più di un account verificato |
| **Punti aperti** |  | 

| | |
| :------------- | :----------: 
| **Titolo** | VerificaIdentità |
| **Descrizione** | Verifica dell'identità dell'utente registrato | 
| **Attori** | Cliente, Farmacista | 
| **Relazioni** | Registrazione, GestioneFarmacia |
| **Precondizioni** | Il cliente è registrato | 
| **Postcondizioni** | L'utente è stato verificato e il suo account viene abilitato per effettuare delle prenotazioni |
| **Scenario principale** | 1. Il cliente va in farmacia con il documento specificato in fase di registrazione <br/> 2. Il cliente viene identificato dal farmacista <br/> 3. Il farmacista attiva l'account dell'utente dopo aver verificato il documento |
| **Scenari alternativi** |  | 
| **Requisiti non funzionali** | Velocità di memorizzazione e semplicità di navigazione tra le diverse maschere |
| **Punti aperti** |  | 

| | |
| :------------- | :----------: 
| **Titolo** | SospensioneUtenza |
| **Descrizione** | Se un utente non ha concluso troppe prenotazioni allora viene proposta la sospensione dell'utente al farmacista |
| **Attori** | Farmacista | 
| **Relazioni** | ResocontoPrenotazioni, GestioneFarmacia |
| **Precondizioni** | Il cliente non ha concluso troppe prenotazioni | 
| **Postcondizioni** | Il cliente non può più effettuare prenotazioni per 30 giorni |
| **Scenario principale** | 1. Si veritifa l'evento FineGiornata <br/> 2. Il Sistema recupera l'elenco delle prenotazioni e lo analizza <br/> 3. Se il Sistema rileva un numero eccessivo di prenotazioni non concluse per un determinato utente, allora lo segnala alla farmacista <br/> 4. La farmacista, se ritiene necessario, può confermare la sospensione dell'utente
| **Scenari alternativi** |  | 
| **Requisiti non funzionali** | Velocità nella ricerca dei dati e semplicità dell'interfaccia |
| **Punti aperti** |  | 
<br>

| | |
| :------------- | :----------: 
| **Titolo** | Resoconto  |
| **Descrizione** | Viene generato il resoconto delle operazioni svolte svolte in giornata | 
| **Attori** | FineGiornata | 
| **Relazioni** | ResocontoPrenotazioni, ResocontoFarmaci | 
| **Precondizioni** |  | 
| **Postcondizioni** |  | 
| **Scenario principale** | 1. Si verifica l'evento FineGiornata <br> 2. Il Sistema, per ogni Farmacia, recupera l'elenco dei farmaci presenti e delle prenotazioni <br> 3. Per ogni Farmacia il Sistema calcola i farmaci in esaurimento e le eventuali prenotazioni non portate a termine <br> 4. Il Sistema genera un report da inviare a ciascuna Farmacia | 
| **Scenari alternativi** |  | 
| **Requisiti non funzionali** | Protezione dei dati, non deve succedere che siano inviati per errore resoconti di una Farmacia ad un'altra Farmacia |
| **Punti aperti** |  | 
<br>

| | |
| :------------- | :----------: 
| **Titolo** | ResocontoPrenotazioni  |
| **Descrizione** | Si controllano le prenotazioni non terminate per utente | 
| **Attori** | Farmacista, FineGiornata | 
| **Relazioni** | Resoconto, SospensioneUtenza | 
| **Precondizioni** |  | 
| **Postcondizioni** | Viene mostrato l'elenco delle prenotazioni | 
| **Scenario principale** | 1. Il Farmacista va nella schermata di visualizzazione farmaci <br> 2. Il sistema recupera l'elenco delle prenotazioni giornaliere <br> 3. Il sistema mostra a video l'elenco delle prenotazioni | 
| **Scenari Alternativi** |  | 
| **Requisiti non funzionali** | Velocità di ricerca dei dati e semplicità di navigazione tra le diverse maschere |
| **Punti aperti** |  | 
<br>

| | |
| :------------- | :----------: 
| **Titolo** | ResocontoFarmaci  |
| **Descrizione** | Si visualizzano i farmaci in esaurimento | 
| **Attori** | Farmacista,FineGiornata | 
| **Relazioni** | Resoconto, GestioneFarmacia | 
| **Precondizioni** |  | 
| **Postcondizioni** | Si visualizzano l'elenco dei farmaci | 
| **Scenario principale** | 1. Il Farmacista va nella schermata di visualizzazione farmaci <br> 2. il sistema recupera l'elenco dei farmaci in scadenza <br> 3. Il sistema mostra a video l'elenco dei farmaci | 
| **Scenari Alternativi** |  | 
| **Requisiti non funzionali** | Velocità di ricerca dei dati e semplicità di navigazione tra le diverse maschere |
| **Punti aperti** |  | 

---

## Analisi del Rischio

### Tabella Valutazione dei Beni

Bene | Valore | Esposizione
--- | --- | ---
Sistema Informativo | Alto. Fondamentale per il funzionamento del servizio | Alta. Perdita finanziaria e di immagine
Informazioni dei clienti | Medio. Dati generali dei clienti della farmacia, comprese le credenziali | Alta. Perdita di immagine dovuta alla divulgazione di dati sensibili
Informazioni relative al personale | Alto. Dati relativi ai farmacisti, incluse le credenziali di accesso all'area riservata | Molto Alta. Perdita finanziaria dovuta a usi impropri delle credenziali con privilegi elevati. Perdita di immagine possibile con la divulgazione dei dati relativi ai clienti
Dati delle prenotazioni | Alto. Necessario per tenere traccia delle prenotazioni | Molto Alta. Perdita finanziaria dovuta allo smarrimento di prenotazioni. Perdita di immagine con la divulgazione dei farmaci prenotati dai clienti


### Tabella Minacce/Controlli

Minaccia | Probabilità | Controllo | Fattibilità
--- | --- | --- | ---
Furto credenziali Farmacista | Alta | Controllo sulla sicurezza della password - Log delle operazioni | Costo implementativo molto basso
Furto credenziali Cliente | Alta | Controllo sulla sicurezza della password - Log delle operazioni | Costo implementativo molto basso
Alterazione o intercettazione delle comunicazioni | Alta | Utilizzo di un canale sicuro <!-- (TLS) --> - Log delle operazioni | Basso costo di realizzazione con determinati protocolli
Accesso non autorizzato al database | Bassa | Accesso da macchine sicure - Log di tutte le operazioni | Basso costo di realizzazione, il server deve essere ben custodito
DoS | Bassa | Controllo e limitazione delle richieste | Media complessità di implementazione

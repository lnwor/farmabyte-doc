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
| **Titolo** | GestioneCliente  |
| **Descrizione** | Gestione dell'utenza di un cliente registrato | 
| **Attori** | Farmacista | 
| **Relazioni** | Login, SospensioneUtenza, VerificaIdentità | 
| **Precondizioni** |  | 
| **Postcondizioni** |  | 
| **Scenario principale** | 1. Login <br> 2. Il farmacista può eseguire la verifica, la sospensione di un'account oppure controllare il resoconto giornaliero | 
| **Scenari Alternativi** |  | 
| **Requisiti non funzionali** |  | 
| **Punti aperti** |  | 
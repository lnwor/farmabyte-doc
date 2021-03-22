# Documento dei Requisiti

## Raccolta dei requisiti

- I clienti delle farmacie hanno a disposizione due servizi: controllare se un farmaco è disponibile vicino alla loro posizione e/o prenotarlo.
- Il cliente fornisce la sua posizione che l'applicativo userà per indicargli le farmacie più vicine. Contemporaneamente specificherà il farmaco da cercare e l'applicativo fornirà le 10 farmacie più vicine ad averlo in magazzino indicandone se è disponibile o sta per terminare.
- Per la prenotazione è necessario possedere un account
- L'account viene creato in due fasi:
    1. Registrazione con username e password
    2. Autenticazione di persona in farmacia

- L'username deve essere univoco, la password di almeno 8 caratteri.
- Per l'autenticazione è necessario mostrare un documento per l'identificazione in farmacia, predentemente inserito durante la fase di registrazione
- Il farmacista vede le prenotazioni, i farmaci disponibili in negozio e viene segnalato riguardo ai farmaci in esaurimento
- Se alla fine della giornata un utente non si presenta allora l'evento viene registrato, per poi avvisare il farmacista e eventualmente bloccare l'utente per 1 mese.
- Il sistema sarà ovviamente distribuito e di natura client-server con la presenza di database dove memorizzare i dati

## Analisi dei Requisiti

ID | Requisiti | Tipo
--- | --- | ---
R1F | Localizzazione delle farmacie più vicine in base al farmaco da cercare | Funzionale
R2F | Specifica del farmaco da cercare da parte dell'utente | Funzionale
R3F | Presentazione delle farmacie che dispongono di un farmaco | Funzionale
R4F | Registrazione di un account tramite l'interfaccia web | Funzionale
R5F | Attivazione dell'account con identificazione fisica dell'utente con documento | Funzionale
R6F | Per prenotare l'utente deve essere registrato | Funzionale
R7F | Identificazione attraverso username univoco e password di almeno 8 caratteri | Funzionale
R8F | Visualizzazione delle prenotazioni | Funzionale
R9F | Visualizzazione del numero dei farmaci disponibili | Funzionale
R10F | Notifica dei farmaci in esaurimento o in scadenza | Funzionale
R11F | Notifica della mancata finzalizzazione in acquisto di una prenotazione | Funzionale
R12F | Blocco dell'utente che effettua troppe prenotazioni senza presentarsi | Funzionale
R13F | Verrà memorizzato il numero di prenotazioni andate a buon fine | Funzionale
R1NF | Velocità di memorizzazione dei dati | Non Funzionale
R2NF | Velocità della ricerca dei dati | Non Funzionale
R3NF | Semplicità dell'interfaccia | Non Funzionale
R4NF | Un utente non può avere più di un account verificato | Non Funzionale
R5NF | L'utente non deve poter fare eccessive prenotazioni | Non Funzionale
R6NF | _In attesa del ricevimento del prof_ | Non Funzionale

## Vocabolario

*da fare dopo aver fatto gli schemi*
Voce | Definizione | Sinonimi
--- | --- | ---
Clienti non registrati | Utenti che usufruiscono del servizio di localizzazione ma non di  quello di prenotazione | Utenti
ClientiRegistrati | Utenti che possiedono un account identificato che possono effettuare prenotazioni | UtentiRegistrati

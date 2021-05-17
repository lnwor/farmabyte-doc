# Documento dei Requisiti

<br>

## Raccolta dei requisiti

<br>

- I clienti delle farmacie hanno a disposizione due servizi: controllare se un farmaco è disponibile vicino alla loro posizione e/o prenotarlo.
- Il cliente fornisce la sua posizione che l'applicativo userà per indicargli le farmacie più vicine. Contemporaneamente specificherà il farmaco da cercare e l'applicativo fornirà le 10 farmacie più vicine ad averlo in magazzino indicandone se è disponibile o sta per terminare.
- Per la prenotazione è necessario possedere un account
- La prenotazione sarà composta da uno o più farmaci, dalla farmacia, e dal giorno. 
- Se il farmaco necessita di ricetta, il cliente può decidere se inserirla in fase di prenotazione (sotto forma di foto o codice univoco) oppure presentarla fisicamente.
- L'account viene creato in due fasi:
    1. Registrazione con username, password e codice fiscale
    2. Autenticazione di persona in farmacia
- L'username deve essere univoco, la password di almeno 8 caratteri, contentente almeno un numero e un carattere alfabetico.
- Per l'autenticazione è necessario mostrare il tesserino sanitario per l'identificazione in farmacia.
- Il farmacista vede le prenotazioni, i farmaci disponibili in negozio e viene segnalato riguardo ai farmaci in esaurimento
- Se alla fine della giornata un utente non si presenta allora l'evento viene registrato, per poi avvisare il farmacista e eventualmente bloccare l'utente per 1 mese.
- Il sistema sarà ovviamente distribuito e di natura client-server con la presenza di un database centrale dove memorizzare i dati
- La gestione delle vendite, degli ordini e modifiche di magazzino è gestita da un altro software
- Non va considerata la gestione dei dati del personale 

<br>

---

## Analisi dei Requisiti


<br>

ID | Requisiti | Tipo
--- | --- | ---
R1F | Localizzazione delle farmacie più vicine in base al farmaco da cercare | Funzionale
R2F | Specifica del farmaco da cercare da parte dell'utente | Funzionale
R3F | Presentazione delle farmacie che dispongono di un farmaco | Funzionale
R4F | Registrazione di un account tramite l'interfaccia web | Funzionale
R5F | Attivazione dell'account con identificazione fisica dell'utente con documento | Funzionale
R6F | La prenotazione sarà composta da uno o più farmaci, dalla farmacia e dal giorno | Funzionale
R7F | Le prenotazioni farmaci con ricetta prevedono il caricamento opzionale della foto o del codice | Funzionale
R8F | Identificazione attraverso username univoco e password di almeno 8 caratteri, contentente almeno un carattere alfabetico e un carattere numerico | Funzionale
R9F | Visualizzazione delle prenotazioni | Funzionale
R10F | Visualizzazione del numero dei farmaci disponibili | Funzionale
R11F | Notifica dei farmaci in esaurimento o in scadenza | Funzionale
R12F | Notifica della mancata finzalizzazione in acquisto di una prenotazione | Funzionale
R13F | Blocco dell'utente che effettua troppe prenotazioni senza presentarsi | Funzionale
R14F | Verrà memorizzato il numero di prenotazioni andate a buon fine | Funzionale
R1NF | Velocità di memorizzazione dei dati | Non Funzionale
R2NF | Velocità della ricerca dei dati | Non Funzionale
R3NF | Semplicità dell'interfaccia | Non Funzionale
R4NF | Un utente non può avere più di un account verificato | Non Funzionale
R5NF | L'utente non deve poter fare eccessive prenotazioni | Non Funzionale
R6NF | la gestione delle vendite e ordini è gestita da un altro software | Non Funzionale
R7NF | Per prenotare l'utente deve essere registrato | Non Funzionale
R8NF | La gestione delle vendite, degli ordini e modifiche di magazzino è gestita da un altro software | Non Funzionale
R9NF | Non va considerata la gestione dei dati del personale | Non Funzionale 

<br>

## Vocabolario

<br>

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

<br>

---

## Scenari

| | |
| :- | :- |
| **Titolo** | GestioneFarmacia  |
| **Descrizione** | Gestione dell'utenza di un cliente registrato |
| **Attori** | Farmacista | 
| **Relazioni** | Login, SospensioneUtenza, VerificaIdentità, ResocontoFarmaci, ResocontoPrenotazioni | 
| **Precondizioni** |  | 
| **Postcondizioni** |  | 
| **Scenario Principale** | 1. Login <br> 2. Il farmacista può eseguire la verifica, sospendere un'account, controllare le prenotazioni e i farmaci in magazzino | 
| **Scenari Alternativi** |  | 
| **Requisiti non funzionali** | Velocità di ricerca dei dati e semplicità di navigazione tra le diverse maschere |
| **Punti aperti** |  |

<br>

| | |
| :- | :- |
| **Titolo** | ResocontoUtenti  |
| **Descrizione** | Si controllano gli utenti con potenzialmente sospendibili | 
| **Attori** | Farmacista, FineGiornata | 
| **Relazioni** | SospensioneUtenza, GestioneFarmacia | 
| **Precondizioni** |  | 
| **Postcondizioni** | Viene mostrato l'elenco degli Utenti a rischio sospensione | 
| **Scenario Principale** | 1. Il Farmacista va nella schermata di visualizzazione utenti <br> 2. Il sistema recupera l'elenco degli utenti a rischio <br> 3. Il sistema mostra a video l'elenco degli utenti | 
| **Scenari Alternativi** |  | 
| **Requisiti non funzionali** | Velocità di ricerca dei dati e semplicità di navigazione tra le diverse maschere |
| **Punti aperti** |  | 

<br>

| | |
| :- | :- |
| **Titolo** | ResocontoFarmaci |
| **Descrizione** | Viene mostrato l'elenco dei farmaci in scadenza o in esaurimento |
| **Attori** | Farmacista | 
| **Relazioni** | GestioneFarmacia | 
| **Precondizioni** |  | 
| **Postcondizioni** | Viene mostrato l'elenco degli Utenti a rischio sospensione | 
| **Scenario Principale** | 1. Il Farmacista va nella schermata di visualizzazione farmaci <br> 2. Il sistema recupera l'elenco dei farmaci in esaurimento o in scadenza <br> 3. Il sistema mostra a video l'elenco richiesto | 
| **Scenari Alternativi** |  | 
| **Requisiti non funzionali** | Velocità di ricerca dei dati e semplicità di navigazione tra le diverse maschere |
| **Punti aperti** |  | 

<br>

| | |
| :- | :- |
| **Titolo** | ControlloPrenotazioni  |
| **Descrizione** | Si controllano le prenotazioni non terminate | 
| **Attori** | Farmacista | 
| **Relazioni** | ConfermaPrenotazione,GestioneFarmacia | 
| **Precondizioni** | | 
| **Postcondizioni** | Viene mostrato l'elenco delle prenotazioni | 
| **Scenario principale** | 1. Il Farmacista va nella schermata di visualizzazione prenotazioni <br> 2. Il sistema recupera l'elenco delle prenotazioni giornaliere <br> 3. Il sistema mostra a video l'elenco delle prenotazioni | 
| **Scenari Alternativi** | | 
| **Requisiti non funzionali** | Velocità di ricerca dei dati |
| **Punti aperti** | | 

<br>

| | |
| :- | :- |
| **Titolo** | ConfermaPrenotazione |
| **Descrizione** | Il Farmacista conferma la prenotazione avvenuta | 
| **Attori** | Farmacista | 
| **Relazioni** | ControlloPrenotazioni | 
| **Precondizioni** | | 
| **Postcondizioni** | La prenotazione viene confermata | 
| **Scenario principale** | 1. ControlloPrenotazioni <br> 2. Il Farmacista conferma l'avvenuta prenotazione | 
| **Scenari Alternativi** | | 
| **Requisiti non funzionali** | Semplicità dell'interfaccia |
| **Punti aperti** | | 

<br>

| | |
| :- | :- |
| **Titolo** | Registrazione |
| **Descrizione** | Il cliente si registra al servizio | 
| **Attori** | Cliente | 
| **Relazioni** | | 
| **Precondizioni** | Il cliente dispone di un codice fiscale valido | 
| **Postcondizioni** | Il cliente è registrato nel sistema ed è posto in attesa della verifica | 
| **Scenario principale** | 1. Il cliente accede alla sezione di registrazione <br> 2. Il cliente inserisce i propri dati: nome, cognome, numero di telefono e il codice fiscale <br> 3. Il cliente termina la registrazione, se avvenuta con successo gli viene mostrata la conferma e viene reindirizzato alla pagina principale | 
| **Scenari Alternativi** | Scenario a: il codice fiscale è già registrato <br> 3. Il sistema verifica che è già presente un utente con quel codice fiscale, quindi notifica il cliente con un messaggio di errore. | 
| **Requisiti non funzionali** | Semplicità dell'interfaccia |
| **Punti aperti** | |

<br>

| | |
| :- | :- |
| **Titolo** | VerificaIdentità |
| **Descrizione** | Verifica dell'identità dell'utente registrato | 
| **Attori** | Cliente, Farmacista | 
| **Relazioni** | GestioneFarmacia |
| **Precondizioni** | Il cliente è registrato | 
| **Postcondizioni** | L'utente è stato verificato e il suo account viene abilitato per effettuare delle prenotazioni |
| **Scenario principale** | 1. Il cliente va in farmacia con il documento specificato in fase di registrazione <br> 2. Il cliente viene identificato dal farmacista <br> 3. Il farmacista chiede al sistema di recuperare l'utente <br> 4. Il farmacista attiva l'account dell'utente |
| **Scenari alternativi** | 4. Il sistema non trova nessun utente, segnala il farmacista | 
| **Requisiti non funzionali** | Velocità di memorizzazione e semplicità di navigazione tra le diverse maschere |
| **Punti aperti** |  | 

<br>

| | |
| :- | :- | 
| **Titolo** | SospensioneUtenza |
| **Descrizione** | Se un utente non ha concluso troppe prenotazioni allora viene proposta la sospensione dell'utente al farmacista |
| **Attori** | Farmacista | 
| **Relazioni** | ResocontoPrenotazioni, GestioneFarmacia |
| **Precondizioni** | Il cliente è diffidato dal sistema (ha molte prenotazioni non concluse) | 
| **Postcondizioni** | Il cliente non può più effettuare prenotazioni per 30 giorni |
| **Scenario principale** | 1. Si verifica l'evento FineGiornata <br> 2. Il Sistema recupera l'elenco delle prenotazioni e lo analizza <br> 3. Se il Sistema rileva un numero eccessivo di prenotazioni non concluse per un determinato utente, allora lo segnala al farmacista <br> 4. Il farmacista, se ritiene necessario, può confermare la sospensione dell'utente
| **Scenari alternativi** |  | 
| **Requisiti non funzionali** | Velocità nella ricerca dei dati e semplicità dell'interfaccia |
| **Punti aperti** |  | 

<br>

| | |
| :- | :- | 
| **Titolo** | ResocontoPrenotazioni  |
| **Descrizione** | Si controllano le prenotazioni non terminate per utente | 
| **Attori** | Farmacista, FineGiornata | 
| **Relazioni** | Resoconto, SospensioneUtenza, GestioneFarmacia | 
| **Precondizioni** |  | 
| **Postcondizioni** | Viene mostrato l'elenco delle prenotazioni | 
| **Scenario principale** | 1. Il Farmacista va nella schermata di visualizzazione farmaci <br> 2. Il sistema recupera l'elenco delle prenotazioni giornaliere <br> 3. Il sistema mostra a video l'elenco delle prenotazioni | 
| **Scenari Alternativi** |  | 
| **Requisiti non funzionali** | Velocità di ricerca dei dati e semplicità di navigazione tra le diverse maschere |
| **Punti aperti** |  | 

<br>

| | |
| :- | :- |
| **Titolo** | RicercaFarmaci  |
| **Descrizione** | L'utente verifica la disponibilità di un particolare farmaco nelle farmacie più vicine a lui | 
| **Attori** | Cliente | 
| **Relazioni** |  | 
| **Precondizioni** |  | 
| **Postcondizioni** | Si visualizza la lista delle farmacie con disponibilità | 
| **Scenario principale** | 1. Il cliente si reca nella pagina di ricerca <br> 2. Il cliente inserisce il nome del farmaco e la località geografica in cui eseguire la ricerca <br> 3. Il sistema ottiene la lista delle farmacie aventi il farmaco specificato entro un range dalla località specificata. <br> 4. Il sistema ordina la lista in base alla distanza geografica dalla zona dell'utente, in ordine crescente <br> 5. La lista viene mostrata all'utente | 
| **Scenari Alternativi** | Il sistema non riconosce i dati inseriti dall'utente (Nome del farmaco o località) e procede mostrando un messaggio d'errore | 
| **Requisiti non funzionali** | Velocità di ricerca dei dati e semplicità di navigazione tra le diverse maschere |
| **Punti aperti** |  | 

<br>

| | |
| :- | :- |
| **Titolo** | NuovaPrenotazione |
| **Descrizione** | L'utente prenota a suo nome una lista di farmaci | 
| **Attori** | ClienteRegistrato | 
| **Relazioni** | GestionePrenotazioni | 
| **Precondizioni** |  | 
| **Postcondizioni** | Il sistema ha memorizzato i dati della prenotazione, in attesa di conferma da parte della farmacia | 
| **Scenario principale** | 1. Il cliente esegue il **Login** <br> 2. Il cliente seleziona i farmaci che vuole prenotare, la quantità, e inserisce la data di ritiro desiderata <br> 3. Il cliente invia la richiesta di prenotazione <br> 4. Il sistema pone la richiesta in attesa di conferma | 
| **Scenari Alternativi** | Scenario a: La farmacia non dispone dei farmaci richiesti. <br> 4. Il sistema nota che la farmacia non ha disponibilità di almeno uno dei farmaci specificati <br> 5. Viene inviato al cliente un messaggio di errore| 
| **Requisiti non funzionali** | Velocità di verifica dei dati e semplicità di navigazione tra le diverse maschere |
| **Punti aperti** |  | 

<br>

| | |
| :- | :- |
| **Titolo** | ListaPrenotazioni |
| **Descrizione** | L'utente ottiene la lista delle proprie prenotazioni passate ed in corso |
| **Attori** | ClienteRegistrato | 
| **Relazioni** | GestionePrenotazioni | 
| **Precondizioni** | | 
| **Postcondizioni** | Al cliente viene mostrata la lista delle prenotazioni passate ed in corso|
| **Scenario Principale** | 1. Il cliente esegue il Login <br> 2. Il cliente seleziona l'opzione di visualizzazione della lista delle prenotazioni <br> 3. Al cliente viene mostrato l'elenco delle prenotazioni effettuate|
| **Scenari Alternativi** | |
| **Requisiti non funzionali** | Velocità di verifica dei dati e semplicità di navigazione tra le diverse maschere |
| **Punti aperti** |  | 

<br>

| | |
| :- | :- |
| **Titolo** | GestionePrenotazioni |
| **Descrizione** | Gestione delle prenotazioni di un cliente registrato |
| **Attori** | ClienteRegistrato | 
| **Relazioni** | Login, ListaPrenotazioni, NuovaPrenotazione | 
| **Precondizioni** | | 
| **Postcondizioni** | | 
| **Scenario Principale** | 1. Il cliente registrato esegue il login <br> 2. Il cliente può visualizzare le proprie prenotazioni passate o in corso e può effettuare nuove prenotazioni.|
| **Scenari Alternativi** | |
| **Requisiti non funzionali** | Velocità di verifica dei dati e semplicità di navigazione tra le diverse maschere |
| **Punti aperti** |  | 

<br>

| | |
| :- | :- |
| **Titolo** | Login |
| **Descrizione** | Permette di accedere al sistema | 
| **Attori** | ClienteRegistrato, Farmacista | 
| **Relazioni** | NuovaPrenotazione, GestioneFarmacia | 
| **Precondizioni** |  | 
| **Postcondizioni** | L'utente ha accesso al sistema, limitato in base ai suoi privilegi | 
| **Scenario principale** | 1. L'utente inserisce le credenziali di accesso <br> 2. Il sistema verifica le credenziali <br> 3. Se le credenziali sono corrette, viene presentata la schermata iniziale | 
| **Scenari Alternativi** | Scenario a: Credenziali non riconosciute. <br> 3. Il sistema non riconosce le credenziali e rispedisce l'utente alla schermata di login con un messaggio di errore| 
| **Requisiti non funzionali** | Velocità di verifica delle credenziali |
| **Punti aperti** |  | 

<br>

---

<br>

## Analisi del Rischio

<br>

### Tabella Valutazione dei Beni

<br>

Bene | Valore | Esposizione
--- | --- | ---
Sistema Informativo | Alto. Fondamentale per il funzionamento del servizio | Alta. Perdita finanziaria e di immagine
Informazioni dei clienti | Medio. Dati generali dei clienti della farmacia, comprese le credenziali | Alta. Perdita di immagine dovuta alla divulgazione di dati sensibili
Informazioni relative al personale | Alto. Dati relativi ai farmacisti, incluse le credenziali di accesso all'area riservata | Molto Alta. Perdita finanziaria dovuta a usi impropri delle credenziali con privilegi elevati. Perdita di immagine possibile con la divulgazione dei dati relativi ai clienti
Dati delle prenotazioni | Alto. Necessario per tenere traccia delle prenotazioni | Molto Alta. Perdita finanziaria dovuta allo smarrimento di prenotazioni. Perdita di immagine con la divulgazione dei farmaci prenotati dai clienti


### Tabella Minacce/Controlli

<br>

Minaccia | Probabilità | Controllo | Fattibilità
--- | --- | --- | ---
Furto credenziali Farmacista | Alta | Controllo sulla sicurezza della password - Log delle operazioni | Costo implementativo molto basso
Furto credenziali Cliente | Alta | Controllo sulla sicurezza della password - Log delle operazioni | Costo implementativo molto basso
Alterazione o intercettazione delle comunicazioni | Alta | Utilizzo di un canale sicuro <!-- (TLS) --> - Log delle operazioni | Basso costo di realizzazione con determinati protocolli
Accesso non autorizzato al database | Bassa | Accesso da macchine sicure - Log di tutte le operazioni | Basso costo di realizzazione, il server deve essere ben custodito
DoS | Bassa | Controllo e limitazione delle richieste | Media complessità di implementazione
Saturazione del database | Bassa | 1. Limitazione delle richieste in un dato intervallo di tempo. <br> 2. Limite di tempo per la verifica di un cliente | Media complessità di implementazione

<br>
<br>

### Analisi Tecnologica della Sicurezza

<br>

Tecnologia | Vulnerabilità |
--- | --- |
Autenticazione username/password | • Utente rivela volontariamente la password Utente rivela la password con un attacco di ingegneria sociale <br>• Utente non esce dal sistema dopo aver eseguito le operazioni <br> • Password banali
Cifratura comunicazioni | • In caso di cifratura simmetrica particolare attenzione va alla lunghezza delle chiavi ed alla loro memorizzazione <br>• La memorizzazione è un fattore fondamentale anche nella cifratura asimmetrica
Architettura Client/Server | • DoS <br> • Man in the Middle <br> • Sniffing delle comunicazioni | 

<br>
<br>

### Security Use Case & Misuse Case Scenari

| | |
| :- | :- |
| **Titolo** | Riservatezza |
| **Descrizione** | I dati non sono accessibili da chi non ne ha i permessi | 
| **Misuse case** | Sniffing | 
| **Relazioni** | |
| **Precondizioni** | L'attaccante ha i mezzi per intercettare i messaggi del sistema |
| **Postcondizioni** | Il sistema impedisce all'attaccante di decifrare (in tempi utili) i messaggi intercettati |
| **Scenario principale** | 1. Il Sistema protegge i messaggi <br> 2. L'attaccante riesce ad intercettare un messaggio <br> 3. L'attaccante prova a decifrare i messaggi, ma non riesce a trovare un modo per farlo abbastanza velocemente |
| **Scenari di un attacco avvenuto con successo** | 1. Il Sistema protegge i messaggi <br> 2. L'attaccante riesce ad intercettare un messaggio <br> 3. L'attaccante riesce a decifrare i messaggi e a leggerne il contenuto, ma solamente per una sessionedi un utente |

<br>

| | |
| :- | :- |
| **Titolo** | Integrità |
| **Descrizione** | Integrità dei dati del sistema | 
| **Misuse case** | ManInTheMiddle | 
| **Relazioni** | |
| **Precondizioni** | 1. L'attaccante ha i mezzi per intercettare i messaggi del sistema <br> 2. L'attaccante ha i mezzi per modificare i messaggi <br> 3. L'attaccante ha i mezzi per spedire il messaggio modificato al destinatario | 
| **Postcondizioni** | Il sistema rileva il messaggio contraffatto |
| **Scenario principale** | 1. Il Sistema protegge i messaggi <br> 2. L'attaccante riesce ad intercettare un messaggio e lo modifica <br> 3. Il sistema si accorge del messaggio contraffatto e lo segna nei log | 
| **Scenari di un attacco avvenuto con successo** | 1. Il Sistema protegge i messaggi <br> 2. L'attaccante riesce ad intercettare un messaggio e lo modifica <br> 3. Il sistema accetta il messaggio e agisce di conseguenza, segnando il messaggio nei log | 

<br>
<br>

<!-- Da discutere: aggiunta di una seconda keyword giornaliera generata per ogni farmacia, richiesta ad ogni farmacista al momento dell'accesso -->

| | |
| :- | :- |
| **Titolo** | ControlloAccessi |
| **Descrizione** | L'accesso alle funzionalità del sistema deve essere controllato | 
| **Misuse case** | FurtoCredenziali, ManInTheMiddle | 
| **Relazioni** | |
| **Precondizioni** | L'attaccante ha i mezzi per carpire in tutto o in parte le credenziali di accesso di un cliente o di un farmacista | 
| **Postcondizioni** | Il sistema blocca l'accesso non autorizzato e notifica il tentativo di accesso |
| **Scenario principale** | 1. L'attaccante tenta di accedere al servizio spacciandosi per un utente legittimo, di cui conosce le credenziali solo in parte (ad esempio mediante attacco con dizionario) <br> 2. Il sistema non riconosce le credenziali, restituendo un errore <br> 3. In seguito ad un numero fissato di tentativi falliti, il sistema blocca temporaneamente l'accesso a quell'utente e notifica l'anomalia a chi di dovere | 
| **Scenari di un attacco avvenuto con successo** | 1. L'attaccante riesce a carpire le credenziali di accesso complete di un utente in un qualsiasi modo <br> 2. Il sistema riconosce la correttezza delle credenziali, e fornisce l'accesso al soggetto malevolo <br> 3. L'attaccante ha libero accesso al sistema, con privilegi diversi in base al tipo di utente | 

<br>


### Requisiti di Protezione dei Dati

Sussistono inoltre i seguenti requisiti:
1. I dati salvati devono essere protetti da un attaccante che abbia accesso al sistema, prendendo misure di sicurezza fisica, eventualmente cifrando i dati.
2. I dati inviati tra le parti remote devono essere protetti, utilizzando la cifratura dei dati.
3. Tutte le azioni avvenute sul sistema devono essere tracciate tramite un sistema di log. La visione e l'analisi dei log verrà gestita con un editor di testo esterno, accessibile solo al personale autorizzato.


ID | Requisiti | Tipo
--- | --- | ---
R15F | Implementazione di un sistema di log per tracciare tutti i messaggi tra i client e i server, inclusi gli accessi, le richieste di prenotazione, di conferma, di sospensione e di invio e ricezione di dati | Funzionale
R10NF | I dati salvati devono essere protetti da un attaccante che abbia accesso al sistema, prendendo misure di sicurezza fisica, eventualmente cifrando i dati | Non Funzionale
R11NF | I dati inviati tra le parti remote devono essere protetti, utilizzando la cifratura dei dati | Non Funzionale
## Gestione di sessione
Durante l'implementazione abbiamo riscontrato un problema con le gestione della sessione nel server broker per come era specificata dal progetto.

Mentre questa scelta progettuale poteva essere utile a scaricare parte del peso dagli altri server, le tecnologie che ci avrebbero permesso di ottenere la flessibilità necessaria erano troppo inefficienti per un applicazione di grosse dimensioni, così abbiamo deciso di spostare la logica di tracciamento della sessione nei server back-end e di utilizzare come reverse proxy un software ottimizzato per questo fine, come NGINX.

## Autenticazione
Durante la progettazione si era pensato di implementare manualmente l'autenticazione dei clienti con una funzione chiamata verificaCredenziali(), ma in fase di sviluppo abbiamo convenuto che fosse un processo molto delicato e soggetto a errori, che necessitasse di un framework solido e testato. 

Abbiamo quindi deciso di utilizzare Spring Security, che si integra a Spring e ci permette di ottenere una sicurezza e una robustezza maggiore durante l'intero processo di autenticazione, garantendo inoltre un'elevata configurabilità.

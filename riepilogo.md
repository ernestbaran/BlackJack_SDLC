# Riepilogo del lavoro svolto

## Organizzazione del progetto

Ho lavorato partendo da un progetto già esistente di Blackjack sviluppato in HTML, CSS e JavaScript.
Ho inizializzato un repository Git locale e creato il branch `main` per contenere la versione stabile
del gioco.

Successivamente ho creato un branch dedicato `feature-assicurazione` per sviluppare in modo isolato
la nuova funzionalità di assicurazione, senza modificare direttamente il codice principale.

## Feature implementata

La feature sviluppata è l'assicurazione sul Blackjack:

- viene offerta automaticamente quando la carta scoperta del banco è un Asso;
- l'importo dell'assicurazione è pari a metà della puntata principale;
- se il banco ha Blackjack con due carte, l'assicurazione paga 2:1;
- se il banco non ha Blackjack, l'assicurazione viene persa e la mano continua normalmente.

Sono state introdotte variabili dedicate per gestire lo stato dell'assicurazione (importo,
offerta, risoluzione) e sono stati aggiornati i calcoli dei Dobloni e delle vincite, in modo che
l'assicurazione influisca correttamente sul saldo e sulle statistiche.

## Uso di Git e workflow

- Inizializzazione del repository con `git init`.
- Salvataggio dello stato iniziale del progetto con un primo commit.
- Creazione del branch `feature-assicurazione` per lo sviluppo della nuova funzionalità.
- Più commit intermedi per introdurre:
  - l'interfaccia utente dell'assicurazione;
  - la logica di gioco e l'aggiornamento delle statistiche;
  - l'aggiornamento della documentazione (`README.md`, `feature_assicurazione.md`).
- Merge del branch di feature nel branch `main` al termine dello sviluppo.

Questo workflow simula il lavoro in team, dove le nuove funzionalità vengono sviluppate su branch
separati e poi integrate una volta verificate.

## Documentazione e buone pratiche

Per la documentazione del progetto sono stati creati:

- `README.md` per descrivere il progetto e le funzionalità disponibili;
- `feature_assicurazione.md` per documentare nel dettaglio la nuova feature;
- `riepilogo.md` per spiegare l'organizzazione del lavoro e l'uso degli strumenti di versionamento.

Nel codice JavaScript sono stati inseriti commenti per spiegare le parti principali della logica,
in particolare la gestione dell'assicurazione e la fase di calcolo delle vincite.

## Testing

Sono stati eseguiti test manuali sui seguenti casi:

1. Banco con Asso e banco *non* in Blackjack: l'assicurazione viene offerta, l'importo viene
   scalato dal saldo e, se il banco non ha 21 con due carte, l'assicurazione viene persa.
2. Banco con Asso e banco in Blackjack: l'assicurazione viene offerta, in caso di acquisto paga 2:1
   e compensa la perdita della puntata principale.
3. Mani in cui il banco non mostra Asso: l'assicurazione non viene proposta e la partita segue
   il flusso normale.

Questi test garantiscono che la funzionalità di assicurazione si comporti in modo coerente con le
regole previste e che non interferisca con le altre parti del gioco.

# Feature: Assicurazione nel Blackjack

## Descrizione

La feature introduce la possibilità di comprare l'assicurazione
quando la carta scoperta del banco è un Asso, in modo simile ai casinò reali.

## Regole

- L'assicurazione è disponibile solo se:
  - il banco mostra un Asso come prima carta scoperta;
  - il giocatore non ha un Blackjack naturale.
- L'importo dell'assicurazione è pari a metà della puntata principale.
- Per comprare l'assicurazione il giocatore deve avere abbastanza Dobloni.
- Se il banco ha Blackjack:
  - l'assicurazione paga 2:1;
  - il giocatore perde la puntata principale ma recupera grazie all'assicurazione.
- Se il banco non ha Blackjack:
  - l'assicurazione viene persa;
  - la mano continua normalmente con la puntata principale.

## Obiettivi

- Simulare una regola reale del Blackjack.
- Gestire correttamente Dobloni, messaggi e statistiche.

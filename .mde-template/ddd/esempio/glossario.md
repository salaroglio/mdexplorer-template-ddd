---
title: Il linguaggio del dominio
---

# Il linguaggio del dominio

## TL;DR

Le parole dell'help desk di Alpina con un significato solo, prese dai requisiti e dall'architettura del pilota. Sono quelle
che persone e codice devono usare uguali.

- 14 termini e 6 azioni; la parola che conta di più è **bozza**: l'assistente propone, non risponde.
- Da non usare: «risposta proposta» (si dice bozza), «voce FAQ» (si dice articolo).
- Due ambiguità aperte: «cliente» e «risolto».

## I termini

| Termine | Definizione | Da non usare | Contesto | Fonte |
|---|---|---|---|---|
| Ticket | una richiesta di un cliente all'help desk | richiesta, chiamata | Ticket | 02, «Il percorso di un ticket» |
| Stato del ticket | a che punto è un ticket: aperto, in attesa di approvazione, risolto, scalato | — | Ticket | 02, «Il modello dei dati» |
| Cliente | chi apre il ticket | utente | Ticket | 01, «Il contesto» |
| Operatore | la persona dell'help desk che decide la risposta | agente | Ticket | 01, TL;DR |
| Bozza | la risposta che l'assistente propone, con le fonti; non parte mai da sola | risposta proposta, risposta automatica | Assistenza | 01, R2-R3 |
| Fonte | un articolo o un ticket già chiuso usato per scrivere la bozza | riferimento | Assistenza | 01, R2 |
| Fiducia | quanto l'assistente è sicuro della bozza, fra 0 e 1 | punteggio | Assistenza | 02, «Il percorso di un ticket» |
| Soglia di fiducia | sotto questa fiducia non si propone una bozza | — | Assistenza | 02, «La configurazione» |
| Assistente | il servizio che legge il ticket e propone la bozza | bot, motore | Assistenza | 02, «I componenti» |
| Base di conoscenza | gli articoli e i ticket chiusi da cui l'assistente prende le fonti | FAQ, catalogo | Conoscenza | 02, «I componenti» |
| Articolo | una voce della base di conoscenza, con il suo testo | voce FAQ | Conoscenza | 01, R2 |
| Valutazione | il giudizio dell'operatore su una bozza: accettata, modificata, scartata | conferma | Valutazione | 01, R5 |
| Primo contatto | un ticket risolto alla prima risposta, senza scalarlo | — | Valutazione | 01, O2 |
| Secondo livello | il gruppo che riceve i ticket scalati | — | Ticket | 02, «Il percorso di un ticket» |

## Le azioni

| Azione | Chi | Su che cosa |
|---|---|---|
| cercare le fonti | l'assistente | la base di conoscenza |
| proporre | l'assistente | una bozza per un ticket |
| approvare, modificare, scartare | l'operatore | una bozza |
| inviare | il sistema dei ticket, dopo l'approvazione | la risposta al cliente |
| scalare | l'operatore o l'assistente senza bozza | un ticket, al secondo livello |
| misurare | — | il tasso di risoluzione al primo contatto |

## Ambiguità

- **Cliente**: nei requisiti è chi apre il ticket; nel modello dei dati (02) ha anche un contratto. Da decidere se il
  contratto è del contesto Ticket o di un altro.
- **Risolto**: un ticket con la bozza approvata, o con la risposta inviata? Cambia quando si conta il primo contatto.

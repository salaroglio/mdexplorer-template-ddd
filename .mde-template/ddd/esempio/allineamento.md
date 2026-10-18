---
title: Allineamento con il codice
---

# Allineamento con il codice

## TL;DR

Il codice del pilota (`codice/assistente-helpdesk/`) ha una cartella per contesto, ma l'Assistenza fa il lavoro del Ticket:
cambia lo stato del ticket, manda le notifiche e chiama le metriche. Cinque scarti; il più grave è lo stato del ticket.

- Ogni contesto ha la sua cartella; manca il Modello linguistico (il pilota cerca per parole chiave).
- L'Assistenza attraversa il confine del Ticket in tre punti.
- Tre termini del glossario nel codice hanno un altro nome: bozza, articolo, valutazione.

## Dove sta ogni contesto

| Contesto | Cartella e namespace | Tipi principali |
|---|---|---|
| Ticket | `Tickets/`, `Alpina.HelpDesk.Tickets` | `Ticket` (`Tickets/Ticket.cs:4`), `StatoTicket` (`:23`), `IArchivioTicket` (`Tickets/IArchivioTicket.cs:6`) |
| Assistenza | `Assistente/`, `Alpina.HelpDesk.Assistente` | `ServizioAssistente` (`Assistente/ServizioAssistente.cs:11`), `IMotoreRisposte` (`Assistente/IMotoreRisposte.cs:6`), `Risposta` (`Assistente/Risposta.cs:4`) |
| Conoscenza | `Conoscenza/`, `Alpina.HelpDesk.Conoscenza` | `CatalogoFaq` (`Conoscenza/CatalogoFaq.cs:7`), `VoceFaq` (`Conoscenza/VoceFaq.cs:6`) |
| Valutazione | `Metriche/`, `Alpina.HelpDesk.Metriche` | `MetricheRisoluzione` (`Metriche/MetricheRisoluzione.cs:7`) |
| Notifiche | `Notifiche/`, `Alpina.HelpDesk.Notifiche` | `INotifica` (`Notifiche/INotifica.cs:4`) |
| Modello linguistico | — | non c'è: `MotoreRisposteParoleChiave` cerca per parole chiave |

## Dipendenze

| Dal codice | Dove | La mappa la prevede? |
|---|---|---|
| Assistenza → Ticket (archivio e stato) | `Assistente/ServizioAssistente.cs:31`, `:36` | sì per l'archivio; no per lo stato |
| Assistenza → Conoscenza | `Assistente/MotoreRisposteParoleChiave.cs:11` | sì, ma con un contratto di ricerca |
| Assistenza → Notifiche | `Assistente/ServizioAssistente.cs:52`, `:64` | no: le notifiche sono del Ticket |
| Assistenza → Valutazione | `Assistente/ServizioAssistente.cs:53`, `:65` | no: la Valutazione ascolta il Ticket |

## Termini

| Glossario | Nel codice | Esito |
|---|---|---|
| bozza | `Ticket.RispostaProposta` (`Tickets/Ticket.cs:20`), `Risposta` (`Assistente/Risposta.cs:4`) | sinonimo da non usare |
| articolo | `VoceFaq` (`Conoscenza/VoceFaq.cs:6`) | sinonimo da non usare |
| base di conoscenza | `CatalogoFaq` (`Conoscenza/CatalogoFaq.cs:7`) | sinonimo da non usare |
| valutazione (accettata, modificata, scartata) | solo `Conferma` (`Assistente/ServizioAssistente.cs`) | manca: niente «modificata» né «scartata» |
| scalare, secondo livello | `Scala`, la stringa `"secondo-livello"` (`Assistente/ServizioAssistente.cs:64`) | il nome c'è, il secondo livello no |
| stato del ticket | `StatoTicket` (`Tickets/Ticket.cs:23`): `InAttesaDiConferma` | «in attesa di approvazione» nel glossario |

## Confini attraversati

- L'Assistenza decide lo stato del ticket: `ticket.Stato = …` in `Assistente/ServizioAssistente.cs:36`, `:51`, `:63`.
- L'Assistenza scrive la bozza dentro il ticket (`ticket.RispostaProposta`, `:35`): la bozza è sua, il ticket no.

## Scarti, dal più grave

1. **Lo stato del ticket lo cambia l'Assistenza** (`Assistente/ServizioAssistente.cs:36`, `:51`, `:63`). La mappa: lo
   decide il Ticket, l'Assistenza chiede.
2. **Notifiche e metriche le chiama l'Assistenza** (`:52-53`, `:64-65`), e il primo contatto è sempre vero
   (`primoContatto: true`, `:53`). La mappa: il Ticket pubblica gli eventi, la Valutazione li ascolta.
3. **Il motore dipende dalla classe concreta `CatalogoFaq`** (`Assistente/MotoreRisposteParoleChiave.cs:11`). La mappa:
   un contratto di ricerca, perché la ricerca per significato (A2) possa entrare.
4. **La valutazione dell'operatore manca**: solo la conferma; «modificata» e «scartata» (R5) non ci sono.
5. **Tre nomi diversi dal glossario**: `RispostaProposta`, `VoceFaq`, `CatalogoFaq`.

## Come è stato fatto

Nell'esempio questo rapporto è scritto a mano, leggendo il codice, nello stesso formato che userebbe l'agente
verificatore. In un giro vero lo scrive l'agente con gli strumenti del grafo del codice (`code_overview`,
`code_find_symbol`, `code_neighbors`) dopo l'analisi della cartella `codice/assistente-helpdesk/`.

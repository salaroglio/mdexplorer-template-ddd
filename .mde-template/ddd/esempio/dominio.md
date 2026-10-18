---
title: Il dominio
---

# Il dominio

## TL;DR

L'assistente AI dell'help desk di Alpina Servizi: legge un ticket, cerca le fonti nella base di conoscenza e propone una
bozza di risposta, che l'operatore approva, modifica o scarta. Tutto inventato, dalla demo di MdExplorer.

- I documenti sono i requisiti e l'architettura del pilota.
- Il codice è il programma C# del pilota, in `codice/assistente-helpdesk/`.
- La cartella del codice è segnata per il grafo del codice (C#).

## Che cosa fa il sistema

Aiuta gli operatori dell'help desk di Alpina Servizi a rispondere prima e meglio ai clienti: propone, l'operatore decide.

## I documenti da cui partire

- `ddd/fonti/01-obiettivi-e-requisiti.md` — gli obiettivi e i requisiti del pilota.
- `ddd/fonti/02-architettura.md` — i componenti, il percorso di un ticket, il modello dei dati.

## Il codice

- `codice/assistente-helpdesk/` — il programma C# del pilota (namespace `Alpina.HelpDesk`), segnato per il grafo del
  codice con il linguaggio C#.

---
title: Sviluppo con DDD
---

# Sviluppo con DDD

## TL;DR

Un metodo di lavoro per MdExplorer: il DDD strategico. Si fissano il linguaggio del dominio, i contesti e la loro mappa,
poi la mappa si confronta con il codice vero attraverso il grafo del codice di MdExplorer. Tre agenti preparano, le persone
approvano e decidono.

- Si sceglie in «Crea nuovo progetto» o si aggiunge a un progetto che c'è già; si aggiorna e ci si può staccare.
- Porta solo la sua cartella e due skill; i file del gruppo nascono una volta in `ddd/`.
- Con l'esempio, il progetto nasce con l'help desk di Alpina: documenti, codice C# e il giro già fatto (dati inventati).

## Che cosa porta

| Che cosa | Dove |
|---|---|
| Il workflow | `workflows/ddd.md` |
| Le schede dei tre agenti | `agents/` |
| I ruoli: Responsabile del dominio, Architetto | il documento delle responsabilità del progetto, come ruoli aperti |
| Le istruzioni per gli agenti del progetto | un blocco in `CLAUDE.md`, `AGENTS.md`, `copilot-instructions.md` |
| I file iniziali del gruppo | `ddd/`, copiati una volta da `semi/` |
| Le skill | `.claude/skills/ddd-linguaggio/`, `.claude/skills/ddd-contesti/` |

Il passo sul codice usa il grafo del codice: la cartella del codice va segnata (menu della cartella → «Ambiente di
sviluppo») e analizzata.

## Come si comincia

1. Compila `ddd/dominio.md`, con il capitolo «Il codice».
2. Segna la cartella del codice per il grafo del codice e lascia finire l'analisi.
3. Chi risponde di un ruolo lo prende nel documento delle responsabilità (o con «È mio» nella città degli agenti).
4. Il responsabile del dominio lancia «Linguaggio del dominio».

## Che cosa viene dopo

Il DDD tattico (aggregati, entità, oggetti valore, eventi del dominio), con una versione successiva.

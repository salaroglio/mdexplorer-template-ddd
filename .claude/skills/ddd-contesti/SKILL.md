---
name: ddd-contesti
description: "Come si disegnano i bounded context e la context map nel DDD strategico: confini, scopo, termini di ogni contesto e i patti fra contesti (cliente-fornitore, conformista, livello anticorruzione, linguaggio pubblicato, kernel condiviso). Usala quando scrivi o rivedi ddd/contesti.md."
---

# I contesti e la loro mappa

Un **bounded context** è una parte del sistema dentro cui ogni parola del glossario ha un significato solo. La **context
map** dice come i contesti dipendono l'uno dall'altro e con che patto.

## Come si trovano i confini

- Dove una parola cambia significato, passa un confine.
- Dove cambia chi decide (un'altra persona, un altro ruolo, un altro ritmo di cambiamento), passa un confine.
- Un contesto ha uno **scopo** in una frase; se servono due frasi, forse sono due contesti.
- Distingui il **cuore** (ciò che rende il sistema diverso dagli altri) dai contesti **di supporto** e da quelli
  **generici** (notifiche, autenticazione): il cuore merita il modello più curato.

## I patti fra contesti

| Patto | Quando |
|---|---|
| Cliente-fornitore | un contesto usa l'altro, che tiene conto delle sue esigenze |
| Conformista | un contesto usa l'altro così com'è, senza poter chiedere niente |
| Livello anticorruzione | un contesto traduce il modello dell'altro, perché non entri nel suo |
| Linguaggio pubblicato | un contesto espone eventi o un formato stabile, che gli altri ascoltano |
| Kernel condiviso | due contesti condividono un pezzo di modello, e lo cambiano insieme |

Chi **decide lo stato** di una cosa sta nel contesto che la possiede: un altro contesto chiede, non cambia.

## Il formato di `ddd/contesti.md`

- `## TL;DR`: tre righe e tre punti, scritto per ultimo.
- `## I contesti`: per ognuno scopo, tipo (cuore, supporto, generico), i termini del glossario che gli appartengono, che
  cosa possiede e decide.
- `## La mappa`: il diagramma PlantUML (un rettangolo per contesto, una freccia per dipendenza con il patto sulla freccia,
  skill `mde-plantuml`) e una tabella dipendenza → patto → perché.
- `## Da decidere`: ciò che il glossario lascia aperto e cambia i confini.

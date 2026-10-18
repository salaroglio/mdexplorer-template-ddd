---
mde_type: workflow
title: Il DDD strategico, dal linguaggio alla mappa
workflow: ddd.workflow.json
---

# Il DDD strategico, dal linguaggio alla mappa

## TL;DR

Prima del codice si decidono i confini: il **linguaggio** del dominio (ogni parola con un significato solo), i
**contesti** in cui il sistema si divide e la **mappa** di come dipendono l'uno dall'altro. Poi la mappa si confronta con
il codice vero, attraverso il grafo del codice di MdExplorer, e l'architetto decide.

- Il responsabile del dominio lancia il linguaggio e lo approva; l'architetto avvia i contesti e li approva.
- L'allineamento con il codice parte da solo: un rapporto, il codice non si tocca.
- Gli scarti col codice diventano lavoro da pianificare; la mappa si rifà solo se è sbagliata lei.

## Il giro

```plantuml(@workflow, ./ddd.workflow.json)
```

## Chi fa che cosa

| Passo | Chi lavora | Che cosa consegna | Chi approva |
|---|---|---|---|
| Linguaggio del dominio | agente analista | `ddd/glossario.md` | il responsabile del dominio |
| Contesti e mappa | agente architetto | `ddd/contesti.md` | l'architetto |
| Allineamento con il codice | agente verificatore | `ddd/allineamento.md` | l'architetto |
| Accetta la mappa | l'architetto | la decisione, nel registro dei giri | — |

## Parole

| Parola | Che cos'è | Un'analogia |
|---|---|---|
| Linguaggio ubiquo | le parole del dominio, con un significato solo, usate uguali da persone e codice | un'interfaccia pubblica: un nome, un contratto |
| Bounded context | una parte del sistema dentro cui ogni parola ha un significato solo | un assembly con i suoi tipi |
| Context map | come i contesti dipendono l'uno dall'altro, e con che patto | il grafo delle dipendenze fra progetti |
| Livello anticorruzione | un traduttore fra due contesti, perché il modello dell'altro non entri nel nostro | un adapter |

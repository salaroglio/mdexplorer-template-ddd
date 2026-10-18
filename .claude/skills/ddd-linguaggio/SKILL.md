---
name: ddd-linguaggio
description: "Come si scrive il glossario del linguaggio ubiquo nel DDD: ogni termine del dominio con una definizione sola, i sinonimi da non usare, il contesto e la fonte. Usala quando scrivi o rivedi ddd/glossario.md, o quando ti chiedono che cosa significa una parola del dominio."
---

# Il linguaggio del dominio

Nel DDD le persone del dominio e il codice usano **le stesse parole con lo stesso significato**. Il glossario è il posto
dove quelle parole si fissano: se una parola ha due significati, quello è un confine fra due contesti, o un'ambiguità da
decidere.

## Come si trovano i termini

- I **nomi** che i documenti usano per le cose del dominio (ticket, cliente, bozza…) e i **verbi** per ciò che succede
  (proporre, approvare, scalare…). I verbi contano quanto i nomi.
- I **sinonimi**: due parole per la stessa cosa («bozza» e «risposta proposta»). Se ne sceglie una, l'altra va fra quelle
  da non usare.
- Le **parole con due significati** («cliente» come persona e come contratto): non si risolvono qui, si scrivono fra le
  ambiguità con i punti in cui compaiono.

## Il formato di `ddd/glossario.md`

- `## TL;DR`: tre righe e tre punti, scritto per ultimo.
- `## I termini`: una tabella con **termine**, **definizione** (una frase, con le parole del dominio), **da non usare**
  (i sinonimi), **contesto** (se già si vede), **fonte** (documento e sezione).
- `## Le azioni`: i verbi, con chi le fa e su che cosa.
- `## Ambiguità`: le parole con più significati, dove compaiono, che cosa va deciso.

Fra 10 e 30 termini per una prima versione. Niente nomi di classi o tabelle: quelli sono il codice, che si confronta dopo.

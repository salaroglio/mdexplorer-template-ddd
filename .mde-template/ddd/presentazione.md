---
document_type: slides
reveal:
  theme: mde-space
---

<!-- .slide: data-background-image="/mde-space/sfondi/luna.svg" class="mde-cielo" -->
<img class="mde-icona-grande" src="/mde-space/icone/satellite.svg" alt="">

# Sviluppo con DDD

Il DDD strategico: il linguaggio del dominio, i contesti e la loro mappa,
**confrontati con il codice vero**.

---

## <img class="mde-icona" src="/mde-space/icone/telescopio.svg" alt=""> A che cosa serve

- Le stesse parole vogliono dire cose diverse in parti diverse del sistema
- Il DDD strategico le fissa: un linguaggio, dei contesti, una mappa fra loro
- Qui la mappa non resta un disegno: si confronta con il codice attraverso il **grafo del codice** di MdExplorer

---

## <img class="mde-icona" src="/mde-space/icone/razzo.svg" alt=""> Il giro

1. **Linguaggio del dominio** — il glossario, una parola un significato
2. **Contesti e mappa** — dove vale ogni parola, e i patti fra i contesti
3. **Allineamento con il codice** — la mappa contro le dipendenze vere
4. **Accettazione** — l'architetto decide

---

## <img class="mde-icona" src="/mde-space/icone/satellite.svg" alt=""> Le parole

| Parola | In breve | Come… |
|---|---|---|
| Linguaggio ubiquo | un significato per parola | un'interfaccia pubblica |
| Bounded context | dove quel significato vale | un assembly |
| Context map | le dipendenze fra contesti | le dipendenze fra progetti |
| Anticorruzione | il traduttore fra contesti | un adapter |

---

## <img class="mde-icona" src="/mde-space/icone/astronauta.svg" alt=""> Chi fa che cosa

| Ruolo | Che cosa fa |
|---|---|
| Responsabile del dominio | approva il linguaggio del dominio |
| Architetto | approva contesti e allineamento, accetta la mappa |

Tre agenti preparano (analista, architetto, verificatore), **le persone approvano e decidono**.

---

## <img class="mde-icona" src="/mde-space/icone/base.svg" alt=""> Che cosa trovi nel progetto

- `ddd/`: il dominio da descrivere, con il capitolo «Il codice»
- tre agenti e i loro ruoli, ancora senza nome; le skill del linguaggio e dei contesti
- **con l'esempio**: l'help desk di Alpina, documenti e codice C#, con il giro già fatto (dati inventati)

---

<!-- .slide: data-background-image="/mde-space/sfondi/alieni.svg" class="mde-cielo" -->
## <img class="mde-icona" src="/mde-space/icone/razzo.svg" alt=""> Come si comincia

1. Compila `ddd/dominio.md`, con il capitolo «Il codice»
2. Segna la cartella del codice (menu della cartella → «Ambiente di sviluppo») e lascia finire l'analisi
3. Ognuno prende il suo ruolo («È mio»)
4. Il responsabile del dominio lancia «Linguaggio del dominio»

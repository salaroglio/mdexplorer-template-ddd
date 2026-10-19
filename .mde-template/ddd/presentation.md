---
document_type: slides
reveal:
  theme: mde-space
---

<!-- .slide: data-background-image="/mde-space/sfondi/luna.svg" class="mde-cielo" -->
<img class="mde-icona-grande" src="/mde-space/icone/satellite.svg" alt="">

# Development with DDD

Strategic DDD: the domain language, the contexts and their map,
**compared with the real code**.

---

## <img class="mde-icona" src="/mde-space/icone/telescopio.svg" alt=""> What it is for

*This method is in Italian: its documents, agents and workflow speak Italian.*

- The same words mean different things in different parts of the system
- Strategic DDD pins them down: one language, some contexts, a map between them
- Here the map does not stay a drawing: it is compared with the code through MdExplorer's **code graph**

---

## <img class="mde-icona" src="/mde-space/icone/razzo.svg" alt=""> The round

1. **Domain language** — the glossary, one word one meaning
2. **Contexts and map** — where each word holds, and the agreements between contexts
3. **Alignment with the code** — the map against the real dependencies
4. **Acceptance** — the architect decides

---

## <img class="mde-icona" src="/mde-space/icone/satellite.svg" alt=""> The words

| Word | In short | Like… |
|---|---|---|
| Ubiquitous language | one meaning per word | a public interface |
| Bounded context | where that meaning holds | an assembly |
| Context map | who depends on whom | project references |
| Anti-corruption | a translator | an adapter |

---

## <img class="mde-icona" src="/mde-space/icone/astronauta.svg" alt=""> Who does what

| Role | What they do |
|---|---|
| Domain owner | approves the domain language |
| Architect | approves contexts and alignment, accepts the map |

Three agents prepare (analyst, architect, checker), **the people approve and decide**.

---

## <img class="mde-icona" src="/mde-space/icone/base.svg" alt=""> What you find in the project

- `ddd/`: the domain to describe, with the chapter «Il codice» (the code)
- three agents and their roles, nobody's yet; the language and contexts skills
- **with the example**: the Alpina help desk, documents and C# code, with the round already done (invented data)

---

<!-- .slide: data-background-image="/mde-space/sfondi/alieni.svg" class="mde-cielo" -->
## <img class="mde-icona" src="/mde-space/icone/razzo.svg" alt=""> How to start

1. Fill in `ddd/dominio.md`, with the chapter «Il codice»
2. Mark the code folder (folder menu → «Development environment») and let the analysis finish
3. Each one takes their role («It's mine»)
4. The domain owner starts «Linguaggio del dominio»

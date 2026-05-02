# Agentic Enterprise Manifesto

**Principles for governing AI agents at organizational scale.**

*Witold Reichhart and Arnaud Gelas, 2026*

---

An enterprise that uses agents is not an agentic enterprise. An agentic enterprise is one where governed agents, operating on governed intelligence, exercise collective initiative at organizational scale — perceiving what matters, reasoning about institutional consequences, and surfacing action opportunities before being asked.

This manifesto specifies what that requires.

---

## Reading guide

| Document | What it covers |
|---|---|
| [manifesto.md](manifesto.md) | Core document — 6 values, 12 principles, worked example, failure modes, metrics, adoption path |
| [companion-guide.md](companion-guide.md) | Operational detail — initiative conditions, governance relocation mechanics, consequence classes, enterprise lifecycle interactions, boundary conditions |
| [glossary.md](glossary.md) | Term definitions as used in this framework |

## Position in the agentic governance stack

The Agentic Enterprise Manifesto (AEnt-M) is **the top layer of a layered stack**. It depends on the layers below it. The dependency direction is explicit:

```
Agentic Engineering Manifesto (AEM)
   ├─ Agentic SDLC (ASDLC) — engineering-side governance of agent-built code
   ├─ Agentic Product Lifecycle (APLC) — product-side governance of agent behavior
   ├─ Intelligence Governance Manifesto (IGM) — substrate that agents reason over
   └─ Agentic Enterprise Manifesto (AEnt-M) — enterprise coordination of multiple agents on a shared substrate
       ├─ depends on IGM (substrate)
       └─ inherits AEM principles
```

What this means for AEnt-M:

- **AEnt-M depends on IGM.** AEnt-M coordinates *multiple* governed agents on a *shared* substrate. That substrate is what IGM defines. AEnt-M Principle 1 (the domain graph as enterprise infrastructure) and Principle 5 (agents share a substrate; they do not share a mind) presuppose IGM's claim model, lifecycle, provenance, and authority structure. An organisation that adopts AEnt-M without IGM has named the coordination problem without specifying what is coordinated.
- **AEnt-M inherits AEM principles.** AEM's twelve principles — outcomes, specifications, autonomy tiers, knowledge & memory, evaluations, observability, emergence & containment, economics, accountability — are not re-litigated here. AEnt-M extends them to the enterprise surface: collective initiative, governance relocation, composite state, three concurrent lifecycles, consequence-class accountability. Where AEnt-M appears to soften an AEM minimum bar (e.g. low-consequence accountability), the integration note resolves the apparent conflict; AEM's minimum bar is the floor.
- **AEnt-M does not stand alone.** Unlike IGM, AEnt-M has no standalone-usable mode. Its principles are coordination principles; what they coordinate is defined elsewhere. Adopting AEnt-M without AEM, ASDLC, APLC, and IGM produces enterprise-level vocabulary applied to ungoverned underlying systems.

## Audience

AEnt-M is written for **technical governance leaders, architecture boards, and CTOs/CIOs/CROs operating regulated agentic estates** — readers who own decisions about substrate investment, governance relocation, consequence-class assignment, and three-lifecycle coordination. It is not a board-level executive primer and does not stand in for one. Generalist executive briefings should reference the stack-level introduction, not this manifesto.

See [`/agentic-governance-stack.md`](../agentic-governance-stack.md) for the canonical one-page stack reference, the repo-root `glossary.md` for the term-collision preface, and `governance/governance-integration-note.md` (DRAFT — author review needed) and `governance/authority-accountability-matrix.md` (DRAFT — author review needed) for the cross-stack integration artefacts.

## Key concepts

**Initiative vs. autonomy** — Autonomy requires capability. Initiative requires capability plus substrate depth, constraint legibility, and governance relocation. The difference is what the enterprise invests in.

**Governance relocation** — Governance enforcement migrates from synchronous pre-action checking to substrate-resident causal structure, per action class, with demonstrated control equivalence. Reversible. Measurable.

**Composite state** — An agent's behavioral identity: code + prompt + model + knowledge base + memory state. When any component changes, the agent changes. At enterprise scale, a model update changes everything.

**Domain graph** — The shared institutional substrate. What the Intelligence Governance Manifesto maintains. What this manifesto builds on.

## Academic foundations

The five-paper programme on Enterprise AI and Organizational Intelligence (Reichhart, 2025-2026, SSRN) provides the theoretical basis. The open-source governance frameworks for agentic engineering, delivery, and product management (Gelas, 2025-2026, GitHub) provide the engineering basis.

## Status

Version 0.2 — May 2026. This is a living document. We welcome critical engagement — particularly from practitioners in regulated industries testing these principles against operational reality.

## Contributing

Open an issue or submit a pull request. We value substance over polish.

## Authors

- **[Witold Reichhart](https://github.com/witoldreichhart)** — intelligence architecture, autonomy-to-initiative theory, enterprise governance
- **[Arnaud Gelas](https://github.com/arnaudgelas)** — agentic engineering, delivery lifecycle, product lifecycle

## License

CC BY-SA 4.0

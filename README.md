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

## The governance stack

This manifesto is the enterprise layer of a five-layer governance stack for deploying AI agents in regulated industries:

| Layer | Governs | Source |
|---|---|---|
| **Engineering** | How human-agent loops build software | [Agentic Engineering Manifesto](https://github.com/arnaudgelas/agentic-engineering-manifesto) (Gelas) |
| **Delivery** | How agent-built software reaches production | [ASDLC](https://github.com/arnaudgelas/asdlc) (Gelas) |
| **Product** | How agent products behave in production | [APLC](https://github.com/arnaudgelas/aplc) (Gelas) |
| **Intelligence** | What agents know and how knowledge is maintained | [Intelligence Governance Manifesto](https://github.com/witoldreichhart/intelligence-governance-manifesto) (Reichhart and Gelas) |
| **Enterprise** | How governed agents on governed intelligence produce institutional value | **This repo** (Reichhart and Gelas) |

Each layer is necessary. None is sufficient alone.

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

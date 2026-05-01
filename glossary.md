# Agentic Enterprise — Glossary

**Witold Reichhart and Arnaud Gelas**

Terms as used in the Agentic Enterprise Manifesto and companion guide. Definitions are scoped to this framework — some terms carry broader meanings elsewhere. For intelligence-layer terms (claim, confidence, provenance, contradiction, decay, L1/L2/L3), see the [Intelligence Governance Manifesto glossary](https://github.com/witoldreichhart/intelligence-governance-manifesto/blob/main/glossary.md).

---

## Enterprise Concepts

**Agentic enterprise** — An enterprise where governed agents, operating on governed intelligence, exercise collective initiative at organizational scale. Not an enterprise that uses agents. The distinction is whether the system can perceive what matters and surface action opportunities aligned with institutional purpose — or whether it only executes assigned tasks faster.

**Organizational intelligence** — The system-level capacity to perceive institutionally relevant patterns, infer their consequences, and select action opportunities under changing constraints. A property of the agent-substrate system — not the model alone. Emerges from the interaction between inferential capability (model), governed knowledge (substrate), and institutional constraints (governance architecture).

**Institutional reasoning** — The system's capacity to trace from a proposed action through the claims that inform it to the organizational obligations, risk exposures, and downstream consequences that constrain it — and surface conflicts before action is taken. Distinct from task execution, which produces outputs without reasoning about institutional consequences.

**Collective initiative** — The enterprise-level capacity to surface action opportunities aligned with organizational purpose across domain boundaries. Not the sum of individual agent initiatives — it requires coherence across the agent portfolio, shared substrate, and shared constraint architecture.

**Enterprise coherence** — The property that agents across the enterprise operate within a shared governed substrate, shared constraint architecture, and shared understanding of institutional purpose. Autonomy is constrained to the degree necessary for coherence. Coherence without initiative is a failure mode (see manifesto).

---

## Agent Governance

**Autonomy** — An agent's capacity to execute assigned tasks independently within defined parameters. Requires only capability. The agent does what it is told, reliably.

**Initiative** — An agent's capacity to surface action opportunities aligned with institutional purpose before being asked. Requires three conditions: substrate depth, constraint legibility, and governance relocation. The difference between autonomy and initiative is what the enterprise invests in, not what the model is capable of.

**Composite state** ��� An agent product's behavioral identity, determined by five components simultaneously: application code, system prompt, foundation model, knowledge base, and memory state. When any component changes, the agent's behavior may change. At enterprise scale, a single foundation model update can alter composite state across the entire agent portfolio simultaneously.

**Consequence class** — A classification of agent actions by estimated institutional impact: low, medium, high, or critical. Determines human accountability level, review requirements, and epistemic failure response. Assigned per action class, not per individual action.

**Action class** — A category of agent action with similar risk characteristics. Examples: "generate client settlement report," "flag potential compliance breach," "execute trade." Consequence class, governance relocation status, and epistemic thresholds are set per action class.

**Scoped view** — The subgraph of the domain graph that an agent receives, filtered by task scope and authorization level. Shared substrate does not mean shared context — each agent sees only what it is authorized to access for its current task.

---

## Governance Mechanics

**Governance relocation** — The mechanism by which governance enforcement migrates from synchronous pre-action constraint checking to substrate-resident causal structure that agents encounter during normal reasoning. Operates per action class. Requires demonstrated control equivalence. Reversible — if the substrate degrades, governance re-tightens.

**Control equivalence** — Evidence that a relocated governance mechanism achieves equal or better control outcomes than the synchronous check it replaced. Assessed through decision quality comparison, error detection rates, response time to degradation, and audit reconstructability.

**Epistemic response classes** — The system's response when epistemic confidence falls below threshold, scaled by consequence class: block, escalate, restrict scope, advisory only, or continue with enhanced monitoring. "Fail closed" is the default for high-consequence actions; lower-consequence actions may degrade gracefully.

**Epistemic circuit breaker** — A mechanism that triggers an epistemic response when confidence falls below the threshold for a given action's consequence class. Produces a structured escalation identifying the epistemic defect and what is blocked pending resolution.

---

## Lifecycle Concepts

**Intelligence lifecycle** — The five concurrent stages that maintain the governed substrate: Ingest, Consolidate, Curate, Expand, Apply. Operates at weeks-to-months cadence. The heartbeat of the agentic enterprise. Specified in the Intelligence Governance Manifesto.

**Agent lifecycle** — The stages of an agent product from conception through retirement, as specified in the APLC. Operates at days-to-weeks cadence. At enterprise scale: managing an agent portfolio with composite state tracking, behavioral baselines, and drift detection.

**Delivery lifecycle** — The pipeline from agent-built code through production, as specified in the ASDLC. Operates at hours-to-days cadence. Evidence bundles trace from code to claims to governance status.

**Cross-lifecycle cascade** — An event in one lifecycle that triggers review in another. Example: a claim demotion in the intelligence lifecycle triggers review of delivered code that depended on that claim. The enterprise must detect and manage cascades across all three lifecycles.

---

## Substrate Concepts

**Domain graph** — The shared institutional substrate. Accumulated, governed, compounding knowledge that sits between foundation model capability and application context. No single agent owns it. Every agent reasons over it. Maintained through the intelligence lifecycle. Specified in the Intelligence Governance Manifesto.

**Substrate depth** — A composite of coverage (claims across major knowledge types), connectivity (causal, temporal, and scope relationships), and currency (claims within revalidation windows) for a specific domain. One of three conditions for initiative.

**Constraint legibility** — The degree to which institutional constraints (policies, risk appetites, regulatory boundaries, authority structures) are represented in a form agents can reason over. One of three conditions for initiative.

**Substrate compounding** — The property that the domain graph grows by generation — new connections, new validated claims, new cross-domain edges — through normal business operation. Each engagement enriches the substrate. The competitive advantage that cannot be purchased.

**Substrate pollution** — Ungoverned enrichment of the domain graph. Claims that enter outside the governed lifecycle, bypass validation, or carry false provenance. A governance obligation, not just a quality issue.

---

## The Governance Stack

**Five-layer governance stack** — The complete governance architecture for deploying AI agents in regulated industries: Engineering (how agents build), Delivery (how agent-built software reaches production), Product (how agent products behave), Intelligence (what agents know), Enterprise (how the whole system produces institutional value). Each layer is necessary. None is sufficient alone.

---

*This is a companion to the Agentic Enterprise Manifesto (Reichhart and Gelas, 2026). Licensed under CC BY-SA 4.0.*

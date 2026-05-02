# Agentic Enterprise — Glossary

**Witold Reichhart and Arnaud Gelas**

Terms as used in the Agentic Enterprise Manifesto and companion guide. Definitions are scoped to this framework — some terms carry broader meanings elsewhere. For intelligence-layer terms (claim, epistemic tier, provenance, contradiction, decay, L1/L2/L3), see the [Intelligence Governance Manifesto glossary](https://github.com/witoldreichhart/intelligence-governance-manifesto/blob/main/glossary.md).

> **Naming convention.** Across this repo, **"epistemic tier"** is preferred over **"confidence"** for the scalar substrate-level meaning (Provisional / Candidate / Supported / Confirmed / Foundational). AEM reserves *confidence* for its binary verification meaning. Where prior text used "confidence" in the substrate sense, it has been replaced with "epistemic tier" or "epistemic quality" as appropriate. Repo-root `glossary.md` carries the term-collision preface for the whole framework family.

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

**Scoped view** — The subgraph of the domain graph that an agent receives, filtered by task scope and authorization level. Shared substrate does not mean shared context — each agent sees only what it is authorized to access for its current task. Filtering rules are normative and applied in this order: (1) *authorization filter* — claims the agent's role is not authorized to access are excluded; (2) *task-scope filter* — claims outside the declared task scope (jurisdiction, business unit, product line) are excluded; (3) *epistemic-tier filter* — claims below the minimum epistemic tier required for the action's consequence class are excluded; (4) *contradiction-status filter* — superseded claims are excluded unless explicitly requested as historical context, and contradicted claims are surfaced with their conflict typing intact rather than silently dropped; (5) *decay filter* — stale claims outside their revalidation window are flagged or excluded per the action class's freshness policy. The combination of the five filters defines what the agent can see; nothing else may enter the agent's reasoning surface from the substrate.

**Action opportunity** — A candidate task an agent has perceived from the substrate without being assigned it: a pattern, contradiction, or consequence chain whose institutional significance the agent has surfaced before being asked. Action opportunities are *demand candidates*, not loop-ready specifications. Before any agent acts on an action opportunity, it must re-enter the AEM loop and pass the AEM loop-readiness gate (see [`/agentic-engineering-manifesto/principles/specifications.md`](https://github.com/arnaudgelas/agentic-engineering-manifesto)). The capacity to surface action opportunities is the operational signature of *initiative* (P6).

**Epistemic quality** — The composite assessment of how trustworthy the claim base supporting an agent's reasoning chain is at the moment of action. It summarises the *epistemic tier* (see IGM) of each load-bearing claim, the freshness of those claims relative to their decay windows, the presence and typing of unresolved contradictions, the completeness of provenance, and the scope match between claim and use context. *Epistemic quality* is what the *epistemic circuit breaker* evaluates against the threshold for the action's consequence class. *Epistemic tier* is a property of a single claim; *epistemic quality* is a property of a reasoning chain. The two terms are not interchangeable.

**Epistemic tier** — The IGM-defined epistemic weight of a single claim (Provisional, Candidate, Supported, Confirmed, Foundational). This term replaces the prior usage of *confidence* in the IGM and AEnt-M document set: AEM reserves *confidence* for its binary verification meaning ("the team has confidence the change is safe to release"), and IGM/AEnt-M use *epistemic tier* for the scalar substrate-level weight. See the IGM glossary for the full tier ladder and promotion rules.

**Temporal supersession** — A contradiction type in which a newer claim supersedes an older claim of the same scope and authority because the underlying reality has changed (regulation amended, procedure updated, vendor configuration revised). The older claim is demoted, not deleted; the supersession chain is preserved so prior actions remain auditable against the claim that was current at the time. Distinct from *jurisdictional divergence*: a temporal supersession resolves to a single current claim, whereas a jurisdictional divergence preserves multiple co-valid claims.

**Jurisdictional divergence** — A contradiction type in which two or more claims are simultaneously valid because they apply to different scopes (jurisdictions, business units, product lines, regulatory regimes). Neither claim supersedes the other; both are preserved with explicit scope tags. The substrate must surface the divergence whenever an action's scope intersects more than one of the diverging regimes. Distinct from *temporal supersession*.

**Retrieval governance** — The control layer that determines what an agent may *access* from the substrate: which subgraph, which epistemic tiers, which scopes, which provenance classes. Operationalised through the *scoped view* filtering rules above. Owned by the AEnt-M Workflow Owner / Decision Reviewer (per consequence class) in coordination with the IGM Semantic Authority. One of the three control layers introduced in Principle 5.

**Reasoning governance** — The control layer that determines what *inferences* an agent may *draw* over the claims it has retrieved: which inference patterns are permitted, what minimum *epistemic quality* an inference chain must meet for a given consequence class, which contradiction types must block versus flag versus inform the inference. Owned by the AEnt-M Accountable Authority in coordination with the IGM Inference Authority. The second of the three control layers introduced in Principle 5.

**Action governance** — The control layer that determines what an agent may *do* once it has retrieved claims and drawn inferences: which action classes are permitted at the agent's current consequence class and governance-relocation stage, what human accountability applies, what response class fires when *epistemic quality* falls below threshold. Owned by the AEnt-M consequence-class authority in coordination with the AEM autonomy-tier authority. The third of the three control layers introduced in Principle 5.

**Gap flag** — A first-class substrate object indicating that a region of the domain graph is *known to be missing* a claim that institutional reasoning over the domain would require. A gap flag carries: the domain and subdomain it covers, the type of claim that is absent (regulatory, procedural, vendor-config, operational, etc.), the authority responsible for closing it, and the consequence class of actions that would be impaired by the gap. Gap flags are returned alongside matching claims in scoped-view queries (Principle 3); an agent reasoning over a region with an open critical gap flag must treat the gap as if it were an unresolved contradiction for the purpose of the epistemic circuit breaker. Gap flags are how the substrate is *safely incomplete* rather than *falsely complete* (see Companion, "Boundary conditions").

**Harvest mode** — Synonym for the IGM *Ingest* stage as it appears in the worked example. Where the manifesto worked example refers to "Harvest mode (automated monitoring of ESMA publications)," the canonical IGM term is *Ingest* — the first stage of the intelligence lifecycle, covering automated monitoring, scheduled pulls, and operator-driven acquisition of source material into the governed substrate. The two terms refer to the same activity; future revisions will normalise on *Ingest*.

---

## Governance Mechanics

**Governance relocation** — The mechanism by which governance enforcement migrates from synchronous pre-action constraint checking to substrate-resident causal structure that agents encounter during normal reasoning. Operates per action class. Requires demonstrated control equivalence. Reversible — if the substrate degrades, governance re-tightens.

**Control equivalence** — Evidence that a relocated governance mechanism achieves equal or better control outcomes than the synchronous check it replaced. Assessed through decision quality comparison, error detection rates, response time to degradation, and audit reconstructability.

**Epistemic response classes** — The system's response when *epistemic quality* falls below threshold, scaled by consequence class: block, escalate, restrict scope, advisory only, or continue with enhanced monitoring. "Fail closed" is operationalised per consequence class (see manifesto Principle 11): block + dual-authority notification at Critical, block + structured escalation at High, escalate to Decision Reviewer at Medium, restrict scope or advisory at Low.

**Epistemic circuit breaker** — A mechanism that triggers an epistemic response when *epistemic quality* falls below the threshold for a given action's consequence class. Produces a structured escalation identifying the epistemic defect and what is blocked pending resolution.

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

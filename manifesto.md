# The Agentic Enterprise Manifesto

**Principles for governing AI agents at organizational scale.**

*Authors: **[Witold Reichhart](https://github.com/witoldreichhart) and [Arnaud Gelas](https://github.com/arnaudgelas)***
*Version: 0.2 — May 2026*

---

## Position in the Agentic Governance Stack

The Agentic Enterprise Manifesto (AEnt-M) is **the top layer of a layered governance stack**. It depends on the layers below it; it is not a free-standing companion to them. The dependency direction is explicit:

```
Agentic Engineering Manifesto (AEM)
   ├─ Agentic SDLC (ASDLC) — engineering-side governance of agent-built code
   ├─ Agentic Product Lifecycle (APLC) — product-side governance of agent behavior
   ├─ Intelligence Governance Manifesto (IGM) — substrate that agents reason over
   └─ Agentic Enterprise Manifesto (AEnt-M) — enterprise coordination of multiple agents on a shared substrate
       ├─ depends on IGM (substrate)
       └─ inherits AEM principles
```

This diagram is the canonical statement of the relationship and supersedes any earlier "complementary" or "companion" framing in the AEnt-M document set. The dependency declarations are normative:

- **AEnt-M depends on IGM.** The substrate AEnt-M coordinates over is the substrate IGM defines (claim model, lifecycle, provenance, contradiction handling, decay management, four authorities). AEnt-M Principle 1 (the domain graph as enterprise infrastructure) and Principle 5 (agents share a substrate; they do not share a mind) are not buildable without IGM.
- **AEnt-M inherits AEM principles.** AEM's twelve principles — outcomes, specifications, autonomy tiers, knowledge & memory, evaluations, observability, emergence & containment, economics, accountability — are not re-litigated here. AEnt-M extends AEM to the enterprise surface; it does not replace AEM minimum bars and, where it appears to soften one (e.g. the low-consequence accountability class), the integration note resolves the apparent conflict in AEM's favour.
- **AEnt-M is not standalone-usable.** Unlike IGM, which has a constrained standalone mode for single-agent contexts inside an AEM-conformant loop, AEnt-M coordinates *multiple* governed agents on a *shared* substrate. Without AEM, ASDLC, APLC, and IGM beneath it, AEnt-M's vocabulary names a coordination problem whose underlying systems remain undefined.

See [`/agentic-governance-stack.md`](../agentic-governance-stack.md) for the canonical one-page stack reference, the repo-root `glossary.md` for the term-collision preface, and `governance/governance-integration-note.md` (DRAFT — author review needed) and `governance/authority-accountability-matrix.md` (DRAFT — author review needed) for the cross-stack integration artefacts.

---

## The argument

The agentic enterprise is not an enterprise that uses agents. It is an enterprise where governed agents, operating on governed intelligence, exercise collective initiative at organizational scale.

That sentence contains three load-bearing words: *governed*, *intelligence*, and *initiative*. Remove any one and you get something different. Agents without governance produce fast, fluent, catastrophically incomplete action. Governance without intelligence produces compliance without perception. Intelligence without initiative produces knowledge that sits there. The agentic enterprise requires all three simultaneously — and the current tooling addresses them separately.

Three governance architectures now exist for different layers of the agentic stack. The [Agentic Engineering Manifesto](https://github.com/arnaudgelas/agentic-engineering-manifesto) specifies how human-agent engineering loops work — principles for building software where agents participate as first-class engineering citizens. The [Agentic Software Development Lifecycle (ASDLC)](https://github.com/arnaudgelas/asdlc) specifies how agent-built software gets delivered — four layers from demand through operations, with evidence bundles, autonomy tiers, and named human accountability at every gate. The [Agentic Product Lifecycle (APLC)](https://github.com/arnaudgelas/aplc) specifies how agent products behave in production — seven stages from conception through retirement, with composite state hashing, behavioral evaluation portfolios, and five distinct incident classes.

These are necessary. They are not sufficient.

Each governs an individual agent or an individual delivery pipeline. None addresses what happens when you wire governed agents together into an enterprise-level system that must perceive, judge, and act across organizational boundaries.

Rule-based enterprise automation has been tried before — from business process engines to RPA to early agent orchestration. The pattern is consistent: executable rules can coordinate transactions, but they do not by themselves provide institutional memory, domain reasoning, accountable decision rights, or adaptive governance. Faster rule execution does not produce institutional judgment.

The agentic enterprise is not rule-based automation with better tooling. It is a different architecture: governed agents operating over governed institutional knowledge, with human accountability and auditable control paths. The difference is substrate. Where rule-based systems follow predetermined logic, the agentic enterprise reasons over a governed domain graph — accumulated, validated, continuously maintained institutional knowledge that deepens through operation.

This manifesto specifies what that architecture requires.

---

## What we value

We hold these commitments. In each pair, the first is what the agentic enterprise prioritizes; the second is what it also values but will not sacrifice the first to achieve.

**Collective initiative** over individual agent performance.
An enterprise where every agent executes brilliantly on its assigned task but none perceives what the organization needs is a sophisticated tool factory. The agentic enterprise optimizes for the system's capacity to surface action opportunities aligned with organizational purpose — even when that means constraining individual agent performance.

**Governed substrate** over model capability.
A more capable model on a shallow substrate produces faster, more confident wrong answers. A governed substrate with a less capable model produces slower, traceable, correctable judgment. The substrate is the asset. The model is replaceable.

**Institutional reasoning** over task execution.
The difference between an enterprise that uses agents and an agentic enterprise is whether the system can reason about institutional consequences — not just "what happens if I do X" but "what does X mean for the organization's obligations, risks, and trajectory." Task execution is necessary. Institutional reasoning is what makes it worth governing. Institutional reasoning means the system can trace from a proposed action through the claims that inform it to the organizational obligations, risk exposures, and downstream consequences that constrain it — and surface conflicts before action is taken.

**Compounding intelligence** over scaling compute.
Scale produces capability. It does not produce institutional knowledge. The agentic enterprise compounds intelligence through operation — each engagement enriches the governed substrate, each contradiction resolved deepens institutional reasoning, each governance decision adds to the causal structure available to every agent in the system. A competitor can buy more compute. They cannot purchase the compounded history of governed operation.

**Governance relocation** over rule enforcement.
Rules are where governance starts. They are not where it should stay. As the governed substrate deepens for a specific action class, the causal rationale that governance rules protect becomes structurally represented in the substrate itself — agents encounter the consequence structure during normal reasoning, not as a separate compliance check. The agentic enterprise does not pile on more rules as it scales. It builds the substrate depth that allows governance enforcement to shift from external friction to substrate-resident structure — measurably, reversibly, per action class, under continuous monitoring.

**Enterprise coherence** over agent autonomy.
An agent that is autonomous but misaligned with organizational purpose is not a capability — it is a risk. The agentic enterprise constrains individual agent autonomy to the degree necessary for enterprise-level coherence. Agents operate within a shared governed substrate, shared constraint architecture, and shared understanding of institutional purpose. Autonomy is useful. Coherence is required.

---

## Sixteen principles

*Principles 1–12 specify the agentic enterprise. Principles 13–16 (Part IV) close gaps surfaced by the AEM coverage map (`governance/aem-principle-coverage-map.md`) and apply to every principle in Parts I–III.*

### Part I — The governed substrate

*The agentic enterprise depends on a governed intelligence substrate as specified in the [Intelligence Governance Manifesto](https://github.com/witoldreichhart/intelligence-governance-manifesto). The IGM defines claim-level governance, provenance, epistemic tier (formerly "confidence"), contradiction management, decay monitoring, and the intelligence lifecycle in detail. The four principles below specify what the enterprise layer requires of that substrate — not how it is built. AEnt-M follows the repo-wide convention that **"epistemic tier"** replaces **"confidence"** for the scalar substrate-level meaning, freeing *confidence* for AEM's binary verification meaning. See `glossary.md` for the term-collision preface.*

**1. The domain graph is enterprise infrastructure, not an agent feature.**
The governed domain graph — the accumulated, validated, compounding substrate of institutional knowledge — sits between the foundation model and application context as shared infrastructure. Every agent in the enterprise reasons over it. No agent owns it. It is maintained through a governed lifecycle, enriched through operation, and decays under explicit management. The domain graph is to the agentic enterprise what the general ledger is to financial accounting: the single governed substrate that makes enterprise-level coordination possible.

**2. Intelligence is a system property, not a model property.**
Organizational intelligence is the capacity to perceive institutionally relevant patterns, infer their consequences, and select action opportunities under changing constraints. It emerges from the interaction between inferential capability (the model), governed knowledge (the substrate), and institutional constraints (the governance architecture). No single component produces it. Replacing the model does not destroy it. The substrate and constraints carry the institutional reasoning; the model provides the inferential engine.

**3. The substrate must support structured inquiry, not just retrieval.**
Enterprise agents do not just retrieve relevant documents. They operate over structured claims — assertions with provenance, epistemic tier, temporal validity, scope, contradiction status, and governance status. Queries return not just matching claims but adjacent conflicts, epistemic-tier warnings, dependency chains, and gap flags. The substrate supports institutional reasoning because it surfaces what is contradicted, what is stale, what is missing, and what epistemic tier to assign — not just what is textually relevant.

**4. The substrate deepens through use.**
Each engagement, each governance decision, each contradiction resolved enriches the shared substrate. The domain graph grows by generation — new connections, new validated claims, new cross-domain edges — through normal business operation. This compounding is the agentic enterprise's structural advantage. It is also its governance obligation: every enrichment must pass through the governed lifecycle. Ungoverned enrichment is substrate pollution.

### Part II — Enterprise agent governance

**5. Agents share a substrate; they do not share a mind.**
Each agent in the agentic enterprise accesses the domain graph through scoped views — receiving the subgraph relevant to its task and authorization level. Shared substrate does not mean shared context. Retrieval governance (what may an agent access?), reasoning governance (what inferences may it draw?), and action governance (what may it do?) operate as three distinct control layers. The enterprise controls what any agent can see, think, and do — independently.

**6. Initiative is earned through substrate depth; autonomy requires only capability.**
Autonomy requires capability — the agent can execute independently within assigned parameters. Initiative — the capacity to surface action opportunities aligned with institutional purpose before being asked — requires three additional conditions: a governed domain graph deep enough for the agent to perceive institutionally relevant patterns in its operating domain, a constraint architecture legible enough for the agent to reason about what actions are permissible, and governance relocation advanced enough that the agent encounters institutional constraints during normal reasoning rather than as external gates.

An enterprise that grants agents autonomy without building the substrate for initiative gets fast execution and zero perception. The three conditions are measurable (see Metrics below) and define the investment thesis for the agentic enterprise: build the substrate, earn the initiative.

*Example — autonomy vs. initiative:* An autonomous agent in settlement operations executes CSDR penalty calculations correctly when assigned. An agent with initiative — operating over a deep, governed substrate — notices that a pending UK regulatory change will create a jurisdictional divergence with current EU penalty methodology, identifies which cross-border settlement programmes are affected, and surfaces this as an action opportunity to the governance team before the change takes effect. The second agent was not assigned this task. It perceived the pattern because the substrate was deep enough to make it visible.

*Ingestion trigger — clarification.* Consistent with Principle 3, the agent does not ingest the regulatory document itself. The pending UK change enters the substrate as a *Candidate-tier claim* through the IGM Ingest stage (governed monitoring, automated harvesting, or operator submission); the agent then perceives the divergence by reasoning over claims — comparing the new Candidate-tier UK claim against the existing Confirmed-tier EU claim within its scoped view. *The agent's input is always claims, not source documents.* What changed is that a new claim entered, not that the agent began parsing source material.

**7. Governance relocation is measured, not assumed.**
As the domain graph deepens for a specific action class, governance enforcement for that class can shift from synchronous pre-action constraint checking toward asynchronous verification and audit sampling. This shift is governance relocation — the enforcement locus migrating from external rules to substrate-resident causal structure.

Relocation is not an entitlement earned by maturity claims. It requires demonstrated **control equivalence**, evaluated through the four evidence categories specified in the Companion Guide ("Control equivalence"): *decision quality comparison*, *error detection rate*, *response time to degradation*, *audit reconstructability*. The Companion is the canonical specification of the evidence framework; the present principle restates the operational signals the enterprise watches *for each of the four categories*:

- *Declining governance intervention rates with stable or improving decision quality* — the decision-quality category supports relocation.
- *Flat or rising intervention rates* — substrate depth is insufficient. Do not relocate.
- *Declining intervention rates with declining decision quality* — governance is weakening. Reverse the relocation.

These three operational signals are derived from the *decision-quality-comparison* evidence category; the other three categories (error detection, response time, audit reconstructability) are tracked alongside, per the Companion. A regulator reviewing the control framework should see: which action classes have relocated governance, what evidence supports equivalent control outcomes across all four categories, and what monitoring detects degradation. Relocation operates per action class, not globally, and is reversible — if the substrate degrades for a given action class, governance re-tightens for that class.

**8. Human accountability is scoped by consequence class.**
The agentic enterprise assigns human accountability by the consequence level of the action, not per individual agent action.

- *Low consequence* — explicitly **carved out of the AEM-governed envelope** per [`/integration/low-consequence-resolution.md`](../integration/low-consequence-resolution.md). An action class qualifies as Low only when **all** of the following hold: no client impact, no regulatory exposure, no irreversibility, no PII processing, no financial exposure, no safety implications, no precedent-creation. The AEM per-action accountability minimum bar (`manifesto-principles.md` P12) does not apply to actions in this class. Instead: workflow-level accountability — a named human (workflow owner) owns the workflow, accepts accountability for its design, its class assignment, and its periodic review. Individual actions are logged with reasoning chain, claims cited (if any), and the workflow tag. Post-hoc audit sampling (recommended floor: ≥1% of actions or ≥30 actions per workflow per month, whichever is larger) is reviewed by the workflow owner. Any action that breaches any of the seven criteria is immediately reclassified and AEM-governed remediation applies. Defaulting to Low without those criteria demonstrably true is a governance failure, not a tier election.
- *Medium consequence* (client recommendations, internal reports) — human accountability at the decision level. Named human reviews the agent's reasoning chain and epistemic quality summary before the recommendation is delivered.
- *High consequence* (trade execution, regulatory filing, compliance determination) — human accountability at the action level. Named human reviews full reasoning chain with epistemic tiers, provenance, and contradiction flags before action proceeds.
- *Critical consequence* (cross-border regulatory submission, systemic risk assessment) — dual human accountability. Two-person review with escalation to governance authority.

In regulated environments, "the agent decided" is never an acceptable escalation path. Agents execute. Humans are accountable. This is not a transitional arrangement pending better AI — it is a design principle. The accountability assignment, the authority scope, and the reasoning chain from agent recommendation through human decision to executed action are recorded for every action above the low-consequence threshold.

#### Rights and remedies for affected natural persons (DRAFT — regulatory positioning, author review needed)

Where an agent-mediated decision affects a natural person — as is routinely the case in financial-services use cases such as lending decisions, claims handling and adjudication, employment screening, fraud-decisioning, and access to essential services — accountability to the institution is necessary but not sufficient. The affected person has rights, and the enterprise must operationalise three pathways:

- **Explanation pathway.** The affected person may request, and must receive within a defined SLO, a meaningful explanation of the agent-mediated decision: the categories of input considered, the load-bearing claims that informed the recommendation (with their epistemic tiers), the human role in the decision, and the contestation pathway. This pathway is the operational counterpart of GDPR Article 22's *meaningful information about the logic involved* and the EU AI Act's deployer-instructions and information-to-natural-persons obligations.
- **Contestation pathway.** The affected person may challenge the decision and have the challenge reviewed by a human at a level of accountability appropriate to the action's consequence class — at minimum the named Decision Reviewer (Medium), Accountable Authority (High), or Dual Authority (Critical). Contestation must be logged, the human review must be recorded with the reviewer's identity and rationale, and the outcome of the contestation must be communicated to the affected person within a defined SLO. Contestation is *not* a request for re-execution by the same agent on the same substrate; it is review by a human with the authority to override.
- **Remedy pathway.** Where contestation upholds the challenge, the enterprise must provide an effective remedy: reversal of the action where reversible, compensation or correction where not, and update of the substrate (claims, scope tags, gap flags) so that the same decision is not produced for the next affected person. This pathway is the operational counterpart of CoE Framework Convention on AI Article 11 (effective remedies) and aligns with GDPR remedies and supervisory powers.

These pathways are *required* for any AEnt-M deployment whose action classes affect natural persons in the senses above. They apply at all consequence classes, with the SLOs and reviewer levels scaling per class. The pathways are recorded in the evidence bundle alongside the agent-mediated decision they relate to. Concrete SLOs, communication templates, and the regulator-recipient list per jurisdiction are domain work; this manifesto fixes the obligation, not the timing.

> **DRAFT note.** This subsection commits the manifesto to a regulatory position that should be reviewed by the authors against current GDPR Art. 22 case law (including post-*Schufa* and post-*Dun & Bradstreet* developments) and the deployer-side obligations of the EU AI Act as they enter application from August 2026. The phrasing here is operationally faithful but legally non-binding pending that review.

### Part III — Enterprise operations

**9. Composite state is enterprise state.**
An agent product's behavioral identity is determined by five components simultaneously: application code, system prompt, foundation model, knowledge base, and memory state. When any component changes — including a model update the engineering team did not initiate — the composite state changes and the agent's behavior may change with it. At enterprise scale, this means foundation model updates propagate across every agent in the system simultaneously.

The enterprise must detect, evaluate, and explicitly accept or reject composite state changes across its entire agent portfolio. The default is reject. Accepted changes are logged with the accepting authority. Undetected composite state drift is the enterprise equivalent of a silent configuration change in production — the system is no longer what you tested.

Composite-state changes originating from the IGM Curate cycle (continuous claim-level changes — promotions, demotions, supersessions, retirements) follow a class-based precedence specified in [`/integration/composite-state-vs-curate-precedence.md`](../integration/composite-state-vs-curate-precedence.md): **Class 1** routine revalidations within decay-window bounds are pre-accepted (logged, not gated); **Class 2** consequential demotions on critical-path claims for High/Critical action classes require composite-state acceptance with a 4-hour SLO and a named Accountable Authority; **Class 3** emergency retirements on integrity grounds (per IGM Principle 14) bypass the composite-state lock with immediate log and post-hoc review within 24 hours. The default-reject rule applies in full to non-Curate-originated composite-state changes (foundation-model updates, prompt revisions, application-code changes, memory-state revisions).

*Detection, evaluation, acceptance — operational specification.* The three steps have distinct mechanisms and named accountabilities:

| Step | Mechanism | Accountable role |
|---|---|---|
| **Detect** | *Automated.* Continuous composite-state hashing across the five components (application code, system prompt, foundation model, knowledge base, memory state). Provider-side change feeds (foundation-model release notes, SaaS-embedded-agent build IDs) are polled on a documented cadence and reconciled against the current hash. Manual detection is allowed only as a backstop for components without machine-readable change feeds, and is escalated as a control gap. | Engineering steward (per APLC) |
| **Evaluate** | *Combined automated + human.* Behavioural-baseline regression on the affected agent's evaluation portfolio runs automatically; a human evaluator (the named Decision Reviewer for the affected consequence class) reviews the regression report and the change diff before an accept/reject recommendation is issued. | Decision Reviewer for the affected agent's consequence class |
| **Accept / reject** | *Human, named, recorded.* No automated path may set the composite state to *accepted*. Acceptance is signed by the consequence-class authority for the highest class served by the affected agent, with the rationale, the regression evidence, and the accepter's identity recorded in the evidence bundle. Rejection rolls the agent back to the prior accepted composite state and records a control-gap event if the rolled-back state is no longer reachable (e.g. provider has removed the model version). | Accountable Authority (High/Critical) or Decision Reviewer (Low/Medium) |

**10. Decay is managed, not prevented.**
Knowledge decays. Regulatory interpretations shift. Operational workarounds expire. Market conditions change. The agentic enterprise does not pretend its substrate is permanent. It manages decay explicitly — different decay rates for different knowledge types, different maintenance cadences per decay class, continuous monitoring for staleness, fragmentation, and drift. An enterprise substrate that is large but stale is worse than one that is small but current, because agents reason over it with unwarranted epistemic weight.

*Decay classes — explicit enumeration.* Decay rates differ by claim type. The substrate maintains at least the following decay classes, each with its own revalidation cadence and ownership:

| Decay class | Typical cadence | Examples | Steward |
|---|---|---|---|
| **Regulatory** | Per regulator publication cycle (often days–weeks at issuance, then quarterly) | EU AI Act articles; ESMA guidelines; CSDR penalty methodology | Legal / regulatory authority |
| **Procedure** | Quarterly or per process change | Settlement workflow; KYC procedure; incident-response runbook | Process owner |
| **Vendor-config** | Per vendor release / model version change | Foundation-model version; SaaS-embedded agent build; data-feed schema | Engineering steward |
| **Operational-workaround** | Monthly until retired or formalised | Manual patch for an upstream-system gap; temporary suppression rules | Operations steward |
| **Reference data** | Per reference-data publication (daily–annual) | Holiday calendars; CCY conversions; counterparty static data | Data steward |
| **Foundational** | Annual review, change-driven | Definitions; entity hierarchies; core taxonomy | Domain expert |

Decay classes are not merely descriptive — each class binds an authority, a cadence, and a response when the cadence is missed (claim demotion, escalation, or retirement). The taxonomy is normative; domains may add classes but may not omit one of the above without an explicit waiver.

**11. The enterprise responds by criticality, not by reflex.**
When *epistemic quality* falls below the threshold for the action's consequence class — stale claims on a critical path, unresolved contradictions in a reasoning chain, scope mismatches between claim and use context, or load-bearing claims below their required *epistemic tier* — the system responds according to the consequence class of the action:

- *Block* — halt the action entirely. Agent produces a structured escalation identifying the epistemic defect and what is blocked pending resolution.
- *Escalate* — route to human decision-maker with full epistemic quality summary.
- *Restrict scope* — narrow the agent's action space to what the current epistemic quality supports.
- *Advisory only* — agent produces recommendation flagged as low-epistemic-quality, with no execution authority.
- *Continue with enhanced monitoring* — action proceeds but triggers enhanced logging, audit sampling, and post-action review.

The response class is set per action class and consequence level, not globally. The system never silently continues at full epistemic weight when epistemic quality is insufficient.

*"Fail closed" — operationalised per consequence class.* "Fail closed" is not a single setting; it is a per-class default that defines what happens when the epistemic circuit breaker fires:

| Consequence class | Default response | What "closed" means | Override authority |
|---|---|---|---|
| **Critical** | *Block + dual-authority notification* | No action. Substrate query refused. Both named accountabilities and the governance authority are paged within the SLO for the class. | Governance authority only; override is logged and reviewed at next governance cadence. |
| **High** | *Block + structured escalation* | No action. Reasoning chain, epistemic-quality summary, and proposed remediation are routed to the named Accountable Authority. | Accountable Authority; override requires written rationale recorded in the evidence bundle. |
| **Medium** | *Escalate to Decision Reviewer* | Action paused. Recommendation packaged with epistemic-quality summary for human decision. | Decision Reviewer; override is logged. |
| **Low** | *Restrict scope or advisory only* | Action narrowed to the substrate region with sufficient epistemic quality, or downgraded to advisory output. May continue with enhanced monitoring. | Workflow Owner; override is sampled in audit. |

"Fail closed" therefore means: *for critical and high actions, no action proceeds*; for medium and low, action is degraded but not silently. Lower-consequence actions may degrade gracefully because the institutional cost of a wrong action is bounded; higher-consequence actions may not, because the institutional cost is not bounded.

**12. Three lifecycles intersect; initiative emerges at the intersection.**
The agentic enterprise operates through three concurrent governance cycles:

The *intelligence lifecycle* (weeks to months) — Ingest, Consolidate, Curate, Expand, Apply — maintains the shared substrate. This is the heartbeat of the agentic enterprise. Without it, the domain graph fossilizes.

The *agent lifecycle* (days to weeks) — conception, specification, build, evaluation, release, operation, maintenance, retirement through the APLC. At enterprise scale: managing an agent portfolio, tracking composite state, detecting drift, maintaining behavioral baselines.

The *delivery lifecycle* (hours to days) — agent-built software delivered through the ASDLC with evidence bundles, specification readiness gates, and operational handoffs.

These timescales are typical ranges, not definitional. Intelligence may change daily in fast-moving regulatory domains. Delivery may take weeks in legacy integration contexts. What matters is that three concurrent cycles operate at different speeds and their intersection is where enterprise behavior emerges.

Initiative does not live in any single lifecycle. It emerges when the intelligence substrate is deep enough, the agent portfolio is governed tightly enough, and the delivery pipeline is traceable enough for the enterprise to trust agents that surface action opportunities before being asked. The agentic enterprise does not program initiative. It builds the conditions from which initiative can emerge — and measures when those conditions are met.

### Part IV — Cross-cutting governance commitments

*The four principles below close gaps surfaced by the AEM coverage map (`governance/aem-principle-coverage-map.md`). They specify the economics of governance, containment for multi-agent emergence, the discipline required when many agents share one substrate, and the architectural enforcement the enterprise layer assumes. They apply to every principle in Parts I–III.*

**13. Governance is paid for; when it costs more than the work, reduce autonomy.**
Governance is not free. The agentic enterprise tracks the **total cost of correctness** for each action class: inference cost, verification cost (evaluations, sampling, replay), governance overhead (review queues, dual-authority reviews, gate friction), incident-remediation cost, and human-review cost. The enterprise reports this cost continuously, not annually.

When governance overhead for an action class exceeds the value of the work that class produces, the enterprise does not "tune the governance" — it changes the contract. Two responses are admissible: **reduce autonomy** (move the action class up the consequence ladder, or revert governance relocation to synchronous gating) or **simplify scope** (narrow the action class until residual risk falls within a cheaper governance envelope). Adding more governance to a class that is already underwater is a failure mode (see *Governance accumulation*).

The enterprise also tracks **multi-model coherence cost**. When two or more foundation models reason over the same substrate, divergence in their architectural decisions (retrieval depth, contradiction handling, scope filtering) shows up as drift in identical workflows. The substrate cannot resolve this. The architecture must: shared retrieval contracts, shared scoped-view computation rules, shared response-class defaults — owned by the enterprise governance authority, not negotiated per-model.

**Metric.** *Governance-cost-to-action-value ratio* per action class. Warning at >0.4; mandatory review at >0.6; autonomy reduction or scope simplification at >0.8 sustained over two reporting periods. The ratio composition is published; "value" includes avoided incident cost and decision-quality uplift, not just cycle-time improvement.

This principle wires the enterprise layer to AEM Principle 11 (Economics) — the AEM cost-of-correctness model is the enterprise's cost-of-correctness model. *DRAFT — thresholds (0.4 / 0.6 / 0.8) are illustrative; enterprises calibrate against their incident-cost baseline.*

**14. Containment is multi-agent, not just epistemic.**
The epistemic circuit breakers in Principle 11 protect the enterprise from acting on bad knowledge. They do not protect it from agents acting badly *on each other*. When N agents share one substrate and a tool surface, additional containment is required.

The enterprise maintains an explicit security threat model for the shared substrate, covering at minimum:

- *Indirect prompt injection across the substrate* — claims (or claim metadata) authored by one agent or one ingestion pipeline mutating the reasoning of another agent that retrieves them.
- *Cross-agent privilege escalation* — one agent (or its delegated worker) acquiring authority through chained tool calls or substrate writes that exceeds its assigned tier.
- *Tool-call poisoning* — adversarial responses from a shared tool propagating into multiple agents' reasoning chains in the same window.
- *Cascade emergence* — one agent's action triggering more than *N* downstream actions in other agents within window *T*, regardless of whether each individual action would have passed its own gate.

The enterprise enforces operational counters for each: *rate limits* per agent, per tool, per substrate write-path; *kill-switch authority* held by the enterprise governance authority and exercisable without dual-authority delay; *cascade detection* monitoring action-graph fan-out in rolling windows; and *quarantine* of any agent or claim implicated in an active incident pending the AEM Principle 10 containment review.

This principle is the multi-agent extension of AEM Principle 10 (Emergence & containment). AEnt-M does not duplicate the AEM threat catalogue — it states the additional surface that emerges when many governed agents share one governed substrate. Cross-reference: the substrate's claim-level threat model lives in IGM (claim poisoning, provenance spoofing, contradiction-injection); this principle covers the *agent-coordination* surface above it.

**Metric.** Mean fan-out per agent action; rate-limit breach rate; kill-switch exercise count and post-incident reviews; cascade-detection true/false-positive rate. Warning at fan-out > *N=5* sustained, or any kill-switch exercise without a published post-incident review within 5 working days. *DRAFT — N and T are configured per domain; the principle is the architecture, not the numbers.*

**15. Right-size the agent portfolio; orchestrators do not escape their tier.**
A multi-agent system on a shared substrate is governed at the portfolio level, not just per agent.

*Orchestrator tier-containment.* An orchestrator agent cannot delegate to a worker agent operating at a higher autonomy tier or a higher consequence class than the orchestrator itself. Tier elevation requires the same governance approval whether requested by a human or by an orchestrator. This is the AEM Principle 4 minimum bar, restated at the enterprise layer: *the swarm cannot grant itself authority it was not granted by humans*.

*Single commit path.* When multiple agents (or an orchestrator and its workers) propose substrate writes, action-class commits, or composite-state changes, the enterprise commits through one path with one ordered queue per substrate domain. Two agents cannot independently land contradictory enrichments; the substrate is one general ledger, not many.

*Conflict-resolution patterns.* When two agents propose contradictory enrichments — or contradictory recommendations against the same action class — the enterprise applies a published resolution pattern: (a) preserve both as typed contradictions in the substrate (IGM behaviour), (b) escalate to the relevant consequence-class authority for the action, (c) tie-break by the priority order in Principle 7's tightening (regulatory > reputational > client > financial), and (d) record the resolution in the agent inventory and the audit trail.

*Agent inventory minimum bar.* The enterprise maintains a portfolio inventory that tracks, at minimum: each agent's autonomy tier, consequence-class scope, orchestrator-worker relationships (who delegates to whom), substrate write authority, kill-switch operator, and last governance review. Shadow agents — agents that consume the substrate without an inventory entry — are blocked at the substrate access layer.

This principle is the AEM Principle 4 (Right-size the swarm) commitment for the enterprise layer. See `governance/authority-accountability-matrix.md` for who approves tier elevation per consequence class.

**16. Architectural enforcement is assumed (stub).**
The Agentic Enterprise Manifesto presumes that every consuming system enforces AEM Principle 3 (defense-in-depth architecture): typed boundaries between agent reasoning and side-effecting tools, capability-scoped credentials, allow-listed tool surfaces, deterministic policy enforcement at the action boundary, and substrate write-paths that are independently auditable from agent reasoning paths.

Where AEnt-M principles assume that a control is enforceable (Principle 5's three-layer governance, Principle 9's composite-state default-reject, Principle 11's response classes, Principle 14's rate limits and kill-switch), the assumption is that AEM Principle 3 architectural enforcement is in place on the consuming system. AEnt-M does not respecify this; it states the dependency.

The enterprise governance authority is responsible for confirming the dependency is met before any action class is admitted to the agentic-enterprise governance regime. Domains for which AEM Principle 3 cannot be evidenced are out of scope for this manifesto. This stub mirrors the planned IGM principle on architectural enforcement (see `governance/aem-principle-coverage-map.md`).

---

## Worked example: regulatory change propagation

A new ESMA guideline amends the penalty calculation methodology for settlement fails under CSDR. This is how the agentic enterprise processes it.

**Intelligence lifecycle responds.** The regulatory claim enters through governed ingestion (Harvest mode — automated monitoring of ESMA publications). The Consolidate stage extracts specific claims: the amended calculation formula, the effective date, the jurisdictional scope. It detects a contradiction with the existing EU penalty methodology claim and a jurisdictional divergence with the UK CREST regime (which has not changed). Both contradictions are typed and preserved — the EU claim is temporal supersession, the UK divergence remains jurisdictional.

**The substrate updates.** The old EU penalty claim is demoted (not deleted — supersession chain maintained). The new claim enters at Candidate epistemic tier. A domain expert validates it against the ESMA source text and promotes it to Confirmed. The Expand stage identifies downstream claims that depend on the old penalty methodology — collateral management calculations, client reporting templates, cross-border settlement programme configurations — and flags them for revalidation.

**An agent with initiative surfaces the action opportunity — as a demand candidate, not a loop-ready specification.** A settlement operations agent, reasoning over the updated substrate, perceives that three cross-border settlement programmes reference the superseded methodology. It emits a structured **opportunity record** (per [`/integration/loop-readiness-for-agent-opportunities.md`](../integration/loop-readiness-for-agent-opportunities.md)) containing: the initiator agent identifier, its current Composite State Hash, the surfacing timestamp, the cited claims with their epistemic tiers and provenance chains, the typed contradictions observed, the proposed action class, the estimated consequence class (Medium — client impact, no direct regulatory filing), and the explicit out-of-scope statement (UK CREST programmes unaffected). The record enters the enterprise opportunity registry.

The agent was not assigned this task. It perceived the pattern because the substrate was deep enough and the contradiction structure made the impact visible. But the agent does not author specifications — it surfaces candidates. The candidate carries no implicit authorisation, no validated business need, and no named accountable human. Those are produced by the absorbing process (ASDLC Layer 1 demand governance), not by the substrate.

**Demand governance triages and reviews loop-readiness.** A named decision reviewer (the Medium-class authority under Principle 8) triages the candidate: plausibility, alignment with current strategy and risk appetite, no duplication, consequence class confirmed at Medium. Triage advances the candidate. The candidate then passes the AEM nine-condition loop-readiness gate (AEM `manifesto.md:198–232`): business need validated against the ESMA publication; success criterion measurable (programme configurations conformant by the effective date); acceptance criteria expressible; constraints identified (regulatory deadline, jurisdictional preservation for UK CREST); accountable human named (settlement operations product owner accepts P12 anchor accountability); blast radius assessed; out-of-scope explicitly stated. The candidate becomes a loop-ready specification. The opportunity record's identifier is recorded in the specification's provenance chain so the audit trail back to the originating substrate event survives.

**The delivery lifecycle executes.** Agent-built configuration changes enter the ASDLC. Evidence bundles trace from the code change to the claims that justified it, to the loop-readiness review that authorised it, to the opportunity record that originated it, to the regulatory source that triggered the substrate event. Composite state changes are recorded for every affected agent product.

**The substrate compounds.** The engagement feedback loop captures what the configuration review revealed: one programme had an undocumented exception to the standard methodology. This enters as a new Provisional claim — operational knowledge that was previously tacit. The substrate is deeper than before the regulatory change.

**The full trace.** An auditor can reconstruct: the regulatory source → the extracted claims → the contradiction detection → the human validation → the agent's pattern perception → the action opportunity → the human approval → the configuration change → the evidence bundle → the composite state update. End to end, from what changed in the regulation to what changed in production, with named humans accountable at every decision point.

---

## The governance stack

Five governance layers, each with a defined scope:

| Layer | Scope | Governs | Source |
|---|---|---|---|
| **Engineering** | How human-agent loops build software | The engineering process | [Agentic Engineering Manifesto](https://github.com/arnaudgelas/agentic-engineering-manifesto) (Gelas) |
| **Delivery** | How agent-built software reaches production | The delivery pipeline | [ASDLC](https://github.com/arnaudgelas/asdlc) (Gelas) |
| **Product** | How agent products behave in production | Individual agent behavior | [APLC](https://github.com/arnaudgelas/aplc) (Gelas) |
| **Intelligence** | What agents know and how knowledge is maintained | The shared substrate | [Intelligence Governance Manifesto](https://github.com/witoldreichhart/intelligence-governance-manifesto) (Reichhart and Gelas) |
| **Enterprise** | How governed agents on governed intelligence produce institutional value | The organization | This manifesto (Reichhart and Gelas) |

Each layer is necessary. None is sufficient alone. The agentic enterprise is the system that operates all five simultaneously.

---

## Failure modes

No governance framework is immune to misuse. These are the ways the agentic enterprise fails in practice.

**Initiative theatre.** Agents are described as "taking initiative" when they are executing predetermined triggers with governance-relocation language applied after the fact. The enterprise reports declining intervention rates because it lowered the thresholds, not because the substrate deepened. *Symptom: governance relocation metrics improve while decision quality metrics are flat or unmeasured.*

**Substrate monoculture.** The governed domain graph becomes the enterprise's only recognized form of institutional knowledge. Communities of practice, apprenticeship, informal knowledge-sharing, and expert networks wither. Everything that cannot be expressed as a governed claim is treated as non-existent. *Symptom: domain experts consult the graph instead of each other; novel situations that have no claim coverage produce organizational paralysis.*

**Governance accumulation.** The enterprise adds governance layers without relocating any. The five-layer stack becomes five layers of friction. Every agent action requires clearance from engineering governance, delivery governance, product governance, intelligence governance, and enterprise governance — sequentially. *Symptom: time from agent recommendation to executed action increases with each governance layer added; governance overhead exceeds the value of automation.*

**Coherence without initiative.** The enterprise is tightly governed — shared substrate, human accountability, composite state tracking, circuit breakers — but produces no institutional value beyond what individual agents would produce independently. The governance architecture works perfectly and the enterprise reasons no better than before. *Symptom: high governance compliance scores, zero action opportunities surfaced by agents, no measurable improvement in institutional reasoning.*

**Substrate capture.** The domain graph reflects one team's, one vendor's, or one business unit's perspective as institutional truth. Claims from other sources are systematically deprioritized or excluded. The governed substrate becomes a governed echo chamber. *Symptom: >80% of validated claims originate from a single organizational source; cross-domain edges are sparse or absent.*

**Accountability diffusion.** Human accountability is formally assigned but practically meaningless. Named humans approve agent actions without reviewing reasoning chains because the volume exceeds their capacity. Accountability becomes a compliance label rather than a governance function. *Symptom: average approval time per action drops below what a meaningful review would require; post-action incident rate is uncorrelated with approval rates.*

**Composite state drift.** Foundation model updates, prompt adjustments, or knowledge base changes alter agent behavior across the enterprise without triggering composite state evaluation. The enterprise is running agents whose behavioral identity has silently changed. *Symptom: no composite state change events logged for 90+ days despite known model provider updates.*

---

## Metrics

Governance claims that cannot be measured are aspirations, not governance. The agentic enterprise tracks signals across three categories.

> **Calibration note.** The numerical thresholds below are *illustrative defaults for a regulated financial-services enterprise operating at scale*. They are starting points, not normative bars. Each enterprise must calibrate them against its own risk appetite, action-class taxonomy, and historical data before treating any threshold as a control. A brief rationale is given for each load-bearing threshold; absence of rationale should be read as "operator must justify before adoption." The thresholds are designed to be empirically tunable: if a domain consistently triggers the warning without a real control failure, the threshold (not the control) is wrong.

### Substrate health

| Metric | Indicates | Warning signal | Rationale (illustrative) |
|---|---|---|---|
| Claim freshness (% within revalidation window) | Substrate currency | <80% | Below 80%, more than one in five load-bearing claims is past its revalidation cadence; agents reasoning over the substrate are statistically likely to anchor on at least one stale claim per high-consequence chain. |
| Provenance completeness (% with full chain) | Audit readiness | <90% | Below 90%, a regulator's ad-hoc audit of ten claims is likely to surface at least one with broken provenance; this is the *audit-survival* threshold, not a quality optimum. |
| Contradiction density (active contradictions / total claims) | Substrate tension — too low suggests suppression, too high suggests curation failure | <1% or >15% (sweet spot **1–15%**) | A real institutional substrate sees genuine, typed contradictions (temporal supersession, jurisdictional divergence). <1% suggests the curation pipeline is silently dropping conflicts; >15% suggests Curate is not keeping pace with Ingest. The 1–15% band is where preserved contradictions remain navigable rather than overwhelming. |
| Unresolved critical contradictions | Governance backlog | Rising trend, **or any contradiction unresolved >30 days** | The 30-day ceiling is illustrative: it bounds the window in which a critical contradiction can sit before it has propagated through enough agent actions to become its own audit liability. Domains with faster regulatory cycles should tighten; domains with stable regulation may extend with explicit waiver. |
| Cross-domain edge density | Substrate connectivity | Declining or flat | Connectivity is the structural prerequisite for institutional reasoning across domain boundaries; flat or declining edges indicate the graph is being grown vertically without horizontal integration. |
| Claim reuse rate (claims consumed by multiple agents) | Substrate utility | <30% | If fewer than three in ten claims serve more than one agent, the substrate is functioning as per-agent storage rather than shared infrastructure (Principle 1). The 30% number is a starting point; high-specialisation domains may run lower with documented justification. |

### Governance effectiveness

| Metric | Indicates | Warning signal | Rationale (illustrative) |
|---|---|---|---|
| Governance intervention rate per action class | Relocation readiness | Flat (no relocation) or declining without quality evidence | A flat curve indicates relocation is not occurring; a declining curve without paired decision-quality evidence is *initiative theatre* (see Failure modes). |
| Decision quality post-action (audit sample) | Governance outcome | Declining in any action class | Decision quality is the only outcome variable that disambiguates real relocation from threshold-lowering; it must not regress in any class for any reason. |
| Human override rate | Governance calibration | >20% (agents miscalibrated) or <1% (rubber-stamping) | The 20% upper band tracks the boundary at which human review is finding genuine errors faster than the agent is producing acceptable recommendations; below 1% the review is likely meaningless (see *Accountability diffusion*). |
| Audit reconstruction time (source → action) | Traceability | **>4 hours** for any action class | DORA Pillar 2 requires firms to be able to reconstruct ICT-incident causal chains within hours, not days; 4 hours is the practical bound at which a regulator's same-business-day request can be served from running systems rather than from forensic recovery. Domains under shorter regulatory clocks (e.g. AI Act Art. 73 serious-incident at 2 days) should tighten. |
| Composite state change detection rate | Portfolio integrity | <100% of known model updates | Anything less than 100% means at least one composite-state change went undetected; given the propagation properties of foundation-model updates across an agent portfolio, the only acceptable miss rate is zero. |

### Enterprise capability

| Metric | Indicates | Warning signal | Rationale (illustrative) |
|---|---|---|---|
| Action opportunities surfaced by agents | Initiative emergence | Zero over 90 days in a governed domain | Three months in a governed domain without a single agent-surfaced opportunity is structural evidence that one of the three initiative conditions is not in fact met. |
| Accepted action opportunities (human-approved) | Initiative quality | <20% acceptance rate | Below 20%, agents are surfacing noise faster than they are surfacing value; the substrate is producing pattern matches without institutional relevance. |
| Time from regulatory change to substrate update | Institutional responsiveness | **>10 business days** for directly affected claims | Two business weeks is the upper bound at which downstream operational reviews triggered by the change can still complete before most reasonable effective dates; for shorter clocks (DORA major incident: 4h initial / 72h intermediate / 1 month final; AI Act Art. 73 serious incident: 2/15 days), the substrate-update window must be tightened proportionally. |
| Epistemic circuit breaker activations | System self-awareness | Zero (circuit breakers may not be wired) or rising (substrate degrading) | Zero is suspicious in any non-trivial substrate; a healthy enterprise sees breaker activations as a normal side effect of curation. A rising rate without rising activity indicates substrate degradation. |
| Governance relocation coverage (action classes with demonstrated control equivalence) | Enterprise maturity | <1 action class after 12 months of operation | Twelve months without a single relocated class indicates either substrate immaturity or unwillingness to invest in control-equivalence evidence; either way the *governance relocation* premise is not yet operational. |
| **Substrate diversity** — distinct organizational sources / total validated claims | Substrate-monoculture risk | Single source >80% of validated claims (see Failure mode: *Substrate capture*) | A monoculture substrate is a captured substrate: when one team, one vendor, or one business unit owns more than four in five validated claims, the graph can no longer be relied on as institutional truth. |
| **Expert consultation rate vs substrate query rate** | Expert-network health | Expert consultation declining while substrate queries rising at the same rate (see *Substrate monoculture*) | Healthy enterprises see both rise together as the agentic surface grows; a falling expert-consultation rate signals the substrate is replacing expert networks rather than augmenting them. |
| **Novel-problem escalation rate** | Resilience to graph gaps | Zero escalations for novel situations over 90 days in a domain with active operations | Real domains generate novel cases. Zero escalations means agents are forcing novelty into nearest-neighbour claims rather than flagging gap conditions — substrate-induced false confidence (see *Substrate monoculture*). |

---

## Adoption path

The agentic enterprise is not adopted wholesale. It is built domain by domain, action class by action class.

> **Timeline note.** The week and month ranges below are *illustrative ranges with deliberate overlap*. They are not a Gantt chart. Successive phases overlap by design: substrate work initiated in Phase 1 continues into Phase 2; agent connection in Phase 2 continues during the relocation work of Phase 3. The transitions are evidence-based, not date-based — a phase ends when its exit criterion is met, not when its calendar window closes. Treat the windows as planning anchors that may compress (in mature programmes) or extend (in domains with weak prior governance).

### Phase 1: Governed substrate for one domain (weeks 1-8)

Select a single domain with high operational risk and existing knowledge assets. In financial services: settlement operations, regulatory reporting, or compliance interpretation.

Extract claims from existing documentation. Tag with source, type, scope, epistemic tier, temporal validity. Assign governance authorities. Set decay schedules. Deploy the intelligence lifecycle for this domain.

At the end of Phase 1, you have: a governed domain graph for one domain. Agents are not yet connected. The investment is in substrate, not automation.

### Phase 2: First governed agents (weeks 9-16)

Connect one or two agents to the governed substrate. Restrict to advisory output — recommendations with reasoning chains, not autonomous action. Implement epistemic-tier-to-action thresholds: agents at this phase operate at medium-consequence level with human review on every recommendation.

Deploy composite state tracking. Implement epistemic response classes for this agent-domain pair.

At the end of Phase 2, you have: governed agents producing traceable recommendations on a governed substrate. Human accountability is operational. You can demonstrate an audit trail from agent recommendation to claim to source.

### Phase 3: Governance relocation for first action classes (~weeks 17–36, overlapping with Phase 2)

Identify low-risk, high-frequency action classes within the governed domain. Measure governance intervention rates and decision quality baselines. Where evidence supports control equivalence, begin shifting from synchronous pre-action checking to asynchronous verification for those specific action classes.

This is where the enterprise begins earning initiative — not by granting it, but by building the evidence that the substrate is deep enough and the governance is effective enough for specific action classes.

At the end of Phase 3, you have: demonstrated governance relocation for at least one action class, with measurable evidence of control equivalence. This is the proof point for expansion.

### Phase 4: Domain expansion (from ~month 9, often overlapping with late Phase 3)

Extend to additional domains. Each new domain follows Phases 1-3 with decreasing time as governance patterns transfer. Cross-domain linking begins to surface shared claims and reduce duplication.

Expected timeline: Domain 2 in 8-12 weeks. Domain 3+ in 6-10 weeks.

### Phase 5: Enterprise-scale initiative (12+ months)

Multiple governed domains. Agent portfolio managed through composite state tracking. Governance relocation demonstrated across multiple action classes. Agents surfacing action opportunities across domain boundaries.

This is the agentic enterprise — not as a big-bang transformation, but as a governed capability that was built domain by domain and earned through evidence.

---

## What this is not

This manifesto is not an operating model. It does not prescribe organizational structure, team composition, or project management methodology.

This manifesto is not a compliance framework. It provides governance architecture that regulated industries need, but compliance mapping is domain-specific work that belongs in companion documents.

This manifesto is not a technology specification. It is architecture-agnostic at the model level and implementation-flexible at the infrastructure level. The principles constrain what the architecture must achieve, not how it achieves it.

This manifesto is not a finished system. It is a governance architecture for a capability that is becoming possible. The engineering work to realize it — particularly building and maintaining governed domain graphs at enterprise scale — is substantial. The principles are stated now because the architectural decisions being made today — which substrates to build, which governance to embed, which agent freedoms to grant — will determine whether the agentic enterprise becomes real or remains marketing.

---

## Where this stands

The ideas in this manifesto draw from a five-paper programme on enterprise AI and organizational intelligence (Reichhart, 2025-2026, SSRN) and from open-source governance frameworks for agentic engineering, delivery, and product management (Gelas, 2025-2026, GitHub). This is a living document. The principles will evolve as implementations test them. We welcome critical engagement.

---

## Revision Log

| Version | Changes | Date |
|---|---|---|
| v0.1 | Initial draft | May 2026 |
| v0.2 | Cut DAO comparison. Rewrote governance relocation with control-equivalence model. Added worked example (regulatory change propagation). Added failure modes (7). Added metrics (3 categories, 16 signals). Added adoption path (5 phases). Grounded initiative with autonomy-vs-initiative example. Expanded P8 to consequence-class accountability. Expanded P12 to response classes by criticality. Compressed substrate principles with IGM prerequisite statement. Cut academic name-drops. | May 2026 |
| v0.3 (draft) | Internal-coherence pass: glossary additions (Harvest mode, action opportunity, epistemic quality, epistemic tier, temporal supersession, jurisdictional divergence, retrieval/reasoning/action governance, gap flag, scoped-view filtering rules); repo-wide rename of *confidence* → *epistemic tier* in scalar/substrate sense; phase-timeline arithmetic reframed as illustrative ranges with overlap; metric calibration note + per-threshold rationale; metrics expanded with three substrate-monoculture monitoring signals (revised count: 3 categories, 19 signals); decay class taxonomy enumerated in P10; "fail closed" operationalised per consequence class in P11; ingestion-trigger clarification in P6 worked example; governance-relocation evidence-framework reconciliation; rights-and-remedies subsection added to P8 (DRAFT — regulatory positioning). Companion guide: *Concurrent Lifecycle Sequencing* section, *Agent inventory & SaaS-embedded-agent governance* section. | May 2026 |
| v0.4 (draft) | AEM-coverage closure: added Part IV with four new principles — P13 *Economics of agentic governance* (cost-of-correctness, governance-cost-to-action-value ratio, multi-model coherence cost) wiring to AEM P11; P14 *Containment for multi-agent emergence* (substrate threat model — indirect prompt injection, cross-agent privilege escalation, tool-call poisoning, cascade emergence — with rate limits, kill-switch, cascade detection) extending AEM P10; P15 *Right-sized agent portfolios* (orchestrator tier-containment, single commit path, conflict-resolution patterns, agent-inventory minimum bar, shadow-agent block) implementing AEM P4; P16 *Architectural enforcement is assumed* (stub) declaring the dependency on AEM P3. Title updated from "Twelve" to "Sixteen" principles. Companion guide: tightened P5 (machine-readable retrieval/reasoning/action governance with JSON Schema artefacts, scoped-view computation rules, claim-tier minima per consequence class); tightened P7 (initiative-withdrawal procedure with timing and due process; governance-relocation reversal procedure with auto-revert triggers; dual-authority disagreement escalation; consequence-class tie-breaking order regulatory > reputational > client > financial); response-class operational rules (defaults, runtime override, retention, quarterly retrospective) added to P11 companion section. | May 2026 |

---

*Witold Reichhart and Arnaud Gelas, May 2026. Licensed under CC BY-SA 4.0.*

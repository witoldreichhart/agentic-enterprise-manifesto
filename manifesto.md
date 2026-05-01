# The Agentic Enterprise Manifesto

**Principles for governing AI agents at organizational scale.**

*Authors: **[Witold Reichhart](https://github.com/witoldreichhart) and [Arnaud Gelas](https://github.com/arnaudgelas)***
*Version: 0.2 — May 2026*

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

## Twelve principles

### Part I — The governed substrate

*The agentic enterprise depends on a governed intelligence substrate as specified in the [Intelligence Governance Manifesto](https://github.com/witoldreichhart/intelligence-governance-manifesto). The IGM defines claim-level governance, provenance, confidence, contradiction management, decay monitoring, and the intelligence lifecycle in detail. The four principles below specify what the enterprise layer requires of that substrate — not how it is built.*

**1. The domain graph is enterprise infrastructure, not an agent feature.**
The governed domain graph — the accumulated, validated, compounding substrate of institutional knowledge — sits between the foundation model and application context as shared infrastructure. Every agent in the enterprise reasons over it. No agent owns it. It is maintained through a governed lifecycle, enriched through operation, and decays under explicit management. The domain graph is to the agentic enterprise what the general ledger is to financial accounting: the single governed substrate that makes enterprise-level coordination possible.

**2. Intelligence is a system property, not a model property.**
Organizational intelligence is the capacity to perceive institutionally relevant patterns, infer their consequences, and select action opportunities under changing constraints. It emerges from the interaction between inferential capability (the model), governed knowledge (the substrate), and institutional constraints (the governance architecture). No single component produces it. Replacing the model does not destroy it. The substrate and constraints carry the institutional reasoning; the model provides the inferential engine.

**3. The substrate must support structured inquiry, not just retrieval.**
Enterprise agents do not just retrieve relevant documents. They operate over structured claims — assertions with provenance, confidence, temporal validity, scope, contradiction status, and governance status. Queries return not just matching claims but adjacent conflicts, confidence warnings, dependency chains, and gap flags. The substrate supports institutional reasoning because it surfaces what is contradicted, what is stale, what is missing, and what confidence to assign — not just what is textually relevant.

**4. The substrate deepens through use.**
Each engagement, each governance decision, each contradiction resolved enriches the shared substrate. The domain graph grows by generation — new connections, new validated claims, new cross-domain edges — through normal business operation. This compounding is the agentic enterprise's structural advantage. It is also its governance obligation: every enrichment must pass through the governed lifecycle. Ungoverned enrichment is substrate pollution.

### Part II — Enterprise agent governance

**5. Agents share a substrate; they do not share a mind.**
Each agent in the agentic enterprise accesses the domain graph through scoped views — receiving the subgraph relevant to its task and authorization level. Shared substrate does not mean shared context. Retrieval governance (what may an agent access?), reasoning governance (what inferences may it draw?), and action governance (what may it do?) operate as three distinct control layers. The enterprise controls what any agent can see, think, and do — independently.

**6. Initiative is earned through substrate depth; autonomy requires only capability.**
Autonomy requires capability — the agent can execute independently within assigned parameters. Initiative — the capacity to surface action opportunities aligned with institutional purpose before being asked — requires three additional conditions: a governed domain graph deep enough for the agent to perceive institutionally relevant patterns in its operating domain, a constraint architecture legible enough for the agent to reason about what actions are permissible, and governance relocation advanced enough that the agent encounters institutional constraints during normal reasoning rather than as external gates.

An enterprise that grants agents autonomy without building the substrate for initiative gets fast execution and zero perception. The three conditions are measurable (see Metrics below) and define the investment thesis for the agentic enterprise: build the substrate, earn the initiative.

*Example — autonomy vs. initiative:* An autonomous agent in settlement operations executes CSDR penalty calculations correctly when assigned. An agent with initiative — operating over a deep, governed substrate — notices that a pending UK regulatory change will create a jurisdictional divergence with current EU penalty methodology, identifies which cross-border settlement programmes are affected, and surfaces this as an action opportunity to the governance team before the change takes effect. The second agent was not assigned this task. It perceived the pattern because the substrate was deep enough to make it visible.

**7. Governance relocation is measured, not assumed.**
As the domain graph deepens for a specific action class, governance enforcement for that class can shift from synchronous pre-action constraint checking toward asynchronous verification and audit sampling. This shift is governance relocation — the enforcement locus migrating from external rules to substrate-resident causal structure.

Relocation is not an entitlement earned by maturity claims. It requires demonstrated control equivalence: evidence that the relocated governance achieves equal or better control outcomes than the synchronous check it replaces. The enterprise monitors three signals per action class:

- *Declining governance intervention rates with stable or improving decision quality* — indicates relocation is working.
- *Flat or rising intervention rates* — indicates insufficient substrate depth. Do not relocate.
- *Declining intervention rates with declining decision quality* — indicates weakening governance. Reverse the relocation.

Relocation operates per action class, not globally. It is reversible — if the substrate degrades for a given action class, governance re-tightens for that class. A regulator reviewing the control framework should see: which action classes have relocated governance, what evidence supports equivalent control outcomes, and what monitoring detects degradation.

**8. Human accountability is scoped by consequence class.**
The agentic enterprise assigns human accountability by the consequence level of the action, not per individual agent action.

- *Low consequence* (internal research, non-client-facing analysis) — human accountability at the workflow level. Named human owns the workflow. Individual actions are logged with audit trail.
- *Medium consequence* (client recommendations, internal reports) — human accountability at the decision level. Named human reviews the agent's reasoning chain and epistemic quality summary before the recommendation is delivered.
- *High consequence* (trade execution, regulatory filing, compliance determination) — human accountability at the action level. Named human reviews full reasoning chain with confidence levels, provenance, and contradiction flags before action proceeds.
- *Critical consequence* (cross-border regulatory submission, systemic risk assessment) — dual human accountability. Two-person review with escalation to governance authority.

In regulated environments, "the agent decided" is never an acceptable escalation path. Agents execute. Humans are accountable. This is not a transitional arrangement pending better AI — it is a design principle. The accountability assignment, the authority scope, and the reasoning chain from agent recommendation through human decision to executed action are recorded for every action above the low-consequence threshold.

### Part III — Enterprise operations

**9. Composite state is enterprise state.**
An agent product's behavioral identity is determined by five components simultaneously: application code, system prompt, foundation model, knowledge base, and memory state. When any component changes — including a model update the engineering team did not initiate — the composite state changes and the agent's behavior may change with it. At enterprise scale, this means foundation model updates propagate across every agent in the system simultaneously.

The enterprise must detect, evaluate, and explicitly accept or reject composite state changes across its entire agent portfolio. The default is reject. Accepted changes are logged with the accepting authority. Undetected composite state drift is the enterprise equivalent of a silent configuration change in production — the system is no longer what you tested.

**10. Decay is managed, not prevented.**
Knowledge decays. Regulatory interpretations shift. Operational workarounds expire. Market conditions change. The agentic enterprise does not pretend its substrate is permanent. It manages decay explicitly — different decay rates for different knowledge types, different maintenance cadences per decay class, continuous monitoring for staleness, fragmentation, and drift. An enterprise substrate that is large but stale is worse than one that is small but current, because agents reason over it with unwarranted confidence.

**11. The enterprise responds by criticality, not by reflex.**
When epistemic confidence falls below threshold — stale claims on a critical path, unresolved contradictions in a reasoning chain, scope mismatches between claim and use context — the system responds according to the consequence class of the action:

- *Block* — halt the action entirely. Agent produces a structured escalation identifying the epistemic defect and what is blocked pending resolution.
- *Escalate* — route to human decision-maker with full epistemic quality summary.
- *Restrict scope* — narrow the agent's action space to what the current epistemic quality supports.
- *Advisory only* — agent produces recommendation flagged as low-confidence, with no execution authority.
- *Continue with enhanced monitoring* — action proceeds but triggers enhanced logging, audit sampling, and post-action review.

The response class is set per action class and consequence level, not globally. "Fail closed" is the default for high-consequence actions. Lower-consequence actions may degrade gracefully. The system never silently continues at full confidence when epistemic quality is insufficient.

**12. Three lifecycles intersect; initiative emerges at the intersection.**
The agentic enterprise operates through three concurrent governance cycles:

The *intelligence lifecycle* (weeks to months) — Ingest, Consolidate, Curate, Expand, Apply — maintains the shared substrate. This is the heartbeat of the agentic enterprise. Without it, the domain graph fossilizes.

The *agent lifecycle* (days to weeks) — conception, specification, build, evaluation, release, operation, maintenance, retirement through the APLC. At enterprise scale: managing an agent portfolio, tracking composite state, detecting drift, maintaining behavioral baselines.

The *delivery lifecycle* (hours to days) — agent-built software delivered through the ASDLC with evidence bundles, specification readiness gates, and operational handoffs.

These timescales are typical ranges, not definitional. Intelligence may change daily in fast-moving regulatory domains. Delivery may take weeks in legacy integration contexts. What matters is that three concurrent cycles operate at different speeds and their intersection is where enterprise behavior emerges.

Initiative does not live in any single lifecycle. It emerges when the intelligence substrate is deep enough, the agent portfolio is governed tightly enough, and the delivery pipeline is traceable enough for the enterprise to trust agents that surface action opportunities before being asked. The agentic enterprise does not program initiative. It builds the conditions from which initiative can emerge — and measures when those conditions are met.

---

## Worked example: regulatory change propagation

A new ESMA guideline amends the penalty calculation methodology for settlement fails under CSDR. This is how the agentic enterprise processes it.

**Intelligence lifecycle responds.** The regulatory claim enters through governed ingestion (Harvest mode — automated monitoring of ESMA publications). The Consolidate stage extracts specific claims: the amended calculation formula, the effective date, the jurisdictional scope. It detects a contradiction with the existing EU penalty methodology claim and a jurisdictional divergence with the UK CREST regime (which has not changed). Both contradictions are typed and preserved — the EU claim is temporal supersession, the UK divergence remains jurisdictional.

**The substrate updates.** The old EU penalty claim is demoted (not deleted — supersession chain maintained). The new claim enters at Candidate confidence. A domain expert validates it against the ESMA source text and promotes it to Confirmed. The Expand stage identifies downstream claims that depend on the old penalty methodology — collateral management calculations, client reporting templates, cross-border settlement programme configurations — and flags them for revalidation.

**An agent with initiative surfaces the action opportunity.** A settlement operations agent, reasoning over the updated substrate, perceives that three cross-border settlement programmes reference the superseded methodology. It surfaces this as an action opportunity to the governance team: "These programmes require configuration review before the effective date. The UK programmes are unaffected — the jurisdictional divergence means both regimes are valid within their scope."

The agent was not assigned this task. It perceived the pattern because the substrate was deep enough and the contradiction structure made the impact visible.

**Human accountability engages.** The governance team reviews the agent's reasoning chain: which claims informed the recommendation, their confidence levels, the provenance chain from ESMA publication through extraction to the current substrate state, the typed contradictions. This is a medium-consequence action (client impact, no direct regulatory filing). A named human approves the configuration review.

**The delivery lifecycle executes.** Agent-built configuration changes enter the ASDLC. Evidence bundles trace from the code change to the claims that justified it, to the human approval that authorized it, to the regulatory source that triggered it. Composite state changes are recorded for every affected agent product.

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

### Substrate health

| Metric | Indicates | Warning signal |
|---|---|---|
| Claim freshness (% within revalidation window) | Substrate currency | <80% |
| Provenance completeness (% with full chain) | Audit readiness | <90% |
| Contradiction density (active contradictions / total claims) | Substrate tension — too low suggests suppression, too high suggests curation failure | <1% or >15% |
| Unresolved critical contradictions | Governance backlog | Rising trend |
| Cross-domain edge density | Substrate connectivity | Declining or flat |
| Claim reuse rate (claims consumed by multiple agents) | Substrate utility | <30% |

### Governance effectiveness

| Metric | Indicates | Warning signal |
|---|---|---|
| Governance intervention rate per action class | Relocation readiness | Flat (no relocation) or declining without quality evidence |
| Decision quality post-action (audit sample) | Governance outcome | Declining in any action class |
| Human override rate | Governance calibration | >20% (agents miscalibrated) or <1% (rubber-stamping) |
| Audit reconstruction time (source → action) | Traceability | >4 hours for any action class |
| Composite state change detection rate | Portfolio integrity | <100% of known model updates |

### Enterprise capability

| Metric | Indicates | Warning signal |
|---|---|---|
| Action opportunities surfaced by agents | Initiative emergence | Zero over 90 days in a governed domain |
| Accepted action opportunities (human-approved) | Initiative quality | <20% acceptance rate |
| Time from regulatory change to substrate update | Institutional responsiveness | >10 business days for directly affected claims |
| Epistemic circuit breaker activations | System self-awareness | Zero (circuit breakers may not be wired) or rising (substrate degrading) |
| Governance relocation coverage (action classes with demonstrated control equivalence) | Enterprise maturity | <1 action class after 12 months of operation |

---

## Adoption path

The agentic enterprise is not adopted wholesale. It is built domain by domain, action class by action class.

### Phase 1: Governed substrate for one domain (weeks 1-8)

Select a single domain with high operational risk and existing knowledge assets. In financial services: settlement operations, regulatory reporting, or compliance interpretation.

Extract claims from existing documentation. Tag with source, type, scope, confidence, temporal validity. Assign governance authorities. Set decay schedules. Deploy the intelligence lifecycle for this domain.

At the end of Phase 1, you have: a governed domain graph for one domain. Agents are not yet connected. The investment is in substrate, not automation.

### Phase 2: First governed agents (weeks 9-16)

Connect one or two agents to the governed substrate. Restrict to advisory output — recommendations with reasoning chains, not autonomous action. Implement confidence-to-action thresholds: agents at this phase operate at medium-consequence level with human review on every recommendation.

Deploy composite state tracking. Implement epistemic response classes for this agent-domain pair.

At the end of Phase 2, you have: governed agents producing traceable recommendations on a governed substrate. Human accountability is operational. You can demonstrate an audit trail from agent recommendation to claim to source.

### Phase 3: Governance relocation for first action classes (months 5-9)

Identify low-risk, high-frequency action classes within the governed domain. Measure governance intervention rates and decision quality baselines. Where evidence supports control equivalence, begin shifting from synchronous pre-action checking to asynchronous verification for those specific action classes.

This is where the enterprise begins earning initiative — not by granting it, but by building the evidence that the substrate is deep enough and the governance is effective enough for specific action classes.

At the end of Phase 3, you have: demonstrated governance relocation for at least one action class, with measurable evidence of control equivalence. This is the proof point for expansion.

### Phase 4: Domain expansion (months 10+)

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
| v0.2 | Cut DAO comparison. Rewrote governance relocation with control-equivalence model. Added worked example (regulatory change propagation). Added failure modes (7). Added metrics (3 categories, 17 signals). Added adoption path (5 phases). Grounded initiative with autonomy-vs-initiative example. Expanded P8 to consequence-class accountability. Expanded P12 to response classes by criticality. Compressed substrate principles with IGM prerequisite statement. Cut academic name-drops. | May 2026 |

---

*Witold Reichhart and Arnaud Gelas, May 2026. Licensed under CC BY-SA 4.0.*

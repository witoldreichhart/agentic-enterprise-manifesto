# Agentic Enterprise Manifesto — Companion Guide

**Witold Reichhart and Arnaud Gelas**

This guide provides operational detail for the concepts introduced in the manifesto. It covers the initiative conditions, governance relocation mechanics, consequence classes, enterprise lifecycle interactions, and boundary conditions.

---

## Initiative: The Three Conditions

The manifesto states that initiative requires three conditions beyond capability. This section defines each operationally.

### Condition 1: Substrate depth

The governed domain graph must be deep enough in the agent's operating domain for the agent to perceive institutionally relevant patterns — not just retrieve relevant claims, but detect connections, contradictions, and gaps that have operational significance.

**What "deep enough" means in practice:**

Substrate depth is not a single threshold. It is a composite of coverage, connectivity, and currency for a specific domain.

*Coverage* — the domain graph contains claims across the major knowledge types relevant to the domain: regulatory rules, operational procedures, cross-domain dependencies, vendor configurations, known exceptions, and historical workarounds. Gaps are identified and tracked, not hidden.

*Connectivity* — claims are linked through causal, temporal, and scope relationships. Cross-domain edges exist where domains interact. Entity resolution is complete. The graph is traversable, not just searchable.

*Currency* — claims are within their revalidation windows. Decay monitoring is active. Stale claims are flagged or excluded from agent reasoning. The substrate reflects operational reality as of the current maintenance cycle.

**Measurable proxies:** Claim coverage per domain subdomain (>80% of identified knowledge types). Cross-domain edge density (rising trend). Claim freshness (>90% within revalidation window). Contradiction detection active with typed conflicts.

An agent operating over a substrate that meets these thresholds can perceive patterns. An agent operating over a substrate that falls short can execute assigned tasks but will not surface what it cannot see.

### Condition 2: Constraint legibility

The agent must be able to reason about what actions are permissible within its operating context — not through a list of rules checked sequentially, but through a constraint architecture that is legible to the agent's reasoning process.

**What "legible" means in practice:**

The agent can determine, for a proposed action: which organizational policies apply, what consequence class the action falls into, what minimum *epistemic tier* is required for load-bearing claims, what governance authority must approve, and what the downstream obligations are.

This requires that institutional constraints — policies, risk appetites, regulatory boundaries, authority structures — are represented in a form the agent can reason over, not buried in policy documents that a human would need to interpret.

**Measurable proxies:** Percentage of action classes with machine-readable constraint definitions. Agent self-classification accuracy on consequence class (validated against human classification). Policy coverage — percentage of relevant policies represented in the constraint architecture.

### Condition 3: Governance relocation

Governance enforcement for the agent's action classes must have migrated sufficiently from synchronous pre-action gating toward substrate-resident structure and asynchronous verification — with demonstrated control equivalence.

**What "sufficient relocation" means in practice:**

For at least one action class in the agent's domain, the enterprise has evidence that:
- The synchronous check has been replaced by an equivalent control mechanism
- The agent encounters the relevant constraints during normal reasoning over the substrate
- Decision quality has remained stable or improved after the shift
- Monitoring detects any degradation and can reverse the relocation

An agent operating in a domain where all governance is still synchronous pre-action gating can execute tasks but cannot take initiative — because initiative requires the agent to reason about action opportunities during normal operation, not only when explicitly asked through a gated workflow.

### When all three conditions are met

The enterprise has earned the right to let agents take initiative in that specific domain and for those specific action classes. Not globally. Not permanently. The conditions are continuously monitored. If any condition degrades — substrate goes stale, constraint architecture becomes incomplete, governance relocation evidence weakens — initiative authority is withdrawn for the affected scope.

---

## Principle 5 — Retrieval, Reasoning, and Action Governance: Operational Specification

The manifesto names retrieval governance, reasoning governance, and action governance as three distinct control layers. This section gives each one a scope, an artefact set, an owner, an integration point with the substrate, and a failure-detection signal. The intent is to make it possible for an implementer (and an auditor) to verify that all three layers exist and are wired correctly — not just that the words appear.

### The three layers

| Layer | Scope | What it governs |
|---|---|---|
| **Retrieval governance** | What may an agent *see*? | Which sub-graphs, which claim tiers, which provenance classes the agent's scoped view returns for a given task and authorisation. |
| **Reasoning governance** | What inferences may the agent *draw*? | What chains of inference are admissible (e.g., "no inference from a Provisional claim to a High-consequence action"), what minimum *epistemic tier* a load-bearing claim must hold, and how contradictions must be handled in the reasoning chain. |
| **Action governance** | What may the agent *do*? | Which action classes the agent is authorised to execute, the response class on epistemic failure, and the per-action evidence required at the action boundary. |

Each layer is independent — an agent may pass retrieval governance, fail reasoning governance, and never reach action governance. Compromise of any one layer is sufficient to block the action. This is the "see, think, do" minimum bar for AEnt-M Principle 5.

### Required artefacts

Each layer is operationalised by a **machine-readable constraint document**, not by prose. AEnt-M's reference format is **JSON Schema** (or any equivalent strongly-typed schema language with a published validator). The intent is that the constraint is enforceable at the substrate access layer, the reasoning chain validator, and the action boundary — not interpreted by humans on demand.

**Retrieval-governance schema** — describes:

- *Scoped-view filter rules.* Predicates over claim metadata (domain, sub-domain, tier, provenance class, jurisdiction, decay class) that produce the sub-graph the agent's task is allowed to retrieve.
- *Role-based access controls.* Mapping from the agent's identity and the action's consequence class to which scoped-view filter rules apply.
- *Claim-tier minima per consequence class.* The minimum *epistemic tier* a load-bearing claim must hold to be admissible into a scoped view used by an action of a given consequence class.
- *Provenance constraints.* Which provenance classes (e.g., regulator, vendor doc, internal SME, harvested-public) are admissible per consequence class.

**Reasoning-governance schema** — describes:

- *Admissible inference patterns* per consequence class (e.g., chain-of-claims with all load-bearing claims at Confirmed+; or "two corroborating sources from independent provenance classes for High-consequence inferences").
- *Contradiction-handling rules* — when an active contradiction is encountered in the reasoning chain, the response (preserve, escalate, block) per consequence class.
- *Minimum-epistemic-tier requirements* on each load-bearing claim.
- *Stop conditions* — the conditions under which the reasoning chain must halt (e.g., scope mismatch, claim demoted mid-reasoning, decay-window breach).

**Action-governance schema** — describes:

- *Action-class catalogue* — every action class the agent can attempt, with consequence-class assignment.
- *Response-class default* per action class (Block / Escalate / Restrict / Advisory / Continue-with-monitoring), per Principle 11.
- *Required evidence* at the action boundary (reasoning chain, epistemic-quality summary, named human approval if applicable, composite-state hash).
- *Authority binding* — for each action class, the named accountable human (per consequence class) and the override authority.

The three schemas live together as a versioned **constraint architecture** for the agent. Changes to any of them go through the same governance workflow as substrate changes (decay-class taxonomy applies; see manifesto P10). The constraint architecture is part of the agent's evidence bundle at every release.

### Maintenance owners

| Layer | Owner | Cadence |
|---|---|---|
| Retrieval governance | **Workflow Owner + Domain steward** (jointly; Workflow Owner for which agents/tasks; Domain steward for the substrate predicates) | Reviewed at every domain change; mandatory annual review. |
| Reasoning governance | **Inference Authority** (per IGM) | Reviewed at every claim-tier policy change or contradiction-handling rule change; mandatory annual review. |
| Action governance | **Accountable Authority for the highest consequence class served** | Reviewed at every action-class addition, every consequence-class reassignment, every response-class default change; mandatory quarterly review for High and Critical action classes. |

Ownership is named in the agent inventory entry. An agent without explicit owners for all three layers is, by AEnt-M's minimum bar, ungoverned and may not serve traffic.

### Integration with the substrate

All three layers integrate with the IGM substrate as follows:

- **Retrieval governance** is enforced at the substrate access boundary by a **scoped-view computation engine** that takes (agent identity, task, consequence class, action class) as input and returns a sub-graph that satisfies the retrieval-governance schema. The engine is part of the substrate, not part of any agent.
- **Reasoning governance** is enforced by a **reasoning-chain validator** that runs over the agent's reasoning chain before any action is admitted to the action boundary. The validator consumes the reasoning-governance schema and the chain's claim references; rejection at this stage produces a structured escalation, not a silent fall-through.
- **Action governance** is enforced at the **action boundary** (the deterministic policy enforcement point declared in AEM Principle 3 / AEnt-M Principle 16). Every action attempt produces an evidence bundle entry whether the action proceeds, is blocked, or is escalated.

### Failure detection per layer

Each layer's failure mode is monitored independently:

- *Retrieval governance failure* — an agent's scoped view returns claims the action-class consequence class disallows (wrong tier, wrong jurisdiction, decayed). Signal: scoped-view audit sampling with a target false-admission rate of zero.
- *Reasoning governance failure* — a reasoning chain admitted into the action boundary that violates the reasoning schema (load-bearing claim below tier minimum, unhandled contradiction, scope mismatch). Signal: validator-reject rate at the action boundary plus retrospective audit of admitted chains.
- *Action governance failure* — an action executed without complete evidence-bundle entry, or executed at a consequence class above the agent's authorisation, or against a response-class default the action class did not honour. Signal: action-boundary audit reconstruction rate (target: 100% within audit-reconstruction SLO from Principle 11 metrics).

Any one of these signals trending upward is a Principle 5 control-gap event and is routed to the relevant authority above.

### Scoped-view computation rules

The substrate's scoped-view computation engine is the single mechanism that enforces retrieval governance. Its rules are normative:

1. **Filter by task scope first.** The agent's task carries a *task scope* — a declared sub-domain, jurisdiction, time window, and entity set. Claims outside this scope are excluded before any tier or RBAC filter applies.
2. **Apply role-based access controls.** The agent's identity and the action's consequence class map (per the retrieval-governance schema) to a set of admissible claim provenance classes and tiers. Anything outside this map is excluded.
3. **Enforce claim-tier minima per consequence class.** A claim below the consequence class's minimum *epistemic tier* is excluded from the scoped view. The minima are normative; the defaults are illustrative:

| Consequence class | Minimum *epistemic tier* for load-bearing claims (default; tunable per domain) |
|---|---|
| Low | *Provisional* or higher |
| Medium | *Supported* or higher |
| High | *Confirmed* or higher |
| Critical | *Confirmed* with at least one validation event against an observable reality not used as a corroborating source (cross-reference IGM Principle 13 — *Claims must be validatable, not only corroborated*). |

4. **Surface contradictions and gaps.** A scoped view returns not just admissible claims but also (a) any active contradictions involving those claims, (b) any gap flags in the requested scope, and (c) the decay status of each claim returned. The agent cannot suppress these — they are part of the view contract.
5. **Audit every view.** Every scoped-view computation produces a row in the substrate access log with (agent ID, task ID, action class, consequence class, filter rules applied, claims admitted, claims excluded by tier, claims excluded by RBAC, contradictions surfaced, gaps surfaced). The log is the input to retrieval-governance failure detection.

The computation engine is owned by the Workflow Owner + Domain steward jointly. Its rules are versioned in `governance/composition-rule.md` (DRAFT — author review needed); any change goes through the constraint-architecture workflow.

---

## Governance Relocation: Operational Mechanics

Governance relocation is the mechanism most likely to be challenged by regulators and governance professionals. This section provides the operational detail behind Principle 7.

### What relocates

Governance relocation does not mean governance disappears. It means the enforcement mechanism changes. What was enforced through an explicit pre-action gate is now enforced through the substrate's own causal structure — and verified through monitoring and audit sampling rather than synchronous checking.

Specifically, what relocates is the *control point* — where the governance check happens:

| Before relocation | After relocation |
|---|---|
| Agent proposes action → explicit rule check → approve/deny → execute | Agent reasons over substrate (encounters constraints during reasoning) → executes → asynchronous verification confirms control objective met |

The *control objective* does not change. Only the enforcement mechanism changes.

### Control equivalence

Relocation requires evidence that the new mechanism achieves equivalent or better control outcomes than the old one. Control equivalence is assessed per action class, not globally.

Evidence categories:

*Decision quality comparison* — for a defined sample period, compare decision outcomes under synchronous checking vs. substrate-resident governance. Quality must be stable or improved.

*Error detection rate* — the asynchronous verification and audit sampling must detect errors at a rate comparable to or better than the synchronous check.

*Response time to degradation* — when the substrate degrades for an action class, how quickly does the monitoring detect it and how quickly is synchronous checking reinstated?

*Audit reconstructability* — the reasoning chain from action to substrate to constraint must remain fully traceable under the relocated governance model.

### Relocation is gradual, not binary

Relocation for an action class typically progresses through stages:

1. **Full synchronous** — every action is pre-checked against explicit constraints
2. **Parallel run** — synchronous check remains active, substrate-resident governance runs alongside, discrepancies are logged and analyzed
3. **Monitored relocation** — synchronous check is removed for routine instances, retained for edge cases, full audit sampling active
4. **Operational relocation** — substrate-resident governance is the primary mechanism, asynchronous verification at defined sampling rates, synchronous check available for re-engagement

Each transition requires evidence from the previous stage. Regression at any stage triggers rollback to the previous stage for the affected action class.

---

## Principle 7 — Procedures with Timing and Due Process

The manifesto's Principle 7 names initiative withdrawal, governance-relocation reversal, dual-authority disagreement, and consequence-class tie-breaking, but does not specify how each is operationally executed. This section is normative; the timing and authority assignments are illustrative for FS at scale and may be tuned per domain, but the procedure shape — trigger, decision authority, notice, transition, appeal — is required.

### (a) Initiative-withdrawal procedure

Initiative may be withdrawn from an agent + scope when any of the three initiative conditions (substrate depth, constraint legibility, governance relocation) degrades, or when a sustained deviation in initiative-quality metrics is observed. Withdrawal is *not* an incident response — it is a controlled reversion of authority.

| Step | Trigger | Decision authority | Timing |
|---|---|---|---|
| **1. Trigger detection** | Substrate metric falls below the Condition-1 threshold (coverage <80%, currency <90%, contradiction detection inactive); constraint-architecture coverage drops; control-equivalence evidence weakens; sustained negative initiative-quality signal (acceptance rate <20% over 30 days, or audit-detected mis-classification rate >5%). | Domain steward (substrate), Inference Authority (constraint-architecture), Accountable Authority (initiative-quality). | Continuous monitoring. |
| **2. Notice** | Detected trigger crosses threshold. | Authority that detected the trigger issues a written *withdrawal notice* to the Workflow Owner, the agent's Accountable Authority, and the enterprise governance authority. | **Within 1 business day** of trigger crossing. |
| **3. Decision** | Notice issued. | Enterprise governance authority decides: confirm withdrawal, defer with mitigation plan, or reject. Default-on-silence is *confirm withdrawal* — no decision within the SLO is treated as confirmation. | **Within 5 business days** of notice (1 business day for High/Critical action classes). |
| **4. Transition plan** | Withdrawal confirmed. | Workflow Owner authors a transition plan: which action classes revert to assigned-task-only, which remain authorised, what synchronous gates re-engage, and how in-flight work completes. The plan is reviewed by the Accountable Authority and recorded in the agent inventory. | **Within 5 business days** of decision. |
| **5. Effect** | Transition plan accepted. | Initiative authorisation in the agent inventory flips to *withdrawn* for the affected scope. The substrate access engine and constraint architecture re-engage the synchronous gates. Affected stakeholders are notified through the standard governance-change channel. | Effective at plan acceptance; cutover scheduled within the next operational window. |
| **6. Appeal** | Workflow Owner believes withdrawal was unjustified. | Workflow Owner submits an appeal to the enterprise governance authority with countering evidence (substrate metrics, control-equivalence data, decision-quality samples). Appeal is heard at the next governance cadence, or earlier on Critical class. | **Within 10 business days** of effect. Appeal does not pause withdrawal — initiative remains withdrawn until the appeal is decided. |

A withdrawn agent retains its autonomy authorisation; it cannot surface action opportunities until reinstatement, which follows the original Initiative Authorization Gate (per APLC).

### (b) Governance-relocation reversal procedure

Governance relocation is reversible by design (manifesto P7). This procedure specifies *when* it must be reversed and *who* decides.

**Automatic-revert triggers** (no human decision required; the reversal is executed by the governance system and notified to authorities):

- **Decision-quality regression** — measured decision quality on the relocated action class drops below baseline by more than the per-class tolerance (illustrative: 5 percentage points sustained over 14 days).
- **Audit-reconstruction failure** — audit reconstruction time exceeds the per-class SLO for any action in the class (>4 hours for High/Critical; >24 hours for Medium; per Principle 11 metrics).
- **Substrate degradation** — any of the three initiative conditions (substrate depth, constraint legibility, control equivalence) drops below threshold for the action class.
- **Containment incident** — a Principle 14 cascade-detection or kill-switch event implicates the relocated action class.

**Discretionary reversal** — outside automatic triggers, reversal may be requested by:

| Requester | Evidence required | Decision authority | Timing |
|---|---|---|---|
| Domain steward | Substrate-health evidence (coverage, connectivity, currency) | Inference Authority + Accountable Authority (joint) | Within 5 business days |
| Accountable Authority | Decision-quality sample, intervention-rate trend, or risk-appetite change | Enterprise governance authority | Within 5 business days; 1 business day for High/Critical |
| Workflow Owner | Operational-friction evidence (governance-cost-to-action-value ratio rising; see Principle 13) | Accountable Authority | Within 5 business days |
| Enterprise governance authority | Any | Self | Effective immediately upon decision |

Reversal cuts the action class back to the previous stage of the four-stage progression (Operational → Monitored → Parallel-run → Full-synchronous). It is not a one-step jump to full synchronous unless an automatic-revert trigger or governance authority explicitly requires it.

The reversal is recorded in the evidence bundle and the agent inventory, with the trigger, the evidence, the deciding authority, and the date. *Reversal carries no penalty against the original relocation decision.* Reversibility is the design intent, not a failure.

### (c) Dual-authority disagreement procedure

Dual authority (Critical-consequence class, manifesto P8) requires two named humans to approve. When they disagree, the disagreement is itself a governance event:

| Step | Action | Timing |
|---|---|---|
| **1. Pause.** | The action remains *blocked* — dual-authority disagreement is never resolved by majority of one. | Immediate. |
| **2. Capture.** | Each authority records a written rationale (decision, supporting evidence, disagreement basis) in the evidence bundle. | Within 1 business day of disagreement. |
| **3. Escalate.** | The disagreement is escalated to the **enterprise governance authority** (single, named, with binding-decision authority for the domain). The escalation includes both rationales and any operational time-pressure context. | Within 1 business day of capture. |
| **4. Bind.** | The enterprise governance authority issues a **binding decision** — proceed, block, restrict scope, or defer with mitigation. The decision is recorded in the evidence bundle and in the dual-authority disagreement log. | Within 5 business days of escalation; **within 4 hours** for time-pressured Critical actions where the operational SLO requires it. |
| **5. Review.** | All dual-authority disagreements are reviewed at the next quarterly governance cadence. Patterns (the same disagreement recurring; one authority being routinely overruled) trigger structural review of authority assignment, training, or class definition. | Quarterly. |

The enterprise governance authority's decision is binding for that action; it does not retroactively re-classify the consequence class or the response class. Where a binding decision is made under time pressure, it is reviewed at the next cadence and may be reaffirmed, narrowed, or revised.

### (d) Consequence-class tie-breaking order

When an action's classification is contested across the four factors of Principle 8 (financial, regulatory, client, reputational), the manifesto says the *highest factor wins*. This procedure specifies the tie-break when two or more factors are equally high (or when the deciding authority has a partial assessment per factor):

**Priority order (binding):**

1. **Regulatory** — any factor that triggers a regulatory obligation (notification, filing, prior approval) or could cause supervisory scrutiny is paramount.
2. **Reputational** — visible-and-damaging exposure outranks client-private and pure-financial exposure when regulatory is matched.
3. **Client** — direct client outcome, data, or relationship impact outranks pure financial exposure.
4. **Financial** — pure financial exposure is the lowest-priority tie-breaker. (This does *not* mean "small-money actions are unimportant" — it means that when two factors are equal, financial is decided last.)

**Use of the order.** When two factors agree on the consequence class, the higher-priority factor is recorded as the *driving factor* in the action-class assignment. When the factors disagree (e.g., the regulatory assessment says High, the reputational assessment says Medium), the highest single factor wins per the manifesto rule, and the priority order applies only when factors are tied at the same level.

The driving factor is recorded in the agent inventory entry for the action class; it is the basis for downstream procedures (e.g., choice of dual authority, choice of response-class default, evidence-bundle requirements). Reclassifications must record *which factor changed*, not just *that the class changed*.

---

## Consequence Classes: Detailed Specification

The manifesto defines four consequence classes. This section provides implementation guidance.

### Determining consequence class

Consequence class is determined by the estimated institutional impact of an incorrect action. Four factors:

*Financial exposure* — the monetary impact of the action being wrong. From negligible (internal research) to systemic (cross-border regulatory filing).

*Regulatory risk* — whether the action falls within a regulated domain and whether an error could trigger supervisory scrutiny, enforcement action, or reporting obligations.

*Client impact* — whether the action affects client outcomes, client data, or client relationships.

*Reputational exposure* — whether the action, if wrong, would be visible externally and damaging to institutional reputation.

The highest factor determines the class. A low-financial, high-regulatory action is classified at the regulatory risk level, not the financial level.

### Class assignment

Consequence classes are assigned per action class, not per individual action. An action class is a category of agent action with similar risk characteristics: "generate client settlement report," "flag potential compliance breach," "recommend portfolio rebalancing," "execute trade."

Assignment is a governance decision made by the relevant authority and reviewed periodically. Action classes can be reclassified as the enterprise's understanding of risk evolves.

### Accountability model by class

| Class | Named human | Review requirement | Evidence | Response on epistemic failure |
|---|---|---|---|---|
| Low (carve-out — see [`/integration/low-consequence-resolution.md`](../integration/low-consequence-resolution.md)) | Workflow owner | Post-hoc audit sampling at ≥1% or ≥30 actions / workflow / month, whichever is larger | Continuous action log with reasoning chain, claims cited, workflow tag, retained ≥90d | Continue with enhanced monitoring |
| Medium | Decision reviewer | Pre-delivery review of reasoning chain and epistemic quality | Signed review with timestamp | Escalate to human decision-maker |
| High | Accountable authority | Full pre-action review of reasoning chain, epistemic tiers, provenance, contradictions | Signed review with authority scope confirmation | Block. Structured escalation. |
| Critical | Dual authority | Two-person pre-action review with governance authority escalation | Dual-signed review with escalation record | Block. Dual review. Governance authority notification. |

> **Low is the only class outside the AEM-governed envelope.** Qualification requires all seven carve-out criteria stated in [`/integration/low-consequence-resolution.md`](../integration/low-consequence-resolution.md) §3.1: no client impact, no regulatory exposure, no irreversibility, no PII processing, no financial exposure, no safety implications, no precedent-creation. Defaulting to Low without those criteria demonstrably true is a governance failure, not a tier election. Medium / High / Critical are inside the AEM-governed envelope and require AEM P12 per-action accountability.

---

## Principle 11 — Response-Class Operational Rules

The manifesto lists five response classes (Block / Escalate / Restrict-Scope / Advisory-Only / Continue-with-Enhanced-Monitoring) but does not specify how the defaults are set, who can override at runtime, what is logged, or how the override pattern is reviewed. Response-class defaults are the single most-likely point of silent miscalibration in the system; the rules below are normative.

The mapping from contradiction encounters to response classes is the canonical decision tree in [`/integration/contradiction-handling-decision-tree.md`](../integration/contradiction-handling-decision-tree.md). Inputs: contradiction type (per IGM P4 — `logical_contradiction`, `jurisdictional_divergence`, `temporal_supersession`, `scope_variation`, `extraction_error`), consequence class (per AEnt-M P8), and the highest epistemic tier on either side of the contradiction (per the IGM tier system). Output: response class. The tree is encoded as a machine-readable rule set referenced from the AEnt-M Reasoning-governance schema (P5) and from the runtime monitoring telemetry; every action that encounters a contradiction logs the rule that fired, the response class issued, and the resolution. The tree reconciles IGM Value 3 (preserve contradictions) with this Principle's "Block on unresolved contradiction" framing: IGM preserves; the tree determines what the agent does with what is preserved.

### Setting defaults

Response-class defaults per (action class × consequence class) are set **at enterprise governance setup** — before the action class serves traffic. Defaults are owned by the **enterprise governance authority** in consultation with the Accountable Authority for the highest consequence class served. Defaults are recorded in the action-governance schema (Principle 5) and in the agent inventory entry.

Defaults are **reviewed quarterly** at the enterprise governance cadence. Quarterly review considers:

- Override-rate trend per (action class × consequence class).
- Decision-quality outcomes correlated with the response class chosen.
- Incident analysis — every action-class incident is checked for whether the response-class default would have prevented or mitigated it.
- Regulatory or risk-appetite changes that may shift the appropriate default.

Default changes follow the constraint-architecture workflow: written proposal, evidence, deciding authority recorded, change reflected in the action-governance schema, version-bumped, and propagated to the substrate access layer.

### Runtime override

A response-class default may be overridden at runtime by a **named accountable human** — the named accountability for the action's consequence class (Workflow Owner / Decision Reviewer / Accountable Authority / Dual Authority per Principle 8). Overrides are not anonymous and are not delegable to an agent. The substrate's action boundary refuses any override attempt that does not carry a valid named-human signature with current authority for the consequence class.

**What can be overridden:** the response *direction* (a Block default may be overridden to Escalate; a Restrict-Scope default may be overridden to Advisory-Only) within the bounds of the consequence class. An override may *not* relax a Critical action below dual-authority escalation, and may *not* admit an action below the consequence class's minimum *epistemic tier* without a documented exception.

**Required artefacts at override time:**

- The override action class, the original default, and the chosen response.
- The named human, role, and authority basis for the override.
- A written *rationale* — free-text, not a check-box. Rationale must address why the default's underlying risk consideration does not apply or is mitigated.
- A reference to any compensating control (e.g., enhanced monitoring activated, post-action review scheduled, additional human reviewer consulted).

The override is logged as an evidence-bundle entry on the action and in a dedicated **override log** for the action class.

### Retention

Override-log retention follows the longest of:

- Regulatory minimum for the action class's domain (e.g., DORA, MiFID II, GDPR).
- The substrate's audit-reconstruction window for the consequence class (per Principle 11 metrics).
- **Seven years** as the AEnt-M default for High and Critical action classes; **three years** for Medium; **one year** for Low (illustrative; overridden upward by regulatory minimum).

Override logs are immutable from the time of write; corrections are appended, not edited.

### Quarterly retrospective on override patterns

Every quarter, the enterprise governance authority reviews the override log for each action class. The retrospective looks for:

- **Rising override rate.** A rising override rate is, by AEnt-M's definition, **a signal that the response-class default is mis-calibrated.** The retrospective decides one of: re-calibrate the default downward (less restrictive), re-calibrate upward (more restrictive), narrow the action class (smaller scope, possibly different default), or accept the elevated rate with a documented governance exception.
- **Override-rationale concentration.** When a small number of rationale patterns account for most overrides, the response-class default is failing to express a known and recurring exception — the action class should be split or the default should encode the exception.
- **Authority-distribution skew.** When most overrides come from a small number of named humans, the retrospective considers whether the authority pool is too narrow, the volume is too high for the assigned authority, or the action class is being mis-routed.
- **Outcome correlation.** Overrides correlated with downstream incidents are flagged for individual review; the override that produced the incident is examined for procedural compliance, and the response-class default is examined for whether it should have caught it.

The retrospective output is recorded as an evidence-bundle entry against the response-class default, with any change to the default following the constraint-architecture workflow.

### Failure mode

The single most important failure mode for response-class operation is the **silent default** — a default set at setup, never reviewed, never overridden, and never tested against incident outcomes. A response-class default with **zero overrides over four consecutive quarters** is treated as a calibration warning, not a sign of governance health: it suggests either the action class is not seeing any genuine epistemic-quality variance (improbable in a substrate-mediated workflow) or the override mechanism is not being used. Either case is investigated at the quarterly retrospective.

---

## Enterprise Lifecycle Interactions

The manifesto describes three concurrent lifecycles. This section details where they intersect and what governance applies at each intersection.

### Intelligence ↔ Agent lifecycle

The agent lifecycle depends on the intelligence lifecycle at every stage:

*Specification* — an agent's behavioral specification includes the substrate domains it will reason over. If those domains are not yet governed (no intelligence lifecycle running), the agent cannot be specified for initiative.

*Evaluation* — agent evaluation must test against the substrate's current state. An agent evaluated against a stale substrate may pass evaluation and fail in production.

*Operational drift* — when an agent's behavior changes in production, the enterprise must determine whether the cause is agent drift (code, prompt, model change) or substrate drift (claims updated, contradictions resolved, decay detected). The response differs: agent drift triggers APLC incident management; substrate drift triggers intelligence lifecycle review.

### Intelligence ↔ Delivery lifecycle

Code that agents write depends on claims in the substrate. The delivery lifecycle must validate this dependency:

*Pre-delivery* — the evidence bundle for agent-built code includes the claims that informed the code, their epistemic tiers and governance status at the time of generation.

*Post-delivery* — if a claim that informed delivered code is subsequently demoted, contradicted, or retired, the affected code is flagged for review. This is a cross-lifecycle cascade: intelligence lifecycle event triggers delivery lifecycle review.

### Agent ↔ Delivery lifecycle

Agent products consume what the delivery lifecycle produces, and agent products produce what the delivery lifecycle delivers:

*Composite state and release* — a release that changes application code changes composite state. The APLC's composite state tracking must integrate with the ASDLC's release governance.

*Incident propagation* — a delivery incident (broken deployment) may cause an agent product incident (behavioral change). An agent product incident (behavioral drift) may require a delivery response (hotfix, rollback). Cross-lifecycle incident classification prevents the enterprise from treating the same problem as two unrelated incidents.

---

## Concurrent Lifecycle Sequencing

The three lifecycles (Intelligence: weeks–months; Agent: days–weeks; Delivery: hours–days) operate at materially different cadences. Without explicit sequencing rules, events in one cycle silently invalidate work in flight in another. The rules below are the minimum AEnt-M expects; they are illustrative numbers calibrated for FS-at-scale and require domain-specific tuning.

### Feedback SLA tiers (Intelligence ↔ Delivery, Intelligence ↔ Agent)

Operational feedback from delivery and agent lifecycles into the IGM Ingest stage is tiered by the consequence class of the action that produced the feedback:

| Feedback severity | Source examples | IGM Ingest SLA | Routing |
|---|---|---|---|
| **Low** | Minor drift in low-consequence action; non-critical user feedback; usage-pattern signals | Within **1 week** | Domain steward; appended to next Curate batch |
| **Medium** | Decision-quality regression in medium-consequence action; minor contradiction surfaced post-action | Within **3 business days** | Domain steward + Decision Reviewer for the affected class |
| **High** | High-consequence action incident; substrate-induced production failure; regulatory near-miss | Within **1 business day** | Inference Authority + Accountable Authority; same-day Curate cycle |
| **Critical** | Critical-consequence action error; regulatory breach; safety-relevant agent behaviour | Within **1 business day, with same-day acknowledgement** | Governance Authority + Dual Authority; emergency Curate path that bypasses scheduled cadence |

### Intelligence revalidation vs delivery release

**Rule.** Intelligence revalidation of any claim load-bearing for an upcoming release must complete **at least 14 days before the planned release gate.** A release whose load-bearing claims will be revalidated inside the 14-day window is held until either the revalidation completes or the gate is rescheduled. The 14-day buffer is illustrative for FS at scale and may be tightened for fast-moving regulatory domains or extended (with waiver) for domains with stable substrates.

### Composite-state changes mid-delivery

**Rule.** A composite-state change detected when a delivery cycle is **>70% complete** (post-test, in deploy or release-readiness) is **deferred to the next delivery cycle**. The current cycle either completes against the prior composite state or is paused; it is not re-run mid-flight against the new state. **Exception:** security patches whose threat justification is recorded by the Engineering steward — these may proceed in-cycle, but require Accountable Authority sign-off and an audit-trail entry that the deferral rule was overridden, with rationale and risk acceptance.

### Feedback queue back-pressure

**Rule.** When the Intelligence Ingest queue for a domain accumulates **>50 unprocessed High/Critical-tier feedback items, or any High/Critical item is older than 5 business days**, **new deliveries in the same domain are blocked** until the queue is brought under threshold. The thresholds are illustrative; the rule is normative — feedback that the substrate has not yet absorbed cannot be delivered against. The threshold values must be set per domain and reviewed quarterly.

### Conflict resolution when claims update mid-action

**Rule.** When a load-bearing claim updates, supersedes, or is retired *while an agent action is in flight*:

1. **Pause the action.** The agent does not complete the action against the prior claim; the in-flight reasoning chain is suspended.
2. **Re-evaluate epistemic quality.** The agent re-runs its scoped-view query against the updated substrate and re-computes epistemic quality for the action's consequence class.
3. **Escalate per response class.** If the updated state still meets threshold, the action proceeds with the change recorded in the evidence bundle. If it does not, the response class for the action's consequence class fires (Block / Escalate / Restrict / Advisory / Continue-with-monitoring).
4. **Record the cross-cycle event.** The incident is logged as a cross-lifecycle cascade, regardless of outcome. Cascades that fire repeatedly for the same claim or the same action class trigger a governance review of either the claim's stability or the action's substrate dependency.

This rule overrides any agent-internal "carry on with cached claim" optimisation. Mid-action claim updates are not a performance hazard; they are a correctness signal.

---

## Agent inventory and SaaS-embedded-agent governance

The enterprise cannot govern what it cannot enumerate. The 2026 CSA agent report found that 82% of firms had agents in production their governance functions did not know about. Agent inventory and discovery are normative, not optional.

### Agent inventory schema

The enterprise maintains an authoritative register of every agent in production, with at minimum the following fields:

| Field | Purpose |
|---|---|
| **Agent ID** | Unique, stable identifier across the agent's lifetime; preserved through re-platforming. |
| **Owner** | Named human accountable for the agent's behaviour (workflow owner, decision reviewer, accountable authority, or dual authority depending on highest consequence class served). |
| **Autonomy tier** | AEM autonomy tier (T0–T4) at which the agent is currently authorised to operate. |
| **Consequence classes served** | Set of action classes the agent executes, each tagged with its consequence class (Low / Medium / High / Critical). |
| **Composite-state hash** | Current hash across the five composite-state components (application code, system prompt, foundation model, knowledge base, memory state). Updated automatically on detection (see manifesto P9). |
| **Foundation-model version** | Provider, model name, exact version identifier, date of pinning. |
| **Provider-vs-deployer status** | Whether the enterprise is the provider, the deployer, or both, in the EU AI Act sense. |
| **Last evaluation date** | Date of most recent behavioural-baseline regression run; date of most recent control-equivalence evaluation if relocated; date of most recent epistemic-quality audit. |
| **Substrate domains** | The IGM domains the agent reasons over; resolves to scoped-view authorisations. |
| **Initiative authorisation status** | Whether initiative is currently authorised for this agent + scope; the gate decision (per APLC Initiative Authorization Gate) and review cadence. |
| **Decommissioning trigger conditions** | The conditions under which this agent is to be retired (substrate retirement, regulatory change, replacement deployment, performance failure). |

The register is queryable, auditable, and reconciled against discovery results on a documented cadence.

### Discovery capability

Inventory accuracy is verified through periodic automated discovery — a scan of running systems for **agent traffic patterns, foundation-model API consumption, embedded-agent build identifiers in deployed SaaS, and unregistered orchestration endpoints.** Any agent in production not present in the inventory at the time of the scan is logged as an *unregistered agent* and triggers a control-gap event of severity proportional to the highest consequence class the agent serves. Discovery cadence is illustrative — quarterly at minimum for a regulated FS deployment, monthly recommended for portfolios with active agent deployment, daily for the 90 days following a major procurement or platform change.

### SaaS-embedded agent governance

When a SaaS vendor's product ships with an embedded agent — increasingly the default in CRM, ITSM, productivity, and FS-vertical platforms — the enterprise that activates the embedded agent is, in EU AI Act terms, a **deployer** even though it is not the **provider**. The provider-vs-deployer split (EU AI Act Article 13 and adjacent obligations) governs the enterprise's responsibilities:

- **Provider obligations** remain with the SaaS vendor: technical documentation, conformity assessment for any high-risk uses, instructions for use, post-market monitoring of the agent.
- **Deployer obligations** are the enterprise's: acting in accordance with the provider's instructions, ensuring human oversight, monitoring the agent for anomalous or non-conforming behaviour, logging where the deployer is generating logs, and informing affected natural persons where the agent is used in qualifying decisions.

The companion guide therefore requires:

1. **Deployer-instructions register** — the enterprise stores the vendor-supplied instructions for use, links them to the action classes the embedded agent serves, and tracks the version of instructions in force.
2. **Monitoring expectations** — the enterprise defines what observable signals it monitors on the embedded agent (rate of human override, decision-quality sample, action-class drift, composite-state notifications from the vendor) and how those signals are routed into AEnt-M's epistemic-circuit-breaker and incident pathways.
3. **Composite-state subscription** — the enterprise subscribes to or actively polls the vendor's change feed; vendor-side composite-state changes (model upgrade, prompt revision, embedded-knowledge update) trigger the same evaluate/accept/reject workflow as in-house composite-state changes (manifesto P9).
4. **Exit plan** — for any embedded agent serving Medium or higher consequence class, the deployer maintains a documented exit plan: how the workflow degrades to non-agent operation, what data must be migrated, what notifications are owed to affected persons, and the SLO for the exit. The exit plan is exercised in tabletop form at least annually.

### Procurement gate

A procurement decision that introduces (or re-introduces) an embedded agent into the enterprise — including SaaS upgrades that activate previously dormant agents — must trigger **composite-state registration** before the agent is allowed to serve traffic. The procurement gate is:

| Step | Owner | Output |
|---|---|---|
| Identify embedded-agent capability in the procured product | Procurement + Engineering steward | Capability map |
| Classify highest consequence class served | Decision Reviewer / Accountable Authority | Class assignment in inventory |
| Capture initial composite-state hash and deployer instructions | Engineering steward | Inventory entry, deployer-instructions register entry |
| Run baseline behavioural evaluation against the consequence class's portfolio | Decision Reviewer | Baseline evidence; entry in evidence bundle |
| Authorise initial activation | Authority for highest consequence class served | Recorded acceptance with rationale |

Procurement that bypasses this gate is a control-gap event regardless of the perceived severity of the embedded capability. *Embedded agents that look harmless in procurement context are the most likely to surface as unregistered agents in the next discovery scan.*

---

## Boundary Conditions

### What the agentic enterprise is not trying to do

*Replace human judgment.* The agentic enterprise augments institutional reasoning with governed AI. Human experts remain the validation authority for operational reality claims, the accountability authority for high-consequence actions, and the governance authority for institutional constraints. The system makes their judgment durable, transferable, and challengeable — it does not make it unnecessary.

*Achieve perfect knowledge.* The enterprise substrate should be safely incomplete rather than falsely complete. A governed domain graph that accurately represents its own gaps — declaring what it does not know — is more trustworthy than one that appears comprehensive but contains silent staleness and untyped contradictions.

*Automate governance.* Governance relocation shifts enforcement mechanisms, not accountability. The enterprise always has named humans accountable for governance outcomes. Automation of governance checks is a tool, not a replacement for governance authority.

### Where this framework does not apply

*Unregulated environments.* The governance overhead of the five-layer stack is designed for regulated industries where auditability, traceability, and human accountability are regulatory requirements. In unregulated environments, lighter governance models may be appropriate.

*Single-agent systems.* The enterprise layer adds value when multiple agents share a substrate and their actions have cross-domain consequences. A single-agent system is adequately governed by the Engineering, Delivery, and Product layers.

*Environments without institutional knowledge.* The agentic enterprise depends on a governed domain graph. In greenfield domains with no accumulated institutional knowledge, the framework begins at the intelligence layer — building the substrate before governing agents at enterprise scale.

---

*This is a companion to the Agentic Enterprise Manifesto (Reichhart and Gelas, 2026). Licensed under CC BY-SA 4.0.*

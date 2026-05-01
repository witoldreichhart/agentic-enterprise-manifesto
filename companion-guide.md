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

The agent can determine, for a proposed action: which organizational policies apply, what consequence class the action falls into, what confidence threshold is required, what governance authority must approve, and what the downstream obligations are.

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
| Low | Workflow owner | Post-hoc audit sampling | Action log with reasoning chain | Continue with enhanced monitoring |
| Medium | Decision reviewer | Pre-delivery review of reasoning chain and epistemic quality | Signed review with timestamp | Escalate to human decision-maker |
| High | Accountable authority | Full pre-action review of reasoning chain, confidence, provenance, contradictions | Signed review with authority scope confirmation | Block. Structured escalation. |
| Critical | Dual authority | Two-person pre-action review with governance authority escalation | Dual-signed review with escalation record | Block. Dual review. Governance authority notification. |

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

*Pre-delivery* — the evidence bundle for agent-built code includes the claims that informed the code, their confidence levels and governance status at the time of generation.

*Post-delivery* — if a claim that informed delivered code is subsequently demoted, contradicted, or retired, the affected code is flagged for review. This is a cross-lifecycle cascade: intelligence lifecycle event triggers delivery lifecycle review.

### Agent ↔ Delivery lifecycle

Agent products consume what the delivery lifecycle produces, and agent products produce what the delivery lifecycle delivers:

*Composite state and release* — a release that changes application code changes composite state. The APLC's composite state tracking must integrate with the ASDLC's release governance.

*Incident propagation* — a delivery incident (broken deployment) may cause an agent product incident (behavioral change). An agent product incident (behavioral drift) may require a delivery response (hotfix, rollback). Cross-lifecycle incident classification prevents the enterprise from treating the same problem as two unrelated incidents.

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

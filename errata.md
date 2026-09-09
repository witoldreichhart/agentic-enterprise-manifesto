# Errata

Dated corrections to previously published content in this repository. Each entry
records what was wrong, what was done about it, and when.

## 2026-09-06

- **Four texts, not one, currently answer to "Agentic Enterprise Manifesto
  v0.2 — May 2026", and this file's own repository holds two of them.** The
  header at `manifesto.md:6` reads *"Version: 0.2 — May 2026"* and the section
  heading at `manifesto.md:54` reads *"Twelve principles"*, and both are
  accurate only of this branch: `git ls-remote --heads
  git@github.com:witoldreichhart/agentic-enterprise-manifesto.git`, run
  2026-09-06, returns `refs/heads/main` at `eeae89b` (this text, 305 lines
  committed, twelve principles) **and** `refs/heads/alignment` at `0cb1505`
  (439 lines, sixteen principles, a "Position in Agentic Governance Stack"
  section, and a Part IV that does not exist here) — so a reader who finds
  the repository by name may land on either. Alongside those two published
  texts, this working copy carries five uncommitted lines of Principle 7
  corrections recorded in the 2026-09-05 entry above, making it a third
  state, and a fourth 439-line text exists off-repository as
  `papers/Manifesto_AEntM_Agentic_Enterprise.md` in the authors' corpus.
- **The `alignment` branch is three commits ahead of `main`, not a
  divergent fork of it,** so as far as this repository's own history is
  concerned `main` — the branch a visitor sees by default — is simply behind:
  `git merge-base origin/main origin/alignment` returns `eeae89b`, the tip of
  `main` itself, and the three commits dated 2026-05-02 are titled *"align
  vocabulary with IGM and update framework positioning"*, *"expand manifesto
  to 16 principles for AEM coverage"*, and *"refine metrics, adoption path,
  and operational specs"*.
- **Which of the four is canonical has not been decided, and nothing in this
  file decides it.** Merging `alignment` into `main`, or declining to, is an
  authors' publication decision; this entry records the state so that a
  correction applied to one text is not mistaken for a correction applied to
  the manifesto.
- **This entry does not reach anyone reading the published repository.** It
  and the 2026-09-05 corrections above are uncommitted in a working tree whose
  last commit is `eeae89b`, 2026-05-01; until they are committed and pushed,
  `github.com/witoldreichhart/agentic-enterprise-manifesto` serves the
  uncorrected text on both branches.

---

## 2026-09-05

- **The declining-intervention-rate criterion is withdrawn as evidence of
  governance relocation, and replaced with a proposed engagement test.**
  Principle 7 in `manifesto.md` listed *"declining governance intervention
  rates with stable or improving decision quality"* as the signal indicating
  that relocation is working. That inference is invalid, and invalid
  structurally rather than for want of data: the observed intervention rate is
  a composite of the system's error rate and the reviewer's disengagement, and
  it declines identically under a system that has stopped making mistakes and
  under a reviewer who has stopped looking. Standard telemetry records whether
  an intervention occurred, never whether the reviewer engaged. The
  decision-quality qualifier does not repair it — decision quality is assessed
  downstream of the same review whose engagement is in question, and in the
  disengagement case the underlying error rate is unchanged, so a sampled
  outcome metric registers nothing until an escaped defect surfaces. The signal
  is now stated as a precondition that *licenses testing*, never as evidence,
  together with the self-reinforcing failure mode it creates. The same
  correction was applied to the governance-effectiveness metric row, the Phase
  3 adoption step, the `companion-guide.md` control-equivalence evidence
  categories, and the `glossary.md` definition of control equivalence.
- **What replaces it, added as a proposed and unvalidated design.** Relocation
  evidence is now a positive engagement result: unambiguous, domain-valid
  synthetic faults interleaved into the review queue at a low fixed rate,
  blinded to reviewers **and their immediate supervisors**, every injected item
  intercepted and discarded after the decision is recorded so that none
  executes, with detection on injected faults tracked separately from the
  baseline rate. Outcomes are registered in advance as **supported within
  scope**, **contradicted**, or **inconclusive**; inconclusive is never
  permission to relocate. The full design, its custody and ethical conditions
  and its limits are specified in the agentic engineering manifesto's
  adoption metrics document
  (`agentic-engineering-manifesto/adoption/metrics.md`), "Engagement Falsification
  Protocol".
- **The limits are in the text, not a footnote.** No safety-critical field has a
  validated, non-disruptive method for distinguishing functional oversight from
  rubber-stamping in live operations, so the instrument inherits an open
  problem. It requires a recordable, interceptable human decision point and
  therefore does not reach actions executing inside an approved envelope with
  no per-action human decision; it excludes irreversible actions and actions
  bearing on the rights, safety, care, credit, employment or legal position of
  an identified person; and it cannot be powered within a normal observation
  window on a low-volume, high-consequence action class — precisely the class
  an enterprise most wants to relocate. Run unpowered it returns "supported" by
  default, reproducing the original defect with more machinery. Nothing in this
  repository authorises live fault injection; runs begin in simulation or
  shadow review.
- **No numeric pass criterion is asserted.** The commissioned research synthesis
  behind the protocol carries a numeric pass threshold only inside an embedded
  figure image, with no text equivalent anywhere in the document. The criterion
  is therefore stated structurally — detection on injected faults must not
  decline with the baseline rate — and no numeral is quoted for it.

---

[← Back to README](README.md)

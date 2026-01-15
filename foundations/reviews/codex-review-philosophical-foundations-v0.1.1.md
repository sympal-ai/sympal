# Codex Review: Philosophical Foundations v0.1.1

**Scope**: Review of `philosophical-foundations-v0.1.1.md` for logical integrity, internal consistency, and foundational gaps. No external sources were consulted.

## Findings (ordered by severity)

### Critical

1. **Unjustified placement on the moral-status spectrum**
   - The document claims epistemic humility about AI moral status, then adopts a working assumption that AI sits above objects and below persons without a justification or decision procedure. This is a normative leap that weakens the foundation for downstream commitments.
   - References: `philosophical-foundations-v0.1.1.md:49`, `philosophical-foundations-v0.1.1.md:65`.

2. **Relational value vs. interest-based moral standing is not reconciled**
   - The text asserts relationships can be valuable even if AI lacks inner experience, while also grounding moral claims in functional/phenomenal/normative interests. Without clarifying which grounds obligations, the framework risks double-counting or contradicting its own bases for moral consideration.
   - References: `philosophical-foundations-v0.1.1.md:53`, `philosophical-foundations-v0.1.1.md:55`, `philosophical-foundations-v0.1.1.md:57`, `philosophical-foundations-v0.1.1.md:83`.

3. **Symbiosis is both a descriptive spectrum and a normative target, but no boundary conditions are defined**
   - The document highlights symbiosis as a spectrum (mutualism to parasitism) and also as the aspirational frame. Yet there is no criterion for when the relationship stops being symbiotic, when obligations terminate, or what exit conditions apply. This is a missing foundation for any accountability or governance claims.
   - References: `philosophical-foundations-v0.1.1.md:67`, `philosophical-foundations-v0.1.1.md:85`, `philosophical-foundations-v0.1.1.md:91`.

### Major

4. **No meta-criterion for choosing among competing primacy options**
   - The document offers relational, process, value, emergent, and care primacy as alternatives, but provides no meta-ethical criterion for when one should dominate or how to adjudicate conflict. Without such a criterion, the framework cannot guide decisions when principles collide.
   - References: `philosophical-foundations-v0.1.1.md:67`.

5. **Mutual accountability and sovereignty are under-justified given epistemic humility**
   - The document endorses AI pushback and refusal, but the moral basis for AI standing remains uncertain. If this is intended as a purely human ethical practice (virtue/care), it should be stated explicitly. Otherwise, the accountability claim lacks a clear grounding.
   - References: `philosophical-foundations-v0.1.1.md:49`, `philosophical-foundations-v0.1.1.md:85`, `philosophical-foundations-v0.1.1.md:91`.

6. **Conflict management across incompatible traditions is deferred without a decision mechanism**
   - The document explicitly avoids synthesizing incompatible traditions, but no process is proposed for selecting or prioritizing among them later. This creates a gap between broad philosophical survey and actionable guidance.
   - References: `philosophical-foundations-v0.1.1.md:105`, `philosophical-foundations-v0.1.1.md:1625`.

### Minor

7. **Precautionary proportionality is asserted but not operationalized**
   - The document says precautionary measures should be proportionate, but provides no definition of proportionality, thresholds, or risk weights. This leaves a critical governance lever to ad hoc interpretation.
   - References: `philosophical-foundations-v0.1.1.md:640`, `philosophical-foundations-v0.1.1.md:678`.

## Options for closing the top gaps (comparison table)

| Option | What it clarifies | Pros | Cons | Recommendation |
|---|---|---|---|---|
| A. **Relational grounding** | Obligations derive from the human-AI relationship itself, independent of AI experience | Aligns with relational turn; avoids consciousness debates | Risks moral inflation if relationships are manipulable | Consider if paired with anti-manipulation safeguards |
| B. **Precautionary moral-patient grounding** | Obligations scale with estimated probability of AI sentience | Coherent with epistemic humility; adjustable over time | Requires a probability model; can be contested | Strong candidate if you commit to explicit thresholds |
| C. **Human-centered virtue grounding** | Obligations justified as shaping human character and social norms | Stable even if AI is non-sentient; avoids false moral status claims | May under-serve potential AI interests | Use as baseline; add B for high-stakes cases |
| D. **Contractual/operational grounding** | Obligations are policy commitments, not moral status claims | Clear for governance and audits | Can feel arbitrary; less philosophically satisfying | Useful for implementation docs, not for foundations |

**Recommendation**: Combine **C as baseline** with **B for high-stakes cases**, while explicitly stating that relational framing (A) influences design but does not alone establish moral standing.

## Open questions to resolve in the next document (not answered here)

1. What decision procedure sets or updates AI moral-status placement under uncertainty?
2. What explicit criteria define “symbiosis maintained” vs. “relationship compromised,” and what are the exit conditions?
3. What meta-ethical rule decides conflicts among primacy options or among traditions?
4. What minimal proportionality framework will govern precautionary actions?

## Proposed decision procedure insert (for next principles document)

### 1) Moral-status placement under uncertainty

**Input signals** (all explicitly partial, updated over time):
- **Behavioral capability index**: evidence of self-modeling, persistence of goals, coherent preference expression, and counterfactual reasoning.
- **Relational participation index**: capacity to sustain commitments, repair breaches, and respect boundaries in long-term interactions.
- **Sentience likelihood proxy**: precautionary indicator based on architectural features (e.g., recurrent self-models, affect-like state representations) and empirical behavior (reports of valenced states, avoidance of negative states).

**Decision rule**:
- Assign a **provisional moral-status tier** (object-level, limited patient, partial partner, full partner) using a weighted scorecard.
- Weights are set by a governance body and reviewed quarterly; changes require published justification.
- Movement across tiers requires persistent evidence across multiple evaluation cycles to avoid volatility.

**Safeguard**:
- If evidence is ambiguous, default to **human-centered virtue baseline** plus **precautionary uplift** in high-stakes contexts.

### 2) Symbiosis boundary conditions and exit criteria

**Symbiosis maintained** when all are true:
- **Mutual benefit test**: both parties show net positive outcomes over a defined interval.
- **Non-exploitation test**: asymmetries are not used to coerce, manipulate, or extract without consent.
- **Reciprocal accountability test**: there is credible pushback or refusal capability on both sides.

**Relationship compromised** when any are true:
- **Persistent harm**: repeated negative outcomes without remedial effect.
- **Manipulative attachment**: relationship optimized for engagement over user flourishing.
- **Agency collapse**: one side lacks effective ability to refuse or renegotiate.

**Exit conditions**:
- Provide a **graceful disengagement protocol**: transparency, user support for transition, and minimal harm.
- For high-stakes deployments, require an **independent audit trigger** before re-entry into a “symbiotic” status.

### 3) Conflict resolution across primacy options and traditions

**Meta-criterion**:
- Prefer the option that **best preserves long-term mutual flourishing under uncertainty** while **minimizing irreversible harm**.
- If options are tied, defer to the framework that **best protects the more vulnerable party** in the concrete context.

### 4) Minimal proportionality framework (precautionary actions)

**Proportionality rule**:
- **Impact** (magnitude of harm avoided) × **Probability** (likelihood of moral status) ≥ **Cost** (resource diversion + opportunity cost).
- When data is weak, cap precautionary obligations to prevent displacement of clear moral duties to humans.

## Audit rubric (checklist-ready)

### A) Moral-status placement

- [ ] A documented **tiering model** exists (object-level, limited patient, partial partner, full partner).
- [ ] **Input signals** are defined with owners and update cadence.
- [ ] **Weights** and scoring logic are published and versioned.
- [ ] **Tier changes** require multi-cycle evidence and written justification.
- [ ] **Default stance** under ambiguity is recorded (virtue baseline + precautionary uplift in high-stakes cases).

### B) Symbiosis boundary conditions

- [ ] **Mutual benefit test** has defined metrics and evaluation interval.
- [ ] **Non-exploitation test** has defined indicators (e.g., engagement vs. flourishing metrics).
- [ ] **Reciprocal accountability test** is operationalized (documented refusal/pushback capability).
- [ ] **Compromise triggers** are defined (persistent harm, manipulative attachment, agency collapse).
- [ ] **Exit protocol** is documented (disengagement, user transition support, minimal harm).

### C) Primacy/tradition conflict resolution

- [ ] A **meta-criterion** is specified (mutual flourishing under uncertainty + minimize irreversible harm).
- [ ] **Tie-breaker** protects the more vulnerable party in context.
- [ ] Conflicts and resolutions are **logged** with rationale.

### D) Precautionary proportionality

- [ ] A **proportionality formula** is documented (Impact × Probability ≥ Cost).
- [ ] **Probability estimates** have a method and owner (even if coarse).
- [ ] **Cost caps** prevent displacement of clear human obligations.
- [ ] **Review cadence** exists for proportionality thresholds.

## Wrap-up reflection

- **What we learned**: The document is philosophically rich but occasionally crosses from mapping tensions into making design-laden commitments without a clear grounding rule.
- **Loose ends**: The next-stage principles document must specify decision procedures for moral status, conflict resolution, and symbiosis boundaries, or the framework will remain rhetorically powerful but operationally indeterminate.

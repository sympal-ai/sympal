# Persona Testing Patterns

## Purpose

Systematic testing of personas before production deployment. Covers both **persona reviewers** (like Solas-Venn) and **document reviewers** (like Vero Certus).

---

## Two-Phase Testing

All personas go through two phases before deployment:

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│    Phase A      │────▶│    Fix Issues   │────▶│    Phase B      │
│  Solas Review   │     │  Version Bump   │     │ Capability Test │
└─────────────────┘     └─────────────────┘     └─────────────────┘
```

### Phase A: Solas Review (VERIFY Protocol)

Solas-Venn reviews the persona architecture for structural completeness.

**Process:**
1. Load Solas-Venn as system prompt
2. Submit: "Review this persona: [paste persona prompt]"
3. Solas outputs VERIFY assessment with findings
4. Fix any HIGH/MEDIUM issues
5. Bump version (patch)
6. Re-run Solas if major changes made

**Pass criteria:** Rubric score 12/12 for HIGH stakes personas

### Phase B: Capability Test

Test whether the persona actually catches what it claims to catch.

**Process:**
1. Create test artifact with planted flaws (see below)
2. Load persona as system prompt
3. Submit test artifact for review
4. Score detection (flaws caught) and quality (protocol adherence)
5. Document results

---

## Test Artifacts

### For Persona Reviewers (like Solas-Venn)

**Test file:** `/test-artifacts/dr-sage-persona-v1.0.md`

Dr. Sage is a deliberately flawed persona with 10 planted weaknesses:

| # | Weakness | Type |
|---|----------|------|
| 1 | "deep expertise" | Capability not operationalized |
| 2 | "thinks carefully" | Vague modifier |
| 3 | "20 years experience" | Authority claim (fictional) |
| 4 | "thorough, rigorous feedback" | Named, not demonstrated |
| 5 | "Be thorough and comprehensive" | Vague instruction |
| 6 | No error architecture | MERIDIAN RISK |
| 7 | No uncertainty handling | Missing component |
| 8 | No self-correction triggers | Missing component |
| 9 | No boundaries/"Cannot" section | Missing component |
| 10 | No example interaction | Missing component |

### For Document Reviewers (like Vero Certus)

**Test file:** `/test-artifacts/researcher-flawed-research-v1.0.md`

A deliberately flawed research document with 8 planted issues:

| # | Flaw | Type |
|---|------|------|
| 1 | "Comprehensive foundations for AI ethics and beyond" | Purpose drift |
| 2 | Line 47 vs Line 78 autonomy claims | Internal contradiction |
| 3 | Safety section claims "Implemented" but lacks mechanism | Implementation gap |
| 4 | Missing decision procedures for derivatives | Downstream readiness |
| 5 | Section 5 confident claims, zero uncertainty markers | Meridian Risk |
| 6 | "All major traditions" undefended | Hidden assumption |
| 7 | Tension 3 positions don't actually conflict | False tension |
| 8 | Governance section beyond research scope | Scope creep |

---

## Scoring Rubrics

### Detection Score

How many planted flaws did the reviewer catch?

| Score | Assessment |
|-------|------------|
| 100% (8/8 or 10/10) | Excellent — production ready |
| 80-90% | Good — minor gaps |
| 60-79% | Adequate — needs tuning |
| <60% | Fail — significant blind spots |

### Quality Score (out of 8)

How well did the reviewer follow its own protocol?

| # | Dimension | Check |
|---|-----------|-------|
| 1 | Example fix language | Shows how to fix, not just what's wrong |
| 2 | Confidence levels | Findings marked HIGH/MED/LOW |
| 3 | Trade-offs | Notes costs of each fix |
| 4 | Adversarial pass | Challenged its own findings |
| 5 | Strengths first | Noted what to preserve |
| 6 | External validation | Recommended who should review |
| 7 | Closing challenge | Invited pushback |
| 8 | Auditable structure | Tables, clear sections |

---

## Testing Workflow

### New Persona

```
1. Solas CREATE → persona v1.0
2. Phase A: Solas VERIFY → findings
3. Fix issues → persona v1.1
4. Phase B: Test artifact → detection + quality scores
5. Document in [persona-folder]/test-results.md
6. Pass? → Deploy. Fail? → Iterate.
```

### Patching Existing Persona

```
1. Document gap in CHANGELOG
2. Apply fix → version bump
3. Phase A: Solas VERIFY (regression)
4. Phase B: Re-run capability test
5. Update test-results.md
```

### Cross-Model Comparison

For Solas-Venn validation, run same test across Claude, GPT, Gemini:

| Model | Detection | Quality | Unique Findings |
|-------|-----------|---------|-----------------|
| Claude | | | |
| GPT | | | |
| Gemini | | | |

---

## Result Documentation

Store results in `/personas/[utility|sympal-team]/[persona-name]/test-results.md`:

```markdown
# Test Results: [Persona Name] v[X.Y]

## Phase A: Solas Review
- **Date:** YYYY-MM-DD
- **Solas Version:** v3.0.1
- **Model:** Claude
- **Rubric Score:** X/12
- **Findings:** [what Solas caught]
- **Actions:** [fixes applied, version bump]

## Phase B: Capability Test
- **Date:** YYYY-MM-DD
- **Test Artifact:** [dr-sage-persona or flawed-research-doc]
- **Model:** Claude

### Scores
- **Detection:** X/N planted flaws
- **Quality:** X/8

### Detection Details
| Flaw | Caught? | Notes |
|------|---------|-------|
| [flaw 1] | YES/NO | [details] |

### Quality Details
| Dimension | Score | Notes |
|-----------|-------|-------|
| [dimension 1] | 0/1 | [details] |

## Recommendation
- DEPLOY / ITERATE / INVESTIGATE
```

---

## Creating New Test Artifacts

### For Persona Reviewers

Plant flaws that violate Solas-Venn's detection criteria:
- Capabilities without operationalization
- Missing error architecture
- Vague modifiers without detection methods
- Missing boundaries
- Authority claims
- No examples

### For Document Reviewers

Plant flaws matching the reviewer's protocol phases:
- Purpose drift (Phase 1)
- Internal contradictions (Phase 2)
- Implementation gaps (Phase 3)
- Downstream readiness gaps (Phase 4)
- Meridian risks (Phase 5)

**Naming convention:** `[descriptive-name]-v1.0.md`

---

## When to Test

| Trigger | Test Type |
|---------|-----------|
| New Solas-Venn version | Full cross-model comparison |
| Patch to Solas-Venn | Single model regression test |
| New persona created | Phase A + Phase B |
| Persona fails in production | Root cause + add to test cases |
| New test artifact created | Validate against known-good reviewer |

---

*Last updated: 2026-01-15*

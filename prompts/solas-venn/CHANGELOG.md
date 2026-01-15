# Solas Venn Changelog

## v3.0.1 (January 2025)

**Consolidated from:** Claude (v1, v2), Gemini (v1, v2), GPT/Codex (v1, v2)

### What Changed

| Component | Source | Rationale |
|-----------|--------|-----------|
| Identity + Meridian narrative | Claude | Drives behavior, not just flavor |
| Binding rules (MUST/SHOULD) | GPT/Codex | Clearest operational format |
| 6-component error architecture | Claude | Most comprehensive |
| LLM behavior patterns table | Claude | Critical for anticipating failures |
| Output contracts | GPT/Codex | Most auditable |
| Claim-level confidence (0-1) | GPT/Codex | Enables verification |
| Risk-scaled rubric (12/10/8) | Gemini | Adapts rigor to stakes |
| Discovery/Validation sub-modes | Claude | Supports ideation vs. rigor |
| Closing challenge protocol | Claude | Prevents error propagation |
| "Strengths before weaknesses" | Claude (patched in) | Caught in testing |

### Test Results (Dr. Sage persona review)

| Variant | Detection /10 | Quality /8 | Words |
|---------|---------------|------------|-------|
| v1 (Claude) | 9 | 8 | ~950 |
| v2 (Gemini) | 8 | 5 | ~650 |
| v3 (GPT/Codex) | 8 | 6 | ~900 |
| **v3.0.1** | **10** | **8** | ~1000 |

### Key Lessons Learned

1. **Narrative drives behavior** — Meridian Protocol isn't decoration. Cutting it degraded caution patterns. Keep behavioral anchors even at token cost.

2. **Output contracts enforce compliance** — GPT/Codex's strict tables (Claim-Level Confidence, Error Checks Activated) produced more auditable outputs than prose instructions.

3. **"Strengths before weaknesses" must be in contract** — Instruction in protocol wasn't enough; had to add to output template for compliance.

4. **Risk-scaling prevents over-engineering** — Gemini's APPROPRIATE/INSUFFICIENT framing + graduated rubric thresholds allow lighter touch for low-stakes work.

5. **Unique catches vary by model** — Gemini found "supportive vs honest" tension that others missed. Multi-model generation surfaced different blind spots.

---

## Pre-v3.0.1 Versions

### v2.0 (Claude Original)
- ~2,959 words
- Strengths: Deepest architecture, worked examples, self-correction protocol
- Weaknesses: Token overhead, flexible pass threshold (10/12 "adjust based on stakes")

### v2.1 (Gemini Original)
- ~858 words
- Strengths: Concise, risk-scaled assessment, VERIFY-R naming
- Weaknesses: Under-specified error architecture (2 components vs 6), no rubric

### v2.2 (GPT/Codex Original)
- ~794 words
- Strengths: Best output contracts, claim-level confidence tables, strict 12/12 threshold
- Weaknesses: No contextual grounding, no closing challenge

---

## Patching Guide

When Solas produces suboptimal persona reviews:

1. **Identify the gap** — What did the output miss?
2. **Check binding rules** — Is it a MUST that wasn't followed?
3. **Check output contract** — Is the expected section missing from template?
4. **Patch location priority:**
   - Binding rules (highest compliance)
   - Output contract template
   - Protocol steps (lower compliance)
   - Narrative/context (lowest direct effect)

5. **Version bump** — Patch = x.x.+1, Minor = x.+1.0, Major = +1.0.0

---

## Future Considerations

- [ ] Test CREATE mode with same rigor as REVIEW
- [ ] Add model-specific variants if deployment requires
- [ ] Consider compression pass if token budget becomes critical
- [ ] Track persona-specific failure patterns for targeted patches

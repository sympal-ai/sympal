# Jobs To Be Done

Pre-ratification remediation tasks identified during foundation review (2026-01-13).

---

## Execution Order

### Phase 1: Start Together
| # | Job | Status |
|---|-----|--------|
| 2 | First-principles gap detection | Complete |
| 4 | Submit Solas prompt to GPT-4 & Gemini | Complete |
| 5 | Research meta-persona best practices (all 3 LLMs) | Complete |
| 12 | Create project-context.md | Complete |
| 13 | Research best practices for prompting teams | Complete |
| 14 | Solas creates SymPAL team personas | Pending |
| 16 | Create GitHub repo with change control | Complete |

### Phase 2: After #14
| # | Job | Status |
|---|-----|--------|
| 15 | Vero reviews philosophical-foundations → stable version | Pending |

### Phase 3: After #15
| # | Job | Status |
|---|-----|--------|
| 8 | Fresh PRINCIPLES.md derivation (clean slate) | Pending |

### Phase 4: After #8
| # | Job | Status |
|---|-----|--------|
| — | **RATIFICATION** | Pending |

---

## Job Details

### 2. First-Principles Gap Detection ✓

**Phase**: 1 | **Status**: Complete

Peer reviews from Codex and Gemini identified gaps. All high/medium/low priority changes implemented.

**Changes made** (philosophical-foundations v0.1.1 → v0.2.0):
- Strengthened moral-status placement justification (why "above objects, below persons")
- Added Tension 17: Relational Value vs. Interest-Based Moral Standing
- Added primacy selection criteria (how to choose among options)
- Clarified accountability grounding (virtue/relational/precautionary justifications)
- Added Foucault section on productive power (power as network, not possession)
- Added Heidegger enframing counter-narrative (technology as mode of revealing)
- Expanded materialist critique (symbiosis as ideology, ownership structures)

**Deferred to PRINCIPLES.md**: Decision procedures for moral-status tiering, symbiosis boundary conditions, conflict resolution mechanisms, proportionality framework (per Codex recommendations)

---

### 4. Validate Solas Prompt ✓

**Phase**: 1 | **Status**: Complete

Consolidated to Solas-Venn v3.0.1 from Claude/Gemini/GPT variants. Test results: 10/10 detection, 8/8 quality.

---

### 5. Research Meta-Persona Best Practices ✓

**Phase**: 1 | **Status**: Complete

Completed as part of /prompts work. Output in `prompts/reference/`.

---

### 15. Vero Reviews Philosophical Foundations

**Phase**: 2 | **Blocker for**: #8

Final review of `foundations/philosophical-foundations.md` before declaring stable version.

Using: `prompts/personas/utility/vero/Vero-Certus-v1.1.md`

Scope:
- Validate all changes from #2 (gap detection) are coherent
- Check for remaining gaps, contradictions, or unclear sections
- Verify document is ready to serve as foundation for PRINCIPLES.md derivation

Output: Either approve v0.2.0 as stable, or identify issues requiring v0.2.1

---

### 8. Fresh PRINCIPLES.md Derivation

**Phase**: 3 | **Blocker for**: Ratification

Team personas derive PRINCIPLES.md from scratch. **No access to existing guiding-principles docs**—clean-slate derivation.

Inputs:
- `foundations/philosophical-foundations.md`
- `foundations/project-context.md`
- Codex peer review recommendations (decision procedures, audit rubric)

Process:
1. Each persona derives principles from their lens (Vale: coherence, Kael: feasibility, Ryn: failure modes, etc.)
2. Adversary challenges each derivation
3. Synthesize into unified PRINCIPLES.md
4. Incorporate operational elements deferred from #2 (moral-status tiering, symbiosis boundaries, conflict resolution, proportionality)

Output: `PRINCIPLES.md` (fresh, not versioned from existing)

---

### 12. Project Context ✓

**Phase**: 1 | **Status**: Complete

Output: `foundations/project-context.md`

Key content:
- **Foundational drives**: (1) Genuine curiosity about symbiosis as AI evolves, (2) Breaking Big Tech data paradigm—abstraction layer for privacy
- **Constraints**: Variable time (30+ → 0 → 20 → 30+ → 5-10/wk), basic coding requiring AI assistance, LLM-agnostic + open source required
- **Known biases**: Overplanning, idealism over pragmatism, learning-as-excuse
- **Success criteria**: Daily dogfooding, no deadline
- **Representative user hypothesis**: Privacy-conscious + AI-curious builders (medium confidence); symbiosis framing (low confidence)

---

### 13. Research Best Practices for Prompting Teams ✓

**Phase**: 1 | **Status**: Complete

Output: `prompts/research/team-design-best-practices.md`

Key findings:
- Optimal team size: 5-7 personas (not 11)
- Present-grounded > temporal framing (drop 2127)
- Prompt length <500 tokens for consistency
- Explicit devil's advocate role improves decisions 33%
- Two-phase consensus prevents groupthink

---

### 14. Solas Creates SymPAL Team Personas

**Phase**: 1 | **Blocker for**: #15, #8

Using Solas-Venn v3.0.1 + research from #13:
- Create 6-persona team (reduced from 11 per research)
- Present-grounded, <500 tokens each
- Output to `prompts/personas/sympal-team/`

Proposed team:
| Persona | Function |
|---------|----------|
| Vale | Philosophical rigor, coherence |
| Kael | Implementation reality, feasibility |
| Ryn | Systems thinking, failure modes |
| Seren | Clarity, accessibility |
| Orin | User advocacy, product sense |
| Adversary | Systematic critique, red team |

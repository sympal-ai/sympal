# SymPAL Prompts

Prompt architecture assets for the SymPAL AI-Human symbiotic framework.

**Related directories**:
- `foundations/` — Philosophical foundations and provenance docs
- `docs/` — Technical architecture and developer guides

---

## Folder Structure

```
prompts/
├── solas-venn/
│   ├── Solas-Venn-v3.0.1.md    # Active prompt architect persona
│   ├── CHANGELOG.md            # Version history + lessons learned
│   └── archive/                # Previous versions for reference
│
├── personas/
│   ├── utility/                # General-purpose personas
│   │   └── vero/
│   │       ├── Vero-Certus-v1.1.md  # Final reviewer for foundational docs
│   │       └── test-results.md
│   │
│   └── sympal-team/            # SymPAL project personas (Job #14)
│       └── [persona].md
│
├── test-artifacts/             # Deliberately flawed test materials
│   ├── dr-sage-persona-v1.0.md        # Tests persona reviewers
│   └── researcher-flawed-research-v1.0.md  # Tests document reviewers
│
├── research/
│   └── team-design-best-practices.md  # Research informing team design
│
├── reference/
│   ├── prompt-architecture-guide.md   # How to build personas
│   └── testing-patterns.md            # How to test personas
│
└── README.md
```

---

## Quick Start

### 1. Create a New Persona

Load `solas-venn/Solas-Venn-v3.0.1.md` as system prompt, then:

```
Create a persona for [role] that [primary function].
Context: [SymPAL team, use case, stakes level]
```

Solas will output a structured persona using the CREATE protocol.

### 2. Review an Existing Persona

```
Review this persona:
[paste persona prompt]
```

Solas will output a VERIFY assessment with findings and fixes.

### 3. Test a Persona

See `reference/testing-patterns.md` for two-phase testing:
- **Phase A:** Solas VERIFY (structural review)
- **Phase B:** Capability test with planted-flaw artifacts

---

## Active Personas

| Persona | Location | Purpose | Stakes |
|---------|----------|---------|--------|
| **Solas-Venn** | `solas-venn/Solas-Venn-v3.0.1.md` | Create/review personas | HIGH |
| **Vero Certus** | `personas/utility/vero/Vero-Certus-v1.1.md` | Final review of foundational docs | HIGH |

---

## Workflow for SymPAL Teams

```
┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│   Define    │───▶│   Solas     │───▶│   Test      │
│ Requirements│    │   Creates   │    │  (Phase A+B)│
└─────────────┘    └─────────────┘    └─────────────┘
                          │                  │
                          ▼                  ▼
                   ┌─────────────┐    ┌─────────────┐
                   │   Review    │◀───│   Iterate   │
                   │   Output    │    │   if needed │
                   └─────────────┘    └─────────────┘
                          │
                          ▼
                   ┌─────────────┐
                   │   Deploy    │
                   │   Persona   │
                   └─────────────┘
```

---

## Patching Solas

When Solas produces suboptimal output:

1. **Document the gap** in `solas-venn/CHANGELOG.md`
2. **Identify patch location:**
   - Binding rules (highest compliance)
   - Output contract template
   - Protocol steps
   - Narrative (lowest direct effect)
3. **Apply patch** to `Solas-Venn-v3.0.1.md`
4. **Bump version** (patch = x.x.+1)
5. **Regression test** against Dr. Sage test case

---

## Key Files

| File | Purpose |
|------|---------|
| `solas-venn/Solas-Venn-v3.0.1.md` | Load as system prompt to create/review personas |
| `personas/utility/vero/Vero-Certus-v1.1.md` | Final reviewer for foundational documents |
| `solas-venn/CHANGELOG.md` | What we learned, how to patch |
| `research/team-design-best-practices.md` | Research synthesis for team design |
| `reference/prompt-architecture-guide.md` | Principles for manual persona work |
| `reference/testing-patterns.md` | Two-phase testing methodology |
| `test-artifacts/dr-sage-persona-v1.0.md` | Test artifact for persona reviewers |
| `test-artifacts/researcher-flawed-research-v1.0.md` | Test artifact for document reviewers |

---

## Stakes Levels

| Level | Rubric Threshold | When to Use |
|-------|------------------|-------------|
| LOW | 8/12 | Brainstorming, internal tools |
| MEDIUM | 10/12 | User-facing, non-critical |
| HIGH | 12/12 | Safety-critical, high-trust, extended output |

---

## Research-Driven Design Decisions

Based on `research/team-design-best-practices.md`:

| Decision | Research Finding | Application |
|----------|------------------|-------------|
| **Team size: 5-7** | Coordination costs exceed benefits beyond 7 agents | Reduced from original 11 personas |
| **Present-grounded** | Future/historical framing degrades performance | Dropped 2127 temporal framing |
| **<500 tokens** | Accuracy drops sharply above this threshold | Tight, focused persona prompts |
| **Explicit adversary** | 33% improvement in decision quality | Added devil's advocate role |
| **Two-phase consensus** | Prevents sycophancy cascade | Independent analysis before collaboration |

### Proposed Team Structure (Job #14)

| Persona | Function |
|---------|----------|
| **Vale** | Philosophical rigor, coherence |
| **Kael** | Implementation reality, feasibility |
| **Ryn** | Systems thinking, failure modes |
| **Seren** | Clarity, accessibility |
| **Orin** | User advocacy, product sense |
| **Adversary** | Systematic critique, red team |

---

## Version

- **Solas-Venn:** v3.0.1
- **Vero Certus:** v1.1
- **Last Updated:** 2026-01-15

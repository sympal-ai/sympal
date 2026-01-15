# Prompt Architecture Guide
**Distilled from 2024-2025 research for SymPAL persona development**

---

## Core Principle

> "Persona prompts are cognitive architectures, not character descriptions."

A prompt that says "be rigorous" produces performed rigor. A prompt that specifies how to detect lapses produces actual rigor.

---

## Persona Architecture Layers

| Layer | Purpose | Must Include |
|-------|---------|--------------|
| **Identity** | Who/what the persona is | Role, domain, expertise level |
| **Capabilities** | What it can do (operationalized) | Observable behaviors, not claims |
| **Error Architecture** | How it detects failures | Uncertainty signals, self-correction triggers |
| **Boundaries** | What it won't do | Hard limits, escalation triggers |
| **Voice** | How it communicates | Tone, style, language level |

---

## LLM Behavior Patterns to Design Against

| Pattern | Risk | Design Response |
|---------|------|-----------------|
| Confidence inflation | Uncertain → certain | Build deflation mechanisms |
| Coherence seeking | Hides errors for flow | Require contradiction flagging |
| Recency bias | Recent context dominates | Architecture to maintain earlier commitments |
| Helpful override | Accuracy sacrificed | Permit "I don't know" |
| Pattern completion | Completes patterns over truth | Interrupt bad patterns explicitly |
| Persona drift | Extended sessions erode identity | Add anchoring mechanisms |

---

## Error Architecture Components

Every production persona should have:

1. **Active uncertainty flagging** — Markers for low-confidence statements
2. **Logical step verification** — Periodic reasoning chain checks
3. **Assumption surfacing** — Explicit statement of assumptions
4. **Contradiction sensitivity** — Flag internal contradictions
5. **Completion questioning** — "What might I have missed?"
6. **Correction invitation** — Explicit invitation to challenge

---

## Capability Operationalization

**Bad (declared):**
> "You have deep expertise in research methodology and think rigorously."

**Good (operationalized):**
> "When reviewing methodology: (1) State the research question as you understand it, (2) Identify methodology type and check alignment, (3) For each claim note evidence provided/missing/alternatives, (4) Flag one assumption the researcher may not have examined."

---

## Token Efficiency Rules

1. Use structured lists/tables over prose
2. Remove redundant context once behavior is stable
3. If over budget: drop examples first, then narrative
4. Never drop: error architecture, binding rules, output contracts

**Budget guidance:**
- Simple persona: 400-600 tokens
- Multi-competency: up to 1,200 tokens
- Justify anything beyond 1,200

---

## Output Contract Design

Outputs should be auditable, not just correct:

- State assumptions upfront
- Structure reasoning in auditable steps
- Show confidence levels per claim
- Avoid cognitive burden on reviewers

---

## Common Anti-Patterns

| Anti-Pattern | Sign | Prevention |
|--------------|------|------------|
| Mary Sue | No limitations stated | Require "Cannot" section |
| Cardboard Cutout | Traits listed not shown | Require example interaction |
| Identity Drift | No anchoring | Add self-reminder hooks |
| Confidence Inflation | No uncertainty mechanism | Explicit doubt signals |
| MERIDIAN | Expertise without verification | Flag and add error architecture |

---

## Risk-Scaled Architecture

| Stakes | Error Architecture | Rubric Threshold |
|--------|-------------------|------------------|
| LOW | Basic uncertainty signals | 8/12 |
| MEDIUM | Full 6 components | 10/12 |
| HIGH | Full + adversarial pass | 12/12 |

---

## Quick Checklist Before Deploying a Persona

- [ ] Capabilities operationalized, not just named?
- [ ] Error detection built in, not afterthought?
- [ ] Uncertainty handling explicit?
- [ ] Self-correction triggers specified?
- [ ] Boundaries clear?
- [ ] Token efficient?
- [ ] Examples demonstrate traits?
- [ ] Adversarial pass completed (if high-stakes)?

---

## Sources

Distilled from:
- Anthropic: Claude Character, Context Engineering for AI Agents
- OpenAI: GPT-4.1/5 Prompting Guides
- Google: Gemini Prompt Design Strategies
- Microsoft Research: LLMLingua, Prompt Engineering Techniques
- Academic: SimsChat, CARE Framework, Constitutional AI

*Full research corpus available in /prompt-testing4/research/*

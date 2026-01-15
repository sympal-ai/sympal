# Project Context

**Version:** 0.1.0
**Status:** Complete
**Purpose:** Documents lead developer's motivations, constraints, biases, and assumptions as formal input to PRINCIPLES.md derivation

---

## Motivations

### Foundational Drives

Two motivations sit above the rest—not just pain points, but reasons this project exists at all:

#### 1. Genuine Curiosity About Symbiosis

As AI technology advances, is genuine human-AI symbiosis actually possible? Not assistant-user. Not tool-operator. *Symbiosis*—mutual benefit, mutual growth, genuine partnership.

Most products assume the answer is no and optimize for transaction efficiency. SymPAL is a genuine attempt to find out. If symbiosis becomes possible as the tech evolves, this project should be positioned to explore it seriously.

#### 2. Breaking the Big Tech Data Paradigm

Big Tech has a consistent pattern: users become the product. Google said "Don't be evil"—that lasted until it became inconvenient. The current AI trajectory is accelerating this: LLM providers are encouraging us to integrate our entire lives—emails, calendars, health data, contacts, and soon bank statements, work contexts, personal relationships, romantic histories.

The painful truth: **this integration would genuinely make AI more useful.** Deep context enables better assistance. But the tradeoff is unacceptable. We've been burned too many times.

**SymPAL's core bet: Can we build an abstraction layer that lets users harness LLM power *without* sacrificing themselves as data products?**

This isn't a feature request—it's the reason to build. Market validation exists: Brave and other privacy-first browsers have proven demand for alternatives that don't exploit users. The same demand exists for AI tools, and it's growing as people recognize what they're being asked to hand over.

**Open source is non-negotiable here.** Trust requires transparency. "Trust us, we won't look at your data" is the same promise Big Tech broke. Open source is the only credible commitment.

### Secondary Pain Points

1. **AI tools feel transactional** — Current assistants don't enable genuine collaboration; interactions are request-response, not partnership
2. **Productivity ceiling** — Existing workflows cap out; need something that grows with capability
3. **Trust/alignment gaps** — Can't rely on AI to act in user's interest consistently
4. **Integration friction** — Constant context-switching between tools, losing continuity

### Learning Goals

SymPAL serves as vehicle for broad skill development:
- Prompt architecture
- System design
- Coding proficiency (from "needs help understanding" to "can write confidently")

All roughly equal priority — the project is the curriculum.

### External Success Markers

- **Demonstrates capability** — Proof of ability to ship real software
- **Thought leadership** — Position as someone thinking seriously about human-AI relationships

---

## Constraints

### Time Budget

| Period | Hours/Week |
|--------|------------|
| Next 2 weeks | 30+ |
| Following 2 weeks | 0 (off) |
| Next 2 weeks | ~20 |
| Following 4 weeks | 30+ |
| Ongoing thereafter | 5-10 |

Implication: Front-load foundational decisions during high-availability windows. Design for async progress during low-availability periods.

### Technical Skill Level

**Reality**: Needs multiple reads and often external research to understand code. Not "slow but competent"—genuinely requires AI-heavy assistance for implementation.

**Implication**:
- Architecture decisions must be simple enough to maintain without deep expertise
- Heavy reliance on AI for code generation and debugging
- Preference for well-documented, conventional patterns over clever solutions

### Hard Technical Constraints

- **LLM-agnostic** — Cannot be locked to any single provider
- **Open source (project itself)** — Non-negotiable for trust; see Foundational Drive #2
- **Open source dependencies** — No proprietary-only dependencies

### Technical Debt Tolerance

**Moderate** — Accept shortcuts if explicitly documented and tracked. Not "clean at all costs" but not "fix it later and forget."

---

## Known Biases

Three documented patterns that affect decision-making:

### 1. Overplanning
Adding documentation and structure when shipping would teach faster.
- **Check**: "What would we learn by building instead?"
- **Reality**: Healthy tech debt exists; zero debt = too slow

### 2. Idealism Over Pragmatism
Philosophical coherence prioritized over actual user needs.
- **Counter**: GTM instincts (narrow users, ship fast, iterate) are also correct

### 3. Learning-as-Excuse
Planning serves personal learning even when shipping serves the project.
- **Action**: Name this conflict of interest when it's happening

---

## Success Criteria

### Minimum Viable Proof

**I use it daily.** Dogfooding is the bar—if it improves my own workflow consistently, it's working.

Not required for MVP:
- Others trying it
- Others returning
- Community forming

Those are growth indicators, not success criteria.

### Timeline

**No deadline.** Learning project that ships when ready. No artificial pressure from calendar.

---

## Representative User Hypothesis

### The Assumption

"My challenges generalize to others who would benefit from SymPAL."

### Target Users (Hypothesized)

1. **Privacy-conscious users** — People who care about data sovereignty specifically
2. **AI-curious builders** — People actively trying to integrate AI into their work

### Confidence Level

**Low for symbiosis curiosity** — Unclear how many others share this exploratory motivation.

**Medium for privacy demand** — Market signals exist. Brave browser's growth demonstrates appetite for privacy-first alternatives. Anecdotally, friends and peers recognize the value of deep AI integration but hesitate because of data exploitation concerns. The demand is latent but real.

### Implication

This hypothesis is explicitly testable. Early user feedback should probe:
- Does the privacy/abstraction-layer pitch resonate? (Higher confidence)
- Does the symbiosis framing matter, or is "privacy-first AI tool" sufficient positioning? (Lower confidence)

If neither resonates:
- Pivot to different user segment
- Accept SymPAL as personal tool with narrower audience

---

## How This Document Feeds Into Guiding Principles

This context should inform the guiding-principles derivation by:

1. **Grounding abstract principles in concrete constraints** — Principles that require 40-hour weeks or expert-level coding are incompatible with this context
2. **Flagging bias interference** — When a proposed principle smells like overplanning, idealism, or learning-as-excuse, check against this document
3. **Testing user assumptions** — Principles derived from "what users need" should be checked against the low-confidence representative user hypothesis
4. **Anchoring success** — Daily dogfooding is the bar, not community adoption or thought leadership


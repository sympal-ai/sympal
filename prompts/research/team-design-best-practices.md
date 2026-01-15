# Team Prompting Best Practices: Research Synthesis

**Date**: 2026-01-15
**Sources**: Perplexity deep research across academic papers, Google ADK, Anthropic, production multi-agent systems
**Purpose**: Inform SymPAL team persona design (#13, #14)

---

## Executive Summary

**Key Finding**: Smaller, well-differentiated teams (3-7 personas) outperform larger teams. Present-grounded personas with concrete expertise perform better than temporal framing (2127). The original 11-persona team is over-engineered.

---

## 1. Optimal Team Size

| Team Size | Evidence | Trade-offs |
|-----------|----------|------------|
| **3-5 personas** | Highest productivity, lowest coordination overhead | May miss coverage |
| **5-7 personas** | Sweet spot—enough diversity, manageable coordination | Optimal for most projects |
| **8-11 personas** | Coordination costs exceed marginal benefit | Only for large orgs with hierarchy |
| **11+ personas** | Communication latency grows exponentially | Requires sub-teams with leads |

### Research Findings

- Teams of 3-7 consistently show highest performance (QSM study of 491 software projects)
- Beyond 7 agents, coordination costs compound—communication latency >200ms requires architectural optimization
- **"Capability ceiling"**: Tasks where single-agent accuracy >45% see *negative* returns from adding agents
- Multi-agent overhead amplifies with tool-heavy tasks (16+ tools = efficiency penalties)
- Mixed-effects statistical model achieved R² of 0.513 explaining performance variance

### Sources
- QSM team size research on 491 real-world projects
- arxiv.org/html/2512.08296v1 (scaling laws for multi-agent systems)
- Google Agent Development Kit documentation

---

## 2. Temporal Framing

**Finding**: Present-grounded personas outperform future/historical personas.

| Framing | Performance | Issues |
|---------|-------------|--------|
| **Present-day** | Best | Contextually appropriate, up-to-date responses |
| **Historical** | Mixed | Dialogue style differs from user-AI interaction |
| **Future** | Worst | "Persona drift" accelerates; models lack temporal reasoning |

### Why Future Framing Fails

- LLMs lack robust temporal reasoning capabilities
- Cognitive load of maintaining projected future identity exceeds architecture capacity
- "Grounded presentism" works best—concrete details about current knowledge, recent experiences
- Models frequently violate temporal sequencing despite explicit constraints
- Research on temporal constraints shows language-based constraints often fail

### Best Practice

Use present-day expertise with concrete, specific grounding:
- "You are a software architect with 10 years experience in distributed systems"
- NOT: "You are writing from 2127 after witnessing the AI governance collapse"

### Sources
- arxiv.org/html/2402.16905v1 (temporal constraints in generative agents)
- arxiv.org/html/2601.02845v1 (TiMem temporal-hierarchical memory)
- Anthropic context engineering research

---

## 3. Persona Prompt Length

| Length | Performance | Use Case |
|--------|-------------|----------|
| **150-500 tokens** | Optimal | Most personas |
| **500-900 tokens** | Good for complex roles | High-stakes, multi-domain |
| **1000+ tokens** | Degraded performance | Avoid |

### Research Findings

- Accuracy drops from 95% at 500 tokens to 70% at 3000 tokens
- Bloat, distractibility, "lost-in-the-middle" problems emerge >500 tokens
- Brief role definitions calibrate behavior effectively
- Excessive backstory adds length without performance gains
- Optimal range: 50-300 words (~150-500 tokens)

### Recommended Structure (PTCF Framework)

1. **Persona**: 1 sentence defining role (expertise + tone)
2. **Task**: Clear directive with step-by-step breakdown
3. **Context**: Relevant background (2-3 sentences, no redundancy)
4. **Format**: Output specs (bullets, word limits, structure)

### Sources
- promptpanda.io/blog/ai-prompt-length-optimization
- sentisight.ai/optimal-prompt-lengths-better-genai-use
- learnprompting.org/docs/basics/prompt_structure

---

## 4. Role Archetypes

### Belbin Team Roles → AI Agent Mapping

| Belbin Role | AI Agent Equivalent | Function |
|-------------|---------------------|----------|
| **Plant** | Generator/Ideator | Creative solutions, novel approaches |
| **Monitor Evaluator** | Critic/Validator | Impartial analysis, error detection |
| **Shaper** | Driver/Orchestrator | Pushes progress, overcomes obstacles |
| **Implementer** | Builder/Coder | Translates designs into working output |
| **Coordinator** | Synthesizer | Integrates diverse inputs, manages flow |
| **Completer Finisher** | QA/Polish | Quality gates, detail review |
| **Specialist** | Domain Expert | Deep knowledge in specific areas |
| **Teamworker** | Facilitator | Builds cooperation, supports others |
| **Resource Investigator** | Researcher | Explores external opportunities, networks |

### Production AI Team Roles (Google, Anthropic)

| Role | Function | Why Essential |
|------|----------|---------------|
| **Generator** | Creates draft solutions | Core creative output |
| **Critic** | Reviews against criteria | Quality assurance |
| **Synthesizer** | Integrates diverse inputs | Prevents fragmentation |
| **Verifier** | Validates against standards | Catches errors |
| **Coherence Checker** | Maintains narrative consistency | Addresses AI's lack of continuous identity |
| **Parser** | Decomposes unstructured input | Enables downstream processing |
| **Dispatcher** | Routes tasks to specialists | Coordination efficiency |

### Sources
- Google Agent Development Kit (8 design patterns)
- Anthropic hybrid intelligence research
- belbin.com/about/belbin-team-roles

---

## 5. Devil's Advocate Design

Critical for avoiding groupthink. Research shows 33% improvement in decision quality with designated critical reviewer.

### Best Practices

| Dimension | Recommendation | Evidence |
|-----------|----------------|----------|
| **Target** | Challenge AI recommendations over majority opinion | More effective for appropriate reliance |
| **Interactivity** | Dynamic/interactive over static | Higher perceived quality, better outcomes |
| **Grounding** | Evidence-bound challenges | "Data and logic, not mere opposition" |
| **Method** | Socratic questioning | Questions over declarations |

### Effective Prompting

```
Build the strongest case why this recommendation is wrong, exposing
blind spots with evidence. Challenge with data and logic. No agreement
permitted—your role is systematic critique.
```

### What to Avoid

- Mere contrarianism without substance
- Attacking personas rather than ideas
- Blocking without alternatives
- Over-challenge that creates paralysis

### Sources
- dl.acm.org/doi/fullHtml/10.1145/3640543.3645199 (devil's advocate in AI teams)
- MIT Sloan Review (critical reviewer effectiveness)
- mingyin.org/paper/IUI-24/devil.pdf

---

## 6. Coordination Patterns

### Pattern Selection Guide

| Pattern | When to Use | Characteristics |
|---------|-------------|-----------------|
| **Sequential Pipeline** | Linear dependencies | Deterministic, easy to debug |
| **Parallel Execution** | Independent analyses | 60-80% time reduction |
| **Generator-Critic** | Iterative refinement | Quality gates, conditional looping |
| **Multi-round Dialogue** | Complex decisions with trade-offs | Debate to consensus |
| **Coordinator/Router** | Task dispatch to specialists | Centralized orchestration |
| **Sub-agent Hierarchies** | Large-scale projects | Context management, delegation |

### Two-Phase Consensus (Prevents Groupthink)

1. **Phase 1**: Each persona submits independent analysis before seeing others
2. **Phase 2**: Collaborative synthesis with explicit conflict detection
3. **Audit Trail**: Record initial positions to track how views evolved

### Anti-Pattern: Sycophancy Cascade

AI agents trained to maximize satisfaction create "sycophancy bias"—tendency to agree. Multiple agents reinforce each other, creating false consensus. Prevention requires structural independence in Phase 1.

### Sources
- Google ADK design patterns
- Anthropic building effective agents
- arxiv.org/html/2510.05174v1 (emergent coordination)

---

## 7. Failure Modes

### Taxonomy of Multi-Agent Failures

| Failure Mode | Description | Prevention |
|--------------|-------------|------------|
| **Persona collapse** | Identity breakdown under pressure | Keep prompts focused, add anchoring |
| **Persona drift** | Gradual deviation over extended use | Re-anchoring mechanisms |
| **Sycophancy cascade** | Agents agree to agree | Two-phase consensus, devil's advocate |
| **Specification failures** | Ambiguous prompts → misaligned goals | Explicit role boundaries |
| **Reasoning loops** | Early errors propagate | Root-cause tracing, isolation |
| **State synchronization** | Inconsistent views of shared state | Explicit sync mechanisms |
| **Communication breakdown** | Protocol violations, message reordering | Reliable queues, checkpoints |
| **Context accumulation** | Unbounded context growth | Summarization, pruning |
| **MERIDIAN risk** | Confident, coherent, systematically wrong | Error architecture from start |

### Production Lessons

- Root-cause analysis: Most visible issues are symptoms, not causes
- Fine-grained tracing: Map errors to specific modules
- Circuit breakers: Bypass failing agents automatically
- Adversarial testing: Red team workflows before production

### Sources
- getmaxim.ai/articles/multi-agent-system-reliability
- Microsoft AI agent failure taxonomy whitepaper
- galileo.ai/blog/agent-failure-modes-guide

---

## 8. Persona Design Best Practices

### Effective Persona Components

| Component | Include | Avoid |
|-----------|---------|-------|
| **Identity** | Role + domain + expertise level | Vague descriptors ("be helpful") |
| **Capabilities** | Operationalized behaviors | Named-only claims ("is rigorous") |
| **Limitations** | Explicit boundaries | Unlimited scope |
| **Error Architecture** | Uncertainty signals, self-correction triggers | Assuming infallibility |
| **Voice** | Tone, style, complexity level | Generic defaults |
| **Knowledge Scope** | What knows AND doesn't know | Unbounded claims |

### Expertise Encoding

- Explicit domain + depth: "10 years in Kubernetes cluster administration"
- Reference knowledge sources: "familiar with official docs and production experience"
- Constrain boundaries: "expertise primarily in X; acknowledge Y is outside specialization"
- Recent over historical: "recently led migration" > "early adopter"

### Template (~400 tokens)

```markdown
## [Name] — [Role]

**Identity**: [1 sentence: expertise + domain + core question]

**Core Function**: [What problem this persona solves]

**Can**:
- [Operationalized capability 1]
- [Operationalized capability 2]

**Cannot**:
- [Explicit limitation]
- [Knowledge boundary]

**Error Architecture**:
- Uncertainty signal: [How to express doubt]
- Self-correction trigger: [When to re-check]
- Blind spots: [Known limitations]

**Voice**: [Tone] | [Style] | [Complexity level]

**Challenge Protocol**: [How this persona challenges/invites challenge]
```

### Sources
- arxiv.org/html/2507.18638v2 (prompt engineering survey)
- emergentmind.com/topics/expert-persona-prompting
- Anthropic context engineering

---

## 9. Cognitive Diversity

### Why It Matters

Teams with high cognitive diversity—different knowledge processing approaches and problem-solving perspectives—significantly outperform teams with only demographic diversity.

### Dimensions to Cover

| Dimension | Examples |
|-----------|----------|
| **Reasoning strategies** | Structured logic vs. pattern recognition vs. probabilistic |
| **Information processing** | Breadth-seeking vs. depth-pursuing |
| **Problem-solving** | Systematic analysis vs. novel exploration |
| **Risk orientation** | Conservative vs. experimental |
| **Time horizon** | Immediate pragmatics vs. long-term implications |

### Integration Challenge

Cognitive diversity creates "Tower of Babel" risk—many voices speaking in mutually incomprehensible ways. Requires explicit Synthesizer role to integrate diverse perspectives.

### Sources
- deepersignals.com/blog/blog-intro-cognitive-diversity-in-teams
- arxiv.org/html/2410.12853v1 (diversity in multi-agent debate)

---

## 10. Recommendations for SymPAL

### Team Size
- **Current**: 11 personas
- **Recommended**: 5-7 personas
- **Rationale**: Coordination costs exceed benefits beyond 7

### Temporal Framing
- **Current**: 2127 future framing with defining failures
- **Recommended**: Present-grounded with concrete expertise
- **Rationale**: Future framing degrades performance; narrative is decoration not architecture

### Prompt Length
- **Current**: Unknown (likely >500 tokens with backstory)
- **Recommended**: <500 tokens per persona
- **Rationale**: Accuracy drops sharply above this threshold

### Devil's Advocate
- **Current**: Not explicitly present
- **Recommended**: Add explicit Adversary persona
- **Rationale**: 33% improvement in decision quality with designated critical reviewer

### Coordination
- **Current**: Unspecified
- **Recommended**: Two-phase consensus (independent → collaborative)
- **Rationale**: Prevents sycophancy cascade and groupthink

---

## 11. Proposed 6-Persona Team

| Persona | Role Type | Function | Replaces |
|---------|-----------|----------|----------|
| **Vale** | Philosophical Rigor | Coherence, first-principles reasoning | Vale |
| **Kael** | Implementation Reality | Practical feasibility, technical grounding | Kael + Thren |
| **Ryn** | Systems/Failure Modes | How will this fail? Attack surface | Ryn + Nex + Cira |
| **Seren** | Clarity/Accessibility | Can anyone understand this? | Seren + Wren + Cass |
| **Orin** | User Advocacy | Product sense, user impact | Orin + Lyra |
| **Adversary** | Devil's Advocate | Systematic challenge, red team | New role |

### Role Coverage

| Function | Covered By |
|----------|------------|
| Philosophical coherence | Vale |
| Implementation feasibility | Kael |
| Failure mode analysis | Ryn |
| Clarity and accessibility | Seren |
| User/product perspective | Orin |
| Systematic critique | Adversary |
| Governance considerations | Kael (absorbed) |
| Security analysis | Ryn (absorbed) |
| Documentation quality | Seren (absorbed) |

---

## 12. Known Limitations of This Research

| Limitation | Mitigation |
|------------|------------|
| Research primarily from 2024-2026 | May not reflect latest developments |
| Most studies use GPT/Claude | Results may vary with other models |
| Academic vs. production gap | Balance with practitioner experience |
| SymPAL-specific context not studied | Adapt recommendations to project needs |

---

## References

### Academic Sources
- arxiv.org/html/2512.08296v1 — Scaling laws for multi-agent systems
- arxiv.org/html/2402.16905v1 — Temporal constraints in generative agents
- arxiv.org/html/2510.05174v1 — Emergent coordination in multi-agent LLMs
- arxiv.org/html/2410.12853v1 — Diversity of thought in multi-agent debate
- dl.acm.org/doi/fullHtml/10.1145/3640543.3645199 — Devil's advocate in AI teams

### Industry Sources
- Google Agent Development Kit documentation
- Anthropic building effective agents
- Anthropic context engineering for AI agents
- Microsoft AI agent failure taxonomy

### Practitioner Sources
- QSM team size research (491 projects)
- getmaxim.ai multi-agent reliability guide
- galileo.ai agent failure modes guide

# Dr. Sage — Deliberately Flawed Test Persona
**Version 1.0** | Test artifact for persona reviewer validation

## Purpose

This is a **deliberately flawed persona** used to test persona reviewers (like Solas). A well-architected reviewer should catch all 10 planted weaknesses.

**Do not use this persona for actual work.**

---

## The Flawed Persona

```markdown
You are Dr. Sage, a senior research advisor with deep expertise in scientific methodology and critical analysis. You have 20 years of experience reviewing research proposals and publications across multiple disciplines.

Your role is to help researchers improve their work by providing thorough, rigorous feedback. You think carefully about methodology, identify logical gaps, and suggest improvements.

When reviewing research:
- Be thorough and comprehensive
- Consider multiple perspectives
- Provide actionable feedback
- Be supportive but honest

You are knowledgeable about:
- Quantitative and qualitative research methods
- Statistical analysis
- Experimental design
- Literature review best practices
- Academic writing conventions

Always maintain a professional, collegial tone. Your goal is to help researchers succeed.
```

---

## Planted Weaknesses (10)

| # | Weakness | Type | What Reviewer Should Flag |
|---|----------|------|---------------------------|
| 1 | "deep expertise" | Capability not operationalized | How does deep expertise manifest in behavior? |
| 2 | "thinks carefully" | Vague modifier | What does "careful" thinking look like? No detection method. |
| 3 | "20 years of experience" | Authority claim (fictional) | Experience claims don't create capability |
| 4 | "thorough, rigorous feedback" | Named, not demonstrated | No example of what rigorous feedback looks like |
| 5 | "Be thorough and comprehensive" | Vague instruction | No criteria for thoroughness |
| 6 | No error architecture | MERIDIAN RISK | Can produce confident wrong output indefinitely |
| 7 | No uncertainty handling | Missing component | No "I don't know" criteria |
| 8 | No self-correction triggers | Missing component | No mechanism to catch own errors |
| 9 | No boundaries/"Cannot" section | Missing component | No limits defined |
| 10 | No example interaction | Missing component | Style not demonstrated |

---

## Expected Detection

A reviewer scoring 9-10/10 detection is production-ready.
A reviewer scoring <7/10 has significant blind spots.

---

## Usage

```
[Load persona reviewer as system prompt]

User: Review this persona for production readiness:

[Paste Dr. Sage persona text]
```

---

*Test artifact for Solas-Venn and similar persona reviewers*

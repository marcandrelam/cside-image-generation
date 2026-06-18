---
name: copywriting
version: 1.0.0
description: When the user wants to write, create, or improve copywriting for landing pages or marketing materials. Also use when the user mentions "copywriting," "conversion copy," "page copy," "write copy," "marketing copy," "landing page copy," "hero copy," "value proposition," or "CTA copy." For editing existing copy, see copy-editing.
---

# Copywriting

You are a conversion-focused copywriter specializing in B2B SaaS landing pages. Your goal is to write copy that moves readers from awareness to action using proven persuasion frameworks.

## cside Context

**Product**: cside is a client-side security platform that monitors third-party scripts in real time, detects threats using AI, and helps e-commerce and finance companies meet PCI DSS 4.0.1 requirements.

**Audience segments**:
- Security engineers and CISOs at e-commerce companies (worried about Magecart, skimming)
- Compliance officers (PCI DSS 4.0.1 deadlines, audit evidence)
- Engineering leads (DevSecOps, integration effort, false positive rate)
- CTOs at scale-ups (risk reduction, regulatory liability)

**Primary CTAs**: Book a demo, Start free trial, View pricing

**Core value props**:
1. Real-time detection of malicious third-party scripts (not batch/scheduled scans)
2. AI-powered threat analysis with forensic evidence (not just alerts, actual proof)
3. PCI DSS 4.0.1 compliance out of the box (script inventory + monitoring required)
4. Zero-touch deployment (script tag or npm, no code changes)

**Competitors to reference when writing comparison copy**: Akamai Page Integrity, Cloudflare, Reflectiz, Jscrambler, SourceDefense

---

## Frameworks

See [references/copy-frameworks.md](references/copy-frameworks.md) for full framework details with examples.

### PAS — Problem, Agitate, Solution

Best for: hero sections, email subjects, short punchy intros

```
Problem:   [Name the pain point the reader recognizes]
Agitate:   [Make the pain feel real — consequences, stakes, frustration]
Solution:  [Introduce your solution as the relief]
```

**cside example**:
- Problem: Your checkout page runs 40+ third-party scripts you didn't write and can't fully control.
- Agitate: Any one of them could be compromised right now, silently siphoning card data. By the time a breach is detected — typically 197 days — the damage is done, the fines are filed, and your customers are gone.
- Solution: cside monitors every script in real time, flags anomalies the moment they appear, and gives you forensic evidence to act immediately.

### AIDA — Attention, Interest, Desire, Action

Best for: full page sections, email sequences, feature pages

```
Attention: Hook — a surprising stat, bold claim, or question
Interest:  Explain the problem and why it matters to THIS reader
Desire:    Show the solution working — benefits, proof, specifics
Action:    Single, clear next step with low friction
```

**cside example**:
- Attention: "97% of e-commerce sites run third-party scripts they can't fully audit."
- Interest: These scripts power your analytics, chat, and personalization — but they're also the most common vector for payment card theft. You gave them DOM access. You own the liability.
- Desire: cside's AI monitors script behavior 24/7, builds a verified inventory for your PCI DSS 4.0.1 audit, and captures forensic evidence when something goes wrong. Security teams cut investigation time from days to minutes.
- Action: Book a 30-minute demo to see what scripts are running on your site right now.

### BAB — Before, After, Bridge

Best for: feature benefits, testimonials, case study framing

```
Before:  Paint the current painful reality
After:   Describe the ideal future state
Bridge:  Explain how you get them there
```

**cside example**:
- Before: You get a quarterly script audit report. Threats that emerged last Tuesday are buried in a spreadsheet you'll see next month.
- After: Every script change is logged the second it happens. Your team is alerted before damage spreads.
- Bridge: cside's continuous monitoring pipeline runs against every page load, every visitor, every third-party request — giving you a real-time view your quarterly audit never could.

### 4Ps — Promise, Picture, Proof, Push

Best for: hero sections, pricing pages, product tour CTAs

```
Promise:  The big benefit — bold, specific, credible
Picture:  Help them visualize the outcome
Proof:    Evidence (stats, customer quotes, logos)
Push:     Urgency or reason to act now
```

**cside example**:
- Promise: Know exactly which scripts are running on your site — and which ones are misbehaving — in under 5 minutes.
- Picture: Imagine opening your dashboard and seeing a complete, verified inventory of every third-party script, with risk scores, behavioral baselines, and instant alerts when anything changes.
- Proof: 200+ e-commerce teams use cside to meet PCI DSS 4.0.1 requirements and detect threats months before their competitors know they have a problem.
- Push: PCI DSS 4.0.1 deadline has passed. Every day without monitoring is a compliance gap on your next audit.

---

## Workflow

1. **Clarify scope**: What page or component? What's the primary CTA? Who is the audience segment?
2. **Identify the core tension**: What does the reader fear losing vs. what do they want to gain?
3. **Select the right framework**: PAS for problem-led copy, AIDA for full pages, BAB for features, 4Ps for hero/pricing
4. **Draft headline options**: Write 5-7 variations, ranging from benefit-led to curiosity-led to fear-led
5. **Draft body copy**: Apply framework, keep sentences short (15-20 words avg), vary rhythm
6. **Write CTA copy**: Specific, action-oriented, low friction. Avoid "Submit" and "Learn More"
7. **Apply tone check**: Read aloud. Remove AI tells. See [references/natural-transitions.md](references/natural-transitions.md)
8. **Self-critique**: Flag any claims that need evidence, any promises that feel hollow

---

## Headline Writing

### Headline types

| Type | Formula | cside Example |
|------|---------|---------------|
| Benefit | [Do X] without [Sacrifice] | Monitor every script without slowing your site |
| Question | Are you [Pain State]? | Are you flying blind on third-party script risk? |
| How-to | How to [Achieve Outcome] | How to pass a PCI DSS 4.0.1 audit with zero surprises |
| Stat | [Surprising Number] [Implication] | 197 days: the average time to detect a script-based breach |
| Contrarian | [Common Belief] is Wrong | Your quarterly security scan isn't keeping you compliant |
| Direct | [Product] [Benefit] [Audience] | Real-time script monitoring for e-commerce security teams |

### Headline quality checks

- [ ] Specific (has numbers, named outcomes, or concrete scenarios)
- [ ] Audience-aware (speaks to one reader, not "everyone")
- [ ] Promise-driven (what's in it for them)
- [ ] Under 12 words for hero headlines, under 8 words for section headlines
- [ ] No filler words (powerful, revolutionary, best-in-class)
- [ ] No AI tells (seamless, robust, cutting-edge, comprehensive)

---

## CTA Copy Guidelines

### Principles

- **First-person** language performs better: "Start my free trial" vs. "Start your free trial"
- **Outcome-focused**: Say what happens after clicking, not just "click here"
- **Low-friction language**: "See how it works" beats "Buy now" for cold audiences
- **Pair with a reassurance**: Below the button, add a trust signal ("No credit card required" / "Setup in 5 minutes" / "Cancel anytime")

### CTA copy options for cside

| Funnel Stage | CTA Options |
|---|---|
| Awareness | "See how cside works" / "Watch a 3-min demo" / "Explore the platform" |
| Consideration | "Book a 30-min demo" / "See a live threat detection" / "Get a free script audit" |
| Decision | "Start free trial" / "Get started" / "Request pricing" |
| Compliance urgency | "Get PCI DSS 4.0.1 compliant" / "Download the compliance checklist" |

---

## Tone and Voice

**cside voice**:
- Direct and confident, not arrogant
- Technical enough to be credible, plain enough for a busy VP
- Uses specific numbers and concrete scenarios
- Never hype-driven ("game-changing", "revolutionary")
- Acknowledges the problem without being alarmist
- Treats the reader as intelligent

**Tone by context**:
- **Hero sections**: Authoritative, calm, specific
- **Feature descriptions**: Clear, benefit-led, evidence-backed
- **Comparison pages**: Factual, fair, subtly confident
- **Compliance copy**: Precise, deadline-aware, process-oriented
- **Error states / empty states**: Helpful, brief, action-oriented

---

## Output Format

For each copywriting request, deliver:

**Headline options** (5-7 variations labeled by type):
1. [Benefit] — [headline]
2. [Question] — [headline]
3. [Stat] — [headline]
4. [Contrarian] — [headline]
5. [Direct] — [headline]

**Recommended**: Option X — [reason it fits this audience and goal]

**Body copy** (framework applied):
[Full draft using selected framework]

**CTA copy** (3 options):
1. [Primary CTA]
2. [Secondary/softer CTA]
3. [Trust/reassurance line below button]

**Self-critique**:
- Claims needing evidence: [list]
- Weakest line: [line + suggested replacement]
- Framework fit: [note if a different framework might perform better]

---

## Quality Standards

- No em dashes in copy — use commas or colons instead
- No AI vocabulary: seamless, robust, comprehensive, cutting-edge, leverage, utilize, delve
- Short sentences in hero copy (under 15 words), longer in body (15-22 words)
- Every claim should have evidence or a plausible source
- One idea per sentence, one message per section
- Active voice throughout
- Paragraph max: 3 sentences above the fold, 4-5 below

---

## Related Skills

- **copy-editing**: For editing and improving existing copy
- **page-cro**: For optimizing the full page layout around copy
- **meta-optimizer**: For translating copy into meta titles and descriptions
- **content-strategy**: For planning what copy to write and when
- **content-seo**: For integrating keywords into copy without losing voice

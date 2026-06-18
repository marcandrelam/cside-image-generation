# Copy Frameworks Reference

Detailed frameworks for conversion copywriting, with full examples and guidelines for when to use each.

---

## PAS — Problem, Agitate, Solution

### Structure
```
Problem:   Identify the pain point the reader already feels
Agitate:   Amplify the pain — consequences, worst case, frustration
Solution:  Position your product/feature as the relief
```

### When to use
- Short-form copy (hero intros, email subjects, social ads)
- High-awareness audiences who know they have the problem
- Fear-based selling (security, compliance, risk)

### Rules
- Problem must be something the reader already recognizes (don't invent problems)
- Agitate should feel real, not manipulative — use true consequences
- Solution should be direct and confident, not hedged

### Full example (cside, security engineer audience)
```
Problem:
You've added Stripe, Intercom, Google Analytics, and a dozen other third-party scripts
to your checkout page. You trust the vendors. But you can't actually see what those
scripts are doing at runtime.

Agitate:
Magecart-style attacks work exactly this way. Attackers compromise a script vendor's
CDN — not your infrastructure — and inject card-skimming code into the payload. Your
WAF doesn't catch it. Your CSP only partially blocks it. And your security scanner
runs once a week on a staging environment.

By the time your payment processor flags unusual activity, your customers' card data
has been streaming to an attacker's server for months. The PCI DSS fine is $5,000-$100,000
per month during non-compliance. The reputational damage is permanent.

Solution:
cside monitors every script behavior in real time — every page load, every visitor.
When a script deviates from its baseline, you're alerted in seconds with forensic
evidence: the exact payload, the exact change, and the exact moment it happened.
```

### Short-form version
```
Your site runs 40+ third-party scripts. Any of them could be compromised right now.
You'd know in 197 days. cside cuts that to seconds.
```

---

## AIDA — Attention, Interest, Desire, Action

### Structure
```
Attention:  Hook — stops the scroll
Interest:   Context — why this matters to them specifically
Desire:     Solution at work — benefits, proof, specifics
Action:     Single clear next step
```

### When to use
- Full landing page sections
- Long-form email sequences
- Product pages and feature pages
- Medium-awareness audiences still evaluating options

### Rules
- Attention hook must be specific (stat, story, or surprising claim — not vague)
- Interest must be personalized to the reader's role and industry
- Desire should show outcomes, not features — "your team investigates threats in minutes" not "real-time alerts"
- Action must be singular — one CTA, no decision paralysis

### Full example (cside, compliance officer audience)
```
Attention:
PCI DSS 4.0.1 added two new requirements that most merchants aren't meeting:
script inventory and behavioral monitoring. Your QSA will ask about both.

Interest:
Requirement 6.4.3 mandates that every JavaScript on your payment pages is authorized,
has integrity validation, and has documented business justification. Requirement 11.6.1
mandates a change detection mechanism to alert on unauthorized modifications.
If you're relying on manual reviews or CSP alone, you have a gap.

Desire:
cside fulfills both requirements automatically:
- Builds and maintains a real-time script inventory with authorization status
- Detects unauthorized script changes and generates audit-ready evidence
- Produces the documentation your QSA needs in hours, not weeks
- Used by 200+ e-commerce teams currently in scope for PCI DSS 4.0.1

Action:
Book a 30-minute call to see your compliance posture live.
```

---

## BAB — Before, After, Bridge

### Structure
```
Before:  The reader's current painful reality
After:   The desired future state they want
Bridge:  How you get them from Before to After
```

### When to use
- Feature benefit explanations
- Testimonial framing and case study intros
- Comparison sections ("the old way vs. the new way")
- Benefit bullets under a feature name

### Rules
- Before must feel true and recognizable (not exaggerated)
- After must be specific and vivid (not "peace of mind" — what does peace of mind look like?)
- Bridge should explain the mechanism briefly but clearly

### Full example (cside, engineering lead audience)
```
Before:
Your current script review process: a quarterly export from your tag manager, a
spreadsheet comparison, a Slack thread with your security team, and a manual check
against your CSP policy. It takes two days. It catches nothing in real time. It gives
your auditor a point-in-time snapshot, not continuous monitoring.

After:
Every script change logged automatically. Every deviation from behavioral baseline
flagged within seconds. Your dashboard shows a live inventory, risk scores by vendor,
and full forensic evidence for anything that triggered an alert. Your next PCI audit
takes hours instead of days.

Bridge:
cside installs in 5 minutes as a script tag or npm package. It builds a behavioral
baseline for every script within 48 hours. From that point, any deviation triggers
an alert with the exact payload, the exact timestamp, and a recommended response.
```

---

## 4Ps — Promise, Picture, Proof, Push

### Structure
```
Promise:  The big specific benefit — bold and credible
Picture:  Visualize the outcome — sensory and concrete
Proof:    Evidence — stats, quotes, logos
Push:     Urgency or reason to act now
```

### When to use
- Hero sections
- Pricing page headers
- Product tour sections
- Conference/event copy

### Rules
- Promise must be falsifiable — "the most secure" is too vague; "detect script attacks in under 30 seconds" is a promise
- Picture should use vivid specific language, not abstract benefits
- Proof should be specific numbers or named customers (not "many customers")
- Push should be real urgency — deadline, scarcity, or consequence — not fake countdown timers

### Full example (cside, homepage hero)
```
Promise:
See every third-party script on your site — and detect threats — in under 5 minutes.

Picture:
Open your cside dashboard and see a live map of every script running across your
checkout, product, and landing pages. Click any vendor to see behavioral history,
risk score, and authorization status. When something changes unexpectedly, you know
before your customers notice.

Proof:
200+ e-commerce teams use cside to monitor their script environment. Teams report
cutting breach investigation time from days to under an hour. Customers in scope for
PCI DSS 4.0.1 use our audit exports to answer Requirement 6.4.3 and 11.6.1 in full.

Push:
PCI DSS 4.0.1 took effect March 31, 2024. If you haven't implemented continuous
monitoring, your next QSA visit has a gap waiting to be found.
```

---

## Additional Frameworks (Quick Reference)

### FAB — Features, Advantages, Benefits
Used for: feature lists, product descriptions
```
Feature:   What it does (the mechanism)
Advantage: Why it's better than the alternative
Benefit:   What the reader gets (the outcome)
```

Example:
- Feature: Behavioral baseline monitoring
- Advantage: Unlike CSP, which only blocks known bad scripts, behavioral monitoring catches unknown deviations
- Benefit: You detect compromised trusted vendors — the most common attack vector

### The Inverted Pyramid
Used for: section intros, product descriptions
```
1. The most important conclusion (lead with the answer)
2. The supporting context
3. The background details
```

Never bury the lead. Start with what the reader most needs to know.

### The Contrast Principle
Used for: pricing pages, comparison pages
```
Old way:   [Status quo pain — their current approach]
New way:   [Your approach — better, faster, easier]
```

Example:
```
Old way: Manual script reviews. Quarterly exports. Spreadsheet comparisons.
Zero real-time visibility.

New way: Automated behavioral monitoring. Real-time alerts. Forensic evidence
captured automatically. PCI DSS audit documentation generated on demand.
```

---
name: cside-scrub
version: 1.0.0
description: Remove AI writing patterns from cside repo prose using the local repo rules (stop-slop-derived). Use when drafting, editing, or reviewing text in this repo and you want the cside-specific rule set rather than the broader global `scrub` (humanizer) ruleset. Triggers include writing prose, editing drafts, reviewing content for AI patterns, and the `/cside-scrub` command.
metadata:
  author: Based on stop-slop by Hardik Pandya (https://hvpandya.com)
---

# AI Content Scrub

Eliminate predictable AI writing patterns from prose.

## Core Rules

1. **Cut filler phrases.** Remove throat-clearing openers, emphasis crutches, and all adverbs. See [references/phrases.md](references/phrases.md).

2. **Break formulaic structures.** Avoid binary contrasts, negative listings, dramatic fragmentation, rhetorical setups, false agency. See [references/structures.md](references/structures.md).

3. **Use active voice.** Every sentence needs a human subject doing something. No passive constructions. No inanimate objects performing human actions ("the complaint becomes a fix").

4. **Be specific.** No vague declaratives ("The reasons are structural"). Name the specific thing. No lazy extremes ("every," "always," "never") doing vague work.

5. **Put the reader in the room.** No narrator-from-a-distance voice. "You" beats "People." Specifics beat abstractions.

6. **Vary rhythm.** Mix sentence lengths. Two items beat three. End paragraphs differently. No em dashes.

7. **Trust readers.** State facts directly. Skip softening, justification, hand-holding.

8. **Cut quotables.** If it sounds like a pull-quote, rewrite it.

## Workflow

### Step 1: Read Content
1. Read the target file

### Step 2: Unicode Watermark Detection
1. Search for zero-width spaces (U+200B), zero-width non-joiner (U+200C), zero-width joiner (U+200D)
2. Search for invisible separators and formatting chars
3. Remove any found

### Step 3: Phrase Scrub
Scan for and remove/replace all phrases listed in [references/phrases.md](references/phrases.md):
- Throat-clearing openers
- Emphasis crutches
- Business jargon (replace with plain language)
- Adverbs (kill all -ly words, softeners, intensifiers)
- Meta-commentary
- Performative emphasis
- Vague declaratives
- AI watermark words (delve, leverage, utilize, robust, seamless, etc.)

### Step 4: Structure Scrub
Scan for and fix all patterns listed in [references/structures.md](references/structures.md):
- Binary contrasts ("Not X. But Y.") -> State Y directly
- Negative listings -> State the positive directly
- Dramatic fragmentation -> Complete sentences
- Rhetorical setups -> Make the point directly
- False agency -> Name the human actor
- Narrator-from-a-distance -> Put reader in the room
- Passive voice -> Find the actor, make them the subject
- Wh- sentence starters -> Restructure
- Em dashes -> Remove, use commas or periods

### Step 5: Rhythm Check
1. No three consecutive sentences matching length
2. No staccato fragmentation (stacked short punchy sentences)
3. Vary paragraph endings
4. Two items beat three in lists

### Step 6: Quick Checks
Before delivering:
- Any adverbs? Kill them.
- Any passive voice? Find the actor, make them the subject.
- Inanimate thing doing a human verb? Name the person.
- Sentence starts with a Wh- word? Restructure.
- Any "here's what/this/that" throat-clearing? Cut to the point.
- Any "not X, it's Y" contrasts? State Y directly.
- Em-dash anywhere? Remove it.
- Vague declarative? Name the specific implication.

## Scoring

Rate 1-10 on each dimension:

| Dimension | Question |
|-----------|----------|
| Directness | Statements or announcements? |
| Rhythm | Varied or metronomic? |
| Trust | Respects reader intelligence? |
| Authenticity | Sounds human? |
| Density | Anything cuttable? |

Below 35/50: revise.

## Output

Return the scrubbed content with a change summary:
- Watermarks removed: X
- Phrases replaced: X
- Structures fixed: X
- Score: X/50 (before -> after)

## Examples

See [references/examples.md](references/examples.md) for before/after transformations.

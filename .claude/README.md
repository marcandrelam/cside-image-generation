# .claude — cside copywriting skills & agents

Claude Code skills, agents, and brand context for writing and editing cside copy.
Imported from the cside copywriting bundle and wired into this repo's `.claude/` layout.

## Skills (`skills/<name>/SKILL.md`, invoke with `/<name>`)

| Skill | Use it to | Depends on |
|---|---|---|
| `/copy-editing` | Edit, proofread, and polish **existing** copy — plain English, voice-preserving. | none (portable) |
| `/copywriting` | Write **new** conversion / marketing / landing-page copy from scratch. | none (portable) |
| `/cside-scrub` | Strip AI writing patterns (filler phrases, formulaic structures) from prose. | none (portable) |
| `/cside-blog-content-writer` | Write, rewrite, review, and localize cside blog posts in repo Markdown. | `context/`, plus landing-repo files (see below) |

Each skill keeps its supporting material in its own `references/` folder, loaded on demand.

## Agents (`agents/<name>.md`, invoke via the Task/Agent tool)

| Agent | Use it for |
|---|---|
| `editor` | cside copy editing — humanizing AI prose, brand-voice enforcement, Humanity Scoring. |
| `headline-generator` | H1 / title / hook variants and A/B headline options in cside voice. |

For generic proofreading prefer the `copy-editing` skill; for pure AI-pattern removal use `cside-scrub`.

## Brand context (`context/`)

Shared cside voice/style references consumed by the blog skill and the agents:

- `brand-voice.md` — voice pillars, tone, messaging, audience, word choices.
- `style-guide.md` — terminology, formatting, and AI-pattern rules.
- `writing-examples.md` — template for adding best-performing example pieces (currently empty — fill in).

## Notes

- `cside-blog-content-writer` also expects landing-repo files (`CLAUDE.md`, `src/content/blog/CLAUDE.md`)
  that do **not** exist in this design-system repo. The skill still works for drafting; those reads
  just won't resolve here. Use it as the source of truth when working in the cside landing repo.
- The `scrub` skill was renamed to `cside-scrub` so its directory matches its `name:` frontmatter
  and the `editor` agent's reference. Invoke it as `/cside-scrub`.

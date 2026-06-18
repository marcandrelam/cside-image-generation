# CLAUDE.md

Entry map for this repo. Read this first, then the file relevant to your task.

This is a **cside Design System handoff bundle** from Claude Design (claude.ai/design):
HTML/CSS/JS prototypes plus the skills to design and write in the cside language.
cside is a client-side security platform. Tagline: "Security for what runs in the browser."
Brand name is lowercase `cside` — never `C/Side`, `CSide`, `C-Side`, or `Cside`.

## Where to go

| Your task | Start here |
|---|---|
| Implement / recreate the designs | [`README.md`](README.md) — handoff instructions for coding agents |
| Design a page, deck, or artifact in the cside language | [`project/cside-design-skill.md`](project/cside-design-skill.md) — the design guide; load `project/tokens.css` in every artifact |
| Write new marketing / landing-page copy | skill `/copywriting` |
| Edit, proofread, or polish existing copy | skill `/copy-editing` |
| Strip AI writing patterns from prose | skill `/cside-scrub` |
| Write or review a cside blog post (repo Markdown) | skill `/cside-blog-content-writer` |
| Humanize prose, enforce brand voice, score humanity | agent `editor` |
| Generate headline / title / hook variants | agent `headline-generator` |

## Layout

- `project/` — design system: `cside-design-skill.md`, `tokens.css`, `ui-kit.html`, HTML prototypes, `assets/`, `fonts/`, `previews/`.
- `.claude/` — copywriting/editing skills (`skills/`), agents (`agents/`), and cside brand context (`context/`). See [`.claude/README.md`](.claude/README.md).

## Conventions

- Voice: professional, technical, calmly confident; plain English; active voice; short paragraphs. No alarmism, no em dashes in body copy.
- The design medium is HTML/CSS/JS prototypes — match the visual output, don't copy prototype internals. Don't render or screenshot unless asked.
- When in doubt about scope, ask before implementing.

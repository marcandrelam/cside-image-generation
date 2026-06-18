# CODING AGENTS: READ THIS FIRST

This is a **handoff bundle** from Claude Design (claude.ai/design).

A user mocked up designs in HTML/CSS/JS using an AI design tool, then exported this bundle so a coding agent can implement the designs for real.

## What you should do — IMPORTANT

**Read `project/cside-design-skill.md` top to bottom** — it is the primary design file (brand, type, color, component recipes, voice). Then **follow its imports**: open every file it pulls in (`project/tokens.css`, `project/ui-kit.html`, assets, fonts) so you understand how the pieces fit together before you start implementing.

For **writing and editing copy** (landing pages, blog posts, headlines, proofreading), use the skills and agents in `.claude/` — see [`.claude/README.md`](.claude/README.md).

**If anything is ambiguous, ask the user to confirm before you start implementing.** It's much cheaper to clarify scope up front than to build the wrong thing.

## About the design files

The design medium is **HTML/CSS/JS** — these are prototypes, not production code. Your job is to **recreate them pixel-perfectly** in whatever technology makes sense for the target codebase (React, Vue, native, whatever fits). Match the visual output; don't copy the prototype's internal structure unless it happens to fit.

**Don't render these files in a browser or take screenshots unless the user asks you to.** Everything you need — dimensions, colors, layout rules — is spelled out in the source. Read the HTML and CSS directly; a screenshot won't tell you anything they don't.

## Bundle contents

- `README.md` — this file
- `CLAUDE.md` — agent entry point / map of the repo
- `project/` — the `cside Design System` files: `cside-design-skill.md` (the design guide), `tokens.css`, `ui-kit.html`, HTML prototypes, assets, fonts, previews
- `.claude/` — copywriting & editing skills, agents, and cside brand-voice context

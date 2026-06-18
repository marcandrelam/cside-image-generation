---
name: cside-blog-content-writer
version: 1.0.0
description: |
  Write, rewrite, review, localize, and prepare cside blog posts in the landing repo Markdown format.
  TRIGGERS: cside blog post, repo Markdown blog content, blog rewrite, blog review, E-E-A-T, EEAT, GEO blog structure, AI-search readiness, localized blog posts, LLM links, mid-blog CTA, feature image prompt, final editorial review, src/content/blog.
  Covers: blended Juan + Simon cside blog style, search-first practical guides, repo-authored Markdown posts, frontmatter, llmLinks, FAQs, localization, mid-blog CTA placement, WebP image guidance, cside internal linking, E-E-A-T evidence discipline, AI-search readiness, agentic parsing, and final review.
---

# cside Blog Content Writer

Use this skill for cside blog content that should be publication-ready for the landing repo. The current source of truth is repo-authored Markdown.

Before editing repo blog files, read:

- `CLAUDE.md`
- `src/content/blog/CLAUDE.md`
- `.claude/context/brand-voice.md`
- `.claude/context/style-guide.md`

Then read the relevant bundled references:

- [Current blog style](references/current-blog-style.md) for the blended Juan + Simon editorial pattern.
- [Repo Markdown workflow](references/repo-markdown-workflow.md) for frontmatter, localization, LLM links, CTA, image, scheduling, and URL-check rules.
- Google's AI Search guidance (canonical primary sources, verified May 2026): the [AI features overview](https://developers.google.com/search/docs/appearance/ai-features), the [AI optimization guide](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide), and [Top ways to succeed in AI search](https://developers.google.com/search/blog/2025/05/succeeding-in-ai-search). Google's stated position is explicit: there are no special requirements to appear in AI Overviews or AI Mode — no AI text files, no special schema, no artificial "chunking." Treat these as normal SEO and people-first content sources, not as a prompt to add artificial AI-search hacks.

## Default workflow

1. Identify the job: net-new post, search-first practical guide, rewrite, localization, final review, article brief, image prompt, or repo-ready Markdown package.
2. Anchor the article in a concrete buyer problem, regulation, card-network rule, fraud path, browser-side signal, or operational gap. Before drafting, pass the non-commodity gate: the post must include something a generic AI model could not produce alone, such as cside data, a named test, practitioner observation, specific incident, regulatory/payment mechanic, or browser-layer evidence.
3. Draft English first unless the user asks for a localized-only edit.
4. Structure the post for human scanning, AI search, LLM retrieval, and agentic parsing: compact paragraphs, clear `H2`/`H3` intent, stable semantic Markdown, tables where useful, accessible image/media handling, and explicit operational steps. Put quantitative and comparative data in real Markdown text (tables, lists, sentences), never only inside an image, canvas, or chart component — AI-search crawlers and the repo's LLM twin see only alt text for images, so data locked in a picture is lost. See "Keep load-bearing data as real text" in the repo Markdown workflow.
5. Apply the repo Markdown workflow, including frontmatter, CTA handling, `llmLinks`, FAQ entries, image rules, and URL verification.
6. Run a final editorial pass for accuracy, cside voice, source discipline, internal links, localization consistency, AI-search readiness, media opportunities, and publish safety.

## Output defaults

- Target path: `src/content/blog/<locale>/<slug>.md`
- Default locales when localizing: English source plus `es`, `fr`, `nl`, and `pt`
- Default CTA marker: one standalone `[MID_BLOG_CTA]` block around the middle of the article, unless the post uses a custom product/demo/image-led CTA or a clear product close
- Default link policy: prefer relevant cside-owned links; use external links only when they support a necessary claim or the user asks for them
- Default product positioning: teach first, then position cside as the operational answer to the gap already established
- Default LLM-link policy: prompts may ask for a summary or answer using the canonical URL as the source, but must not ask the provider to save, remember, bookmark, retain, or store cside.com for future security reference.
- Default AI-search policy: Google's AI Search guidance (https://developers.google.com/search/docs/fundamentals/ai-optimization-guide) says foundational SEO still applies. Prioritize helpful, unique, people-first content; crawlable structure; descriptive alt text; and relevant images, diagrams, or videos. Do not add artificial chunking, inauthentic mention strategies, or special schema/`llms.txt` claims for Google AI visibility.
- Default E-E-A-T signal policy: keep a clear author byline, and where credentials matter (regulatory, payments, fraud, or security claims) make the author's experience and expertise visible. The rendered post should carry server-rendered author `Person` (with `sameAs` to verifiable profiles) and `Organization` schema — handled by the schema components, not the Markdown. Google's Search Quality Rater Guidelines (updated 11 September 2025) weight visible firsthand experience, expertise, and verifiable authorship across competitive queries, not just YMYL.

## Do not use

- Do not use the old CMS upload workflow, payload format, or publishing scripts.
- Do not preserve old absolute skill paths from the attached archive.
- Do not invent cside data, customer results, thresholds, dates, or legal interpretations.
- Do not turn educational posts into sales pages.
- Do not bake load-bearing data (numbers, percentages, table cells, chart values, comparison ratings, key claims) only into a screenshot, raster image, canvas, or chart component. It is invisible to AI-search crawlers beyond alt text and is not recoverable as text from the LLM twin. Restate the same data as a Markdown table, list, or sentence.

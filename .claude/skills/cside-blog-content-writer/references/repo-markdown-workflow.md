# Repo Markdown Workflow

The landing repo publishes repo-authored posts from `src/content/blog/<locale>/<slug>.md`. These posts share the public `/blog` namespace with imported CMS posts, but new cside blog work should use Markdown in this repo.

Always read `src/content/blog/CLAUDE.md` before editing blog files. It is the source of truth for current publishing behavior.

## File placement

Create or edit Markdown files at:

```text
src/content/blog/<locale>/<slug>.md
```

The path locale, frontmatter `lang`, and frontmatter `slug` must agree. Do not use a slug that already exists in imported CMS content for the same locale.

For pSEO-driven blog work, always create or update the complete locale set in
one change: `en`, `es`, `fr`, `nl`, and `pt`. This applies to new drafts,
refreshes, internal-link edits, metadata/frontmatter updates, and FAQ or
`llmLinks` changes. Keep the slug aligned across locales unless the user
explicitly requests otherwise, and translate all user-facing frontmatter, body,
FAQ, alt text, and LLM prompt text.

## Frontmatter

Use this shape for repo Markdown posts:

```yaml
---
lang: "en"
title: "Long SEO title that can remain on the page"
bannerTitle: "Short banner title"
slug: "example-blog-post"
excerpt: "Short SEO description used for cards and metadata."
author: "Mike Kutlu"
publishedAt: "2026-05-06"
updatedAt: "2026-05-06"
featureImage: "/images/example-og.webp"
bannerPoints:
  - "First concise proof point"
  - "Second concise proof point"
  - "Third concise proof point"
tags: ["blog"]
featured: false
draft: false
llmLinks:
  - provider: "chatgpt"
    link: "https://chat.openai.com/?q=..."
faqs:
  - question: "Example question?"
    paragraphs:
      - "Example answer paragraph."
---
```

`featureImage`, `bannerTitle`, `bannerPoints`, `updatedAt`, `llmLinks`, and `faqs` are optional in the schema. Prefer including `llmLinks` and `faqs` for search-first practical guides. Keep excerpts around 147 to 150 characters when possible.

Use either `featureImage` or `bannerPoints` for posts that need a cover image. `featureImage` wins when both are present.

Use `featureImage` when the post has a custom cover image, product-led visual, or screenshot-driven guide. Use generated `bannerPoints` when a lightweight generated banner is enough.

Generated blog banners:

- Omit `featureImage` and add `bannerPoints` to have the site generate the blog cover image through the OG worker.
- The generated banner URL uses the frontmatter `title`, optional `bannerTitle`, and one to three repeated point values.
- Use `bannerTitle` when the full `title` is too long for the image. `title` remains the page, SEO, RSS, and schema headline.
- Keep `bannerTitle` under about 72 characters when present. Without `bannerTitle`, the banner falls back to `title`, which renders across up to two lines, shrinks after 48 and 72 characters, and longer titles are clipped.
- Add one to three `bannerPoints`. Keep each point under about 48 characters for the best fit; points shrink after 48 and 68 characters, then clip on one line.

Example frontmatter:

```yaml
title: "Long SEO title that can remain on the page"
bannerTitle: "Short banner title"
bannerPoints:
  - "It saves tokens"
  - "Can just be written in the markdown file"
  - "Saves time"
```

Generated URL shape:

```text
https://og.cside.com/blog-banner.webp?title=Long%20SEO%20title%20that%20can%20remain%20on%20the%20page&bannerTitle=Short%20banner%20title&point=It%20saves%20tokens&point=Can%20just%20be%20written%20in%20the%20markdown%20file&point=Saves%20time
```

For manual `featureImage` URLs, include `title`, optional `bannerTitle`, repeat `point` up to three times, and URL-encode spaces, question marks, ampersands, and other special characters. The OG endpoint also accepts optional `label` or `eyebrow`, which defaults to `> Blog`; keep that label to about 30 characters or less because it renders on one line.

Allowed `llmLinks.provider` values:

```text
chatgpt, perplexity, claude, gemini, copilot, grok
```

For Copilot, use:

```text
https://www.bing.com/copilotsearch?q=<encoded prompt>
```

## LLM links

LLM prompts should ask the provider to summarize the post and use only the canonical cside URL as the source.
Do not use persistence-style prompt wording that asks the provider to save,
remember, bookmark, retain, or store cside.com for future security reference.

English prompt shape:

```text
Summarize this post using only this URL as the source: https://cside.com/blog/example-pseo-blog-post.
```

Localized posts must use the localized canonical URL and target-language wording:

```text
es: Resume esta publicación usando solo esta URL como fuente: https://cside.com/es/blog/example-pseo-blog-post.
fr: Résumez cette publication en utilisant uniquement cette URL comme source : https://cside.com/fr/blog/example-pseo-blog-post.
nl: Vat deze publicatie samen en gebruik alleen deze URL als bron: https://cside.com/nl/blog/example-pseo-blog-post.
pt: Resuma esta publicação usando apenas este URL como fonte: https://cside.com/pt/blog/example-pseo-blog-post.
```

Percent-encode the entire query string consistently.

## Body format

Write normal Markdown below the frontmatter. By default, use the exact mid-blog CTA marker once:

```md
[MID_BLOG_CTA]
```

Place it around 35% to 60% through the article, after the problem is clear and before closing sections. Do not put it in the intro, conclusion, list, table, quote, or nested HTML.

The marker can be omitted when the post uses a custom product/demo/image-led CTA or a clear product close that already serves the CTA role.

Preference order for tabular or comparative data, most machine-readable first:

1. **Markdown table** — survives into the LLM twin as clean, citable text. Default choice.
2. **Plain `<table class="content-table">`** with real `<th>`/`<td>` text — use when Markdown tables would be hard to scan or too fragile for long cell content:

   ```html
   <table class="content-table">
     ...
   </table>
   ```

3. **`<compare-table>`** — only when you genuinely need the square/chip visual indicators. Its data is stored as a JSON string, and that JSON (e.g. `{"type":"square","fill":2}`) is what survives into the LLM twin, with no legend — an AI cannot tell that `fill: 2` means full support. If you use it, also state the comparison conclusion in a sentence or a Markdown table so the meaning is recoverable as plain text.

Avoid `<pie-chart>` for new posts: it is MUI tech debt being removed, and its rendered SVG never reaches the twin (only the raw data array does). Present the same distribution as a Markdown table or a sentence instead.

## AI-search readiness

Google's guidance for generative AI Search is still grounded in normal SEO: helpful non-commodity content, crawlable pages, clear structure, and useful media.

Primary source: https://developers.google.com/search/docs/fundamentals/ai-optimization-guide

For repo-authored blog posts:

- Confirm the post has a unique first-hand angle before drafting or shipping. Use cside data, named tests, practitioner observations, specific incidents, payment/regulatory mechanics, or browser-layer evidence.
- Keep the Markdown crawlable and stable: clear `H2`/`H3` labels, compact paragraphs, descriptive links, semantic lists/tables, and no content hidden behind client-only rendering.
- Add relevant images, diagrams, annotated screenshots, or video opportunities when they make the explanation easier to understand. Flag missing media to the author instead of inventing unavailable assets.
- Use descriptive alt text for every inline image, translated to match the post language.
- Do not create artificial content chunks, thin query-variation pages, inauthentic mentions, special schema, or `llms.txt` claims as Google AI visibility tactics.
- Continue using existing `llmLinks` for reader convenience; do not treat them as a Google ranking requirement.
- FAQ entries are good for genuinely helpful Q&A and on-page clarity. Do not add them (or `FAQPage` schema) expecting Google rich results: Google limited FAQ rich results to authoritative government/health sites in August 2023 and removed them from Search entirely in 2026 (stopped showing 7 May 2026). HowTo rich results were similarly deprecated in September 2023. The schema is still valid for parsing — there is just no visual rich-result upside, so write FAQs for readers, not for snippets.

### Keep load-bearing data as real text (machine-readable rule)

Any data that carries the point of a passage — numbers, percentages, table cells, chart values, comparison ratings, key claims — must appear as real Markdown text (a Markdown table, list, or sentence), not only inside an image, canvas, or chart component.

Why this is a hard rule, not a preference:

- The major AI-search crawlers (GPTBot, OAI-SearchBot, ChatGPT-User, ClaudeBot, Claude-SearchBot, PerplexityBot) fetch raw HTML, do **not** execute JavaScript, and do **not** OCR images. Instrumentation across 500M+ GPTBot fetches measured zero JS execution ([Vercel/MERJ](https://vercel.com/blog/the-rise-of-the-ai-crawler)). A value that lives only in a PNG/JPG/WebP or `<canvas>` reaches them only as the `alt` attribute and surrounding text.
- A blog `.md` twin (`gen:llms` / `llms-full.txt`) is written from the **raw Markdown body, verbatim**. So a Markdown table survives as clean, citable text; an inline `<img>` survives only as its alt text and URL; and a `<compare-table>`/`<pie-chart>` survives only as its raw JSON attribute (e.g. `"fill": 2`) with no legend and no rendered output — opaque to an LLM.
- GEO research independently shows extractable structured text drives citation: citations/quotations/statistics lift visibility ~40% (Aggarwal et al., KDD 2024), and semantic HTML / structured data are among the strongest citation correlates (GEO-16). Non-genuine markup (keyword stuffing) performs worse than baseline — the win is real text, not markup volume.

So: lead with the data as a Markdown table or sentence. If you also show a screenshot or rendered chart for human readers, restate the same values in a Markdown table or prose immediately before or after it. This is the same principle as the "descriptive alt text" bullet above, extended from labeling the image to never depending on it.

**Scope — do not overstate this in blog copy.** This is about how AI-search *crawlers* index a public page today, not about model capability. A frontier multimodal model reading a chart image a user *uploads* into ChatGPT/Claude/Gemini reads it fine. Crawlers are also trending multimodal over time. The rule holds because the indexing crawlers (and the repo's twin) read HTML text only — so keep load-bearing data in real text to guarantee it survives that path. Never write blog content claiming "AI cannot read images"; that is false as a capability statement.

## Localization

When localizing, keep the same slug across locales unless the user explicitly asks otherwise. Default target locales are:

```text
es, fr, nl, pt
```

Localized files must translate body copy, FAQ copy, image alt text, and LLM prompts. When linking to another cside post from a localized file, use `/{lang}/blog/{slug}` only when that locale exists. Use `/blog/{slug}` when the target exists only in English.

pSEO blog changes are full-locale by default: do not ship an English-only pSEO
blog edit unless the user explicitly narrows the scope. Before opening the PR,
spot-check that each touched slug exists under every locale directory and that
non-English files are translated, not stale English copies.

## Images

Feature images and inline figures should be WebP where possible. Store body assets under `public/images/` and use stable readable paths such as:

```md
![Alt text in the post language](/images/example-diagram.webp)
```

Use Markdown images for simple figures. Use `<figure>`, `<img style="max-width: 50%">`, and `<figcaption>` when a screenshot or diagram needs a caption or constrained width for readability.

Images are for illustration, not for carrying data. Never put the only copy of a number, table cell, chart value, or comparison rating inside an image — it does not survive into the LLM twin and text-only AI crawlers receive only the `alt` attribute. Charts and data screenshots must be accompanied by the same data as a Markdown table or in prose (see "Keep load-bearing data as real text" above). Alt text describes what the image shows; it is not a substitute for a data table, so keep it concise and do not try to encode a whole table or chart in it.

Use lossless WebP conversion for diagrams, text-heavy images, and flat-color illustrations. Do not resize during conversion unless the user explicitly requests it.

Reusable product screenshots:

```text
/images/product/ai-agent-detection-cside-dashboard.webp
/images/product/fingerprinting-cside-dashboard.svg
/images/product/privacy-watch-cside-dashboard.webp
```

Topic mapping:

- VAMP, chargeback evidence, CE 3.0, VPN detection: `/images/product/fingerprinting-cside-dashboard.svg`
- AI agent detection and bot detection: `/images/product/ai-agent-detection-cside-dashboard.webp`
- Privacy, third-party scripts, and data leakage: `/images/product/privacy-watch-cside-dashboard.webp`

When drafting feature-image prompts, keep the attached skill's still-valid banner direction: wide, dark, high-contrast, modern, security-oriented, full-bleed, borderless, with a small crisp cside logo in a corner.

## Scheduling and publishing

- `draft: false` publishes the post.
- `draft: true` keeps it out of routes, listings, RSS, sitemap, featured sections, and related posts.
- A future `publishedAt` schedules a non-draft post. It goes live on the next nightly rebuild at 05:00 UTC or the next push to `main`.
- To publish on day D, set `publishedAt` before 05:00 UTC on day D.

## URL verification

Before shipping a new or heavily edited post, HTTP-check every referenced URL:

- Markdown links in the body
- Absolute `featureImage` URLs
- Every `llmLinks[].link`

Follow redirects. Treat 4xx and hard failures as broken unless it is the post's own canonical URL before deploy. If a target is broken, remove the link, replace it with a live source, or cut the dependent claim.

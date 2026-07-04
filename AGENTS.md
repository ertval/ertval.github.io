# AGENTS.md — ertval.github.io

Personal portfolio site for `ertval.github.io`. Static HTML+CSS, no build step, shipped via GitHub Pages.

## Layout

```
.commandcode/      # design brief + taste notes (authoritative content source)
  design/brief.md  # design system, voice, anti-references, components
  taste/taste.md   # continuously learned taste notes
docs/index.md      # site spec — identity, narrative, projects, timeline
public/            # deployed artifact, served as-is by GitHub Pages
  index.html       # single page
  styles.css       # tokens + scoped styles, OKLCH, light + dark
.github/workflows/pages.yml   # deploy workflow
```

## Deploy model (non-obvious)

- Deploy source of truth = `public/`. Pages workflow uploads `public/` as the artifact (`pages.yml:31`).
- CI **ignores** `docs/**`, `.commandcode/**`, and all `*.md` on push (`pages.yml:6-8`). Edits to the spec files do **not** trigger a deploy — they are build inputs for the developer, not served content.
- Branching: deploys from `main` only. No preview environments.

## How to ship a change

There is no build step and no test command. Three ordered checks before commit:

1. Edit `public/index.html` and/or `public/styles.css`.
2. Open `public/index.html` in a browser (or `python3 -m http.server -d public` for a quick local check). Verify light + dark (`prefers-color-scheme`) and narrow viewport (`<= 420px`).
3. Cross-check the rendered text against `docs/index.md` — that file is the source of truth for copy. If the page and the spec disagree, the page is wrong.

Do not edit `docs/index.md` to match a code typo. Spec wins; HTML is the implementation.

## Style / content guardrails (lifted from `.commandcode/design/brief.md`)

These are conventions an agent would otherwise break by reflex:

- **No build tooling.** No bundler, no preprocessor, no framework. Plain HTML + one CSS file. Do not introduce `package.json`, npm scripts, Vite, Tailwind, etc.
- **No JS library, no SPA routing.** The page is static. Inline SVG favicon is already data-URL-encoded — do not extract.
- **Design tokens live in `public/styles.css` `:root` and `@media (prefers-color-scheme: dark)` blocks.** Build colour in OKLCH. One accent (`--accent`), near-neutral paper/ink, hairline borders. Do not add new utility layers or component frameworks.
- **Voice:** sparse, technical, sentence case, no exclamation. Concrete words over buzzwords. White space carries weight.
- **Anti-references (don't add):** animated typing, matrix rain, particle backgrounds, snake GIFs, visitor counters, commit-graph widgets, "Trusted by" strips, gradient CTA buttons, long resume-dump timelines, fake testimonials.
- **Featured projects:** max 4, pinned repos as primary proof. Quarterly rotation expected in spec, not in automation.
- **Accessibility:** WCAG AA in both themes, 2–3px visible focus rings, descriptive link text (no icon-only controls), respect `prefers-reduced-motion`, LTR only.

## Repo conventions specific to this codebase

- `docs/index.md` is the **spec**, not documentation. Update it first when copy changes; then mirror into `public/index.html`.
- `.commandcode/design/brief.md` is the **design spec**. Update it before introducing new components or visual patterns, then implement in `public/styles.css`.
- No tests, no lint, no formatter config. The closest thing to a "typecheck" is opening the file in a browser.
- No `.gitignore` is required for the artifact — there is no build output separate from sources. If you ever add a generated dir, ignore it; do not commit it under `public/`.
- Linked URLs in the HTML point to external GitHub repos and contact addresses defined in the spec. If you change contact info, edit both `docs/index.md` and `public/index.html` together.

## What an agent is likely to get wrong without this file

- Assuming there's a build, tests, or deploy pipeline beyond the Pages workflow.
- Editing markdown and expecting a redeploy (it won't fire).
- Reaching for a CSS framework or JS when the constraint is plain HTML+CSS.
- Treating `docs/index.md` as a side-document instead of the canonical content source.
- Inflating the page with SaaS-landing patterns the design brief explicitly rejects.

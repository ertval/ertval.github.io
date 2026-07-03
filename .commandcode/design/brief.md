# Design Brief — ertval.github.io

## Register

**Brand.** Personal portfolio and landing page. The interface is the experience — arrival reaction is the deliverable. A visitor decides in ≤10 seconds whether Ertval is worth contacting.

## Surface

Single-page (or minimal multi-page) portfolio hosted on GitHub Pages at `ertval.github.io`. Currently only `index.md` exists as a content spec — no interface code yet. Design work builds the HTML surface from this brief plus the content spec.

## User

A technical recruiter, founder, or AI-native engineering lead arriving cold. They scan fast, are skeptical of buzzwords, and want proof that this person can ship production-safe agentic systems. They are deciding whether to open a conversation. Secondary: a collaborator exploring shared projects on GitHub.

## Job

Decide. The page is a focused pitch: who Ertval is, what he builds (production-safe agentic AI on real backend infrastructure), proof it works (pinned repos, hackathon win), and one dominant action — contact.

Secondary work patterns:
- **Explore** — featured projects as scannable proof-of-work, GitHub as primary evidence.
- **Learn** — narrative sections that explain architectural philosophy (bounded autonomy) without lecturing.

## Artifact

Featured GitHub repositories and a hackathon win are the proof objects. The status bar (current role, recent win) is the live-signal artifact. Links to pinned repos are the primary evidence, not commit graphs or stats widgets.

## Voice

Confident, technical, sparse. "Bounded autonomy" as a through-line — the page itself should feel disciplined the way the architecture is: freedom within deliberate gates. Minimal copy, no marketing preamble, no exclamation, sentence case. White space carries weight. The page reads like a senior engineer's commit message, not a SaaS landing page.

Concrete physical words: quiet, precise, load-bearing, bounded, durable, sharp.

## Anti-references

- No animated typing effects, matrix rain, snake GIFs, particle backgrounds.
- No visitor counters, commit-graph flex widgets, or stat dumps.
- No resume-dump experience blocks (timeline stays tight, not a wall of rows).
- No generic SaaS cream-and-purple, no blue-violet gradient CTAs.
- No card grids for the sake of cards — only featured projects are card-shaped.
- No centered hero trio as a reflex (centered headline + sub + two CTAs) unless it earns the center.
- No "Trusted by" logo strips, no fake testimonials, no "Get started today" energy.

## Design Principles

1. **Proof over claims.** Pinned repos and the hackathon win do the convincing. Words describe philosophy; links show implementation.
2. **White space > density.** The page breathes. A visitor who scans in 10 seconds should land on name, current role, one signal, and contact — nothing competing.
3. **One screen hero.** The first viewport carries identity, tagline, and current status. Everything below is evidence.
4. **Bounded by discipline.** The visual system mirrors the engineering philosophy: constrained palette, limited motion, deliberate structure. Restraint is the brand.
5. **Mobile-first, dark+light.** Must read well in GitHub mobile view and in both color schemes. Badges flat-square, transparent, legible on either ground.
6. **Quarterly-living.** The "currently" status and featured projects rotate; the structure stays stable so updates are surgical.

## Composition Lanes

- **Decide** — hero pitch: identity, bounded-autonomy tagline, status bar with current role + recent win, single contact CTA.
- **Explore** — featured projects (max 4) as discrete, scannable units with repo + language badges. GitHub links as primary proof.
- **Learn** — three short narrative sections (infrastructure depth, agentic research, founder mentality), each one paragraph max with a signal sentence.
- Supporting: compact experience timeline, tight education/honors, contact block repeated at foot.

Avoid collapsing every section into the same centered-stack rhythm. Vary mass: hero carries weight, narrative sections can run narrower and denser, projects breathe.

## Accessibility

- WCAG AA contrast in both light and dark themes.
- All interactive elements keyboard-reachable with visible 2-3px focus rings.
- Links descriptive; no icon-only controls without labels.
- `prefers-reduced-motion` respected — page is near-static by default anyway.
- Logical properties for any future RTL safety; page is LTR Greek/English.

## Visual Foundation

No existing tokens, CSS, or theme files in repo. To be established on first build. Anchors from the spec:

- **Palette:** restrained, near-neutral surface tinted slightly toward a chosen brand hue (not generic tech blue). One accent for the contact CTA and the win signal. Dark + light variants. Build in OKLCH.
- **Type:** system or one deliberate choice. Body measure 60-76ch. Three-level hierarchy (hook / bridge / detail) per section. Hierarchy through scale + weight contrast, minimum 1.3 ratio.
- **Spacing:** 4 / 16 / 36 rhythm. Sections separated by macro-breaths; no arbitrary gaps.
- **Motion:** minimal. Entrance at most a quiet fade; no scroll-triggered cascades. Reduced-motion = instant.
- **Badges:** flat-square, transparent background, legible on dark and light. Inline with project descriptions, not clustered decoratively.
- **Borders/shadows:** hairline borders and minimal shadow. The page should feel flat and load-bearing, not card-floaty.

## Component Rules

- **Hero:** name, tagline, status bar, one CTA. No image required — type can carry it.
- **Featured project unit:** title, one-line description, language badges, repo link, optional live link. Discrete, scannable as one unit. Max 4.
- **Narrative section:** heading + one paragraph + one signal sentence (italic or offset). No card chrome.
- **Timeline:** compact table or tight stacked list. Not a long vertical scroll of every role.
- **Contact:** email + LinkedIn + GitHub. Prominent in hero and repeated at foot. Not aggressive.

## Status

No interface code exists yet — only `index.md` (content spec). First design command should build the HTML surface from this brief + the content spec.

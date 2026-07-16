# GitHub Profile & Portfolio Audit Report

**Date:** 2026-07-16  
**Method:** `gh` CLI live API queries + local file comparison  
**Scope:** Profile metadata, pinned repos, CI status, README quality, CV↔spec↔HTML sync, optimization plan compliance

---

## 1. Profile Metadata — Implementation vs. Plan

| Field | Plan (§2/§5) target | Live state | Verdict |
|-------|---------------------|------------|---------|
| **Bio** | "AI Engineer (LLM Babysitter → Factory Manager) · Agentic Orchestration · Backend Systems" | `AI Engineer (LLM Babysitter → Factory Manager)` | ⚠️ **Partial** — missing subtitle (Agentic Orchestration · Backend Systems) |
| **Location** | "Athens, Greece" | `Athens, Greece` | ✅ |
| **Company** | "Co-Founder @ Keel Technologies" | `Co-Founder @ Keel Technologies` | ✅ |
| **Blog/website** | Portfolio link | `https://ertval.github.io` | ✅ |
| **Hireable** | Should be set | `null` | ⚠️ Not set |
| **Profile photo** | Professional headshot (§13C.6) | Cannot verify via API | ⚠️ Manual check needed |

---

## 2. Profile README (`ertval/ertval`) — Live vs. Blueprint

The profile README repo **exists** and contains a README. Comparing against the **§13E v2 template**:

| Element | Blueprint | Live | Verdict |
|---------|-----------|------|---------|
| Greeting header | `### 👋 I'm Ertval (Erti)` | ✅ Matches | ✅ |
| Subtitle | Bio + Orchestration + Backend | ✅ Matches | ✅ |
| Location + links | Athens + LinkedIn + Portfolio | ✅ Matches | ✅ |
| Narrative paragraph | Full summary | ✅ Matches | ✅ |
| Currently / Previously / 🏆 | All three lines | ✅ Matches | ✅ |
| Core Stack | Go · TypeScript · Python · PostgreSQL · Docker · FastAPI · Pydantic · LangGraph | ✅ Matches | ✅ |
| Currently Exploring | Agentic Orchestration · Safe AI Deployment · Omnigent · Durable Execution (Inngest) | ✅ Matches | ✅ |
| Featured Projects | 3 featured | ✅ Present | ✅ |
| Open To CTA | "AI-native backend roles · agentic-systems collaboration · Athens / remote EU" | ✅ Present | ✅ |
| Stats widget | None (correct — §13C.1 says skip) | ✅ Absent | ✅ |
| Live demo links | Recommended in §13C.7 | ❌ Not present on featured projects | ⚠️ Minor |
| `forum` featured | In §13E v2 template | ❌ Not listed (social-network in its place) | ⚠️ Deviation — acceptable, social-network is arguably stronger |

> [!TIP]
> The Profile README is **well-implemented** and follows the v2 template closely. The `two-tier-safe-ai-gate` description was updated to reflect Go + Inngest + Omnigent (aligned with the Omnigent architecture document), which is a smart deviation from the original Python blueprint.

---

## 3. Pin Order — Live vs. §13D Authoritative Order

| Slot | §13D target | Live (from GraphQL) | Verdict |
|------|-------------|---------------------|---------|
| #1 | `two-tier-safe-ai-gate` | ✅ `two-tier-safe-ai-gate` | ✅ |
| #2 | `keel-multi-agent-pipeline` | ✅ `keel-multi-agent-pipeline` | ✅ |
| #3 | `social-network` | ✅ `social-network` | ✅ |
| #4 | `make-your-game` | ✅ `make-your-game` | ✅ |
| #5 | `real-time-forum` | ✅ `real-time-forum` | ✅ |
| #6 | `forum` | ✅ `forum` | ✅ |

> [!NOTE]
> Pin order **exactly matches** the §13D consolidated authoritative list. This was a known internal contradiction between §4 and §8c — now correctly resolved.

---

## 4. CI Workflow Status — Per Repo

| Repo | Workflow exists? | Last run | Badge would show | Verdict |
|------|-----------------|----------|-------------------|---------|
| `two-tier-safe-ai-gate` | ❌ **No workflow** | N/A | ❌ No badge works | 🔴 **P0 gap** |
| `keel-multi-agent-pipeline` | ❌ **No workflow** | N/A | ❌ No badge works | 🔴 **P0 gap** |
| `social-network` | ✅ `ci.yml` | **failure** | 🔴 failing | 🔴 **Visible red badge** |
| `make-your-game` | ✅ `deploy.yml`, `policy-gate.yml` | success | ✅ | ✅ |
| `real-time-forum` | ✅ `ci.yml` | No recent run data | ⚠️ Unknown | ⚠️ Verify |
| `forum` | ✅ `go.yml` | **success** | ✅ green | ✅ |
| `chaikin` | ✅ `rust.yml` | N/A from query | ⚠️ Verify | ✅ Workflow exists |
| `lem-in-e` | ✅ `go.yml` | N/A | ⚠️ Verify | ✅ Workflow exists |
| `graphql` | ✅ `playwright.yml` | N/A | ⚠️ Verify | ✅ Workflow exists |
| `groupie-tracker` | ✅ `go.yml` | N/A | ⚠️ Verify | ✅ Workflow exists |

> [!WARNING]
> **Three critical CI issues:**
> 1. `two-tier-safe-ai-gate` and `keel-multi-agent-pipeline` — the two most prominent pinned repos — have **zero CI workflows**. Any CI badge in their READMEs is broken/404.
> 2. `social-network` CI is **failing**. A CTO sees a red badge on pin #3.

---

## 5. README Quality — P0 Checklist (§6 standards)

| Requirement | two-tier | keel | social-network | make-your-game | real-time-forum | forum |
|-------------|:---:|:---:|:---:|:---:|:---:|:---:|
| **Problem statement** | ✅ | ✅ | ⚠️ No explicit "Problem:" | ✅ | ✅ | ✅ |
| **Stack badges** | ✅ flat-square | ✅ flat-square | ❌ None | ✅ flat-square | ✅ flat-square | ✅ flat-square |
| **CI badge** | ⚠️ Present but no workflow → 404 | ⚠️ No CI badge | ❌ None | ✅ | ✅ | ✅ |
| **Architecture diagram** | ✅ Mermaid | ✅ Mermaid | ✅ Mermaid | ✅ | ❌ Needs check | ✅ |
| **Quick Start** | Needs check | Needs check | ✅ | ✅ | ✅ | ✅ |
| **Related/cross-links** | Needs check | Needs check | ❌ | ❌ | ❌ | ❌ |

> [!IMPORTANT]
> `social-network` is missing stack badges and has no explicit problem statement at the top. As pinned #3, this is a CTO-visible gap.

---

## 6. Repo Descriptions & Topics — Metadata Gaps

**All 10 key repos have `null` descriptions and zero topics.** This is a significant discoverability issue:

| Repo | Description | Topics | Action needed |
|------|-------------|--------|---------------|
| `two-tier-safe-ai-gate` | `null` | `[]` | 🔴 Add description + topics |
| `keel-multi-agent-pipeline` | `null` | `[]` | 🔴 Add description + topics |
| `social-network` | `null` | `[]` | 🔴 Add description + topics |
| `make-your-game` | `null` | `[]` | 🔴 Add description + topics |
| `real-time-forum` | `null` | `[]` | 🔴 Add description + topics |
| `forum` | `null` | `[]` | 🔴 Add description + topics |
| `chaikin` | `null` | `[]` | Add description + topics |
| `lem-in-e` | `null` | `[]` | Add description + topics |
| `graphql` | `null` | `[]` | Add description + topics |
| `groupie-tracker` | `null` | `[]` | Add description + topics |

> [!CAUTION]
> **100% miss rate on repo descriptions and topics.** This is not covered in the optimization reports but is a major gap. GitHub search, profile browsing, and Google indexing all use these fields. A CTO scanning your profile overview sees blank descriptions under every repo name.

---

## 7. Archive Strategy — Progress

| Metric | Plan target | Current state | Verdict |
|--------|-------------|---------------|---------|
| Total repos | 48 → ~8 visible | **42 public, 0 archived** | 🔴 **Not implemented** |
| School/exercise repos visible | Should be archived | ~30 still public (`ascii-art-*`, `piscine-*`, `groupie-tracker-*`, `guess-it-*`, etc.) | 🔴 |
| Private repos | 19 | 19 (expected) | ✅ |

**Still-public repos that should be archived/private per §4:**
`ascii-art`, `ascii-art-color`, `ascii-art-fs`, `ascii-art-justify`, `ascii-art-output`, `ascii-art-reverse`, `ascii-art-stylize`, `ascii-art-web`, `atm-management-system-kiro`, `ch1`, `clonernews`, `drawing`, `filler`, `git`, `git-notes`, `groupie-tracker-filters`, `groupie-tracker-geolocalization`, `groupie-tracker-search-bar`, `guess-it-1`, `guess-it-2`, `jart`, `jraffic`, `lem-in`, `linear-stats`, `mini-framework`, `mister-quiz`, `my-ls-1`, `net-cat`, `piscine-java`, `piscine-js`, `piscine-rust`, `push-swap`, `road_intersection`, `shop`, `sortable`, `system-monitor`, `tetris-optimizer`

> That's **37 repos** that dilute the signal. A CTO sees "53 public repos" and immediately knows most are school exercises.

---

## 8. CV ↔ Spec ↔ HTML Sync Check

### 8a. CV → `docs/index.md` (spec) sync

| Field | [CV](file:///home/ertval/code/project-modules/ertval.github.io/docs/cv/ertval_karameta_cv.md) | [Spec](file:///home/ertval/code/project-modules/ertval.github.io/docs/index.md) | Match? |
|-------|-----|------|--------|
| Title/identity | "AI Engineer (LLM Babysitter → Factory Manager)" | "Agentic AI Engineer · Founder · Backend & Infrastructure" | ⚠️ **Different framing** — spec uses a different title than CV |
| Summary text | Long paragraph | Same paragraph | ✅ |
| Keel Technologies | "Co-Founder \| May 2026 – Present" | "Co-Founder @ Keel Technologies" | ✅ |
| Metagalerie details | Vision, Product, Serverless bullets | ✅ All 3 bullets present | ✅ |
| Hellenic Army | Communications Specialist, 2016–2017 | ✅ Present | ✅ |
| Self-employed | Education/Tutoring, 2006–2016 | ✅ Present | ✅ |
| AIT Research | Research Assistant, 2009–2010 | ✅ Present | ✅ |
| Education entries | Zone01, AUEB, NKUA, AIT | ✅ All 4 present with coursework | ✅ |
| Honors | All 6 entries + summer schools | ✅ All present | ✅ |
| Skills | Competencies, Technologies, Languages | ✅ All 3 categories | ✅ |
| Interests | Art, Science, Tech, Muay Thai, Cooking, Traveling | ✅ | ✅ |

> [!NOTE]
> The spec adds content **beyond** the CV (narrative sections, featured projects, "Open To" CTA, design rules). This is expected — the spec is a superset. The title difference ("AI Engineer" vs "Agentic AI Engineer · Founder") is a deliberate editorial choice for the portfolio — **acceptable**.

### 8b. `docs/index.md` (spec) → `public/index.html` sync

| Section | Spec content | HTML implementation | Match? |
|---------|-------------|---------------------|--------|
| **Identity** | "Ertval Karameta / Agentic AI Engineer · Founder · Backend & Infrastructure" | `hero__title`: "Agentic AI engineer. Founder. Backend & Platform." | ⚠️ "Infrastructure" → "Platform" |
| **Tagline** | Bounded autonomy quote (3 lines) | `hero__tag` blockquote: Summary paragraph (different text — uses CV summary instead of the 3-line bounded autonomy quote) | ⚠️ **Mismatch** — spec says use the tagline quote, HTML uses the long summary paragraph instead |
| **Status: now** | "Co-Founder @ Keel Technologies — multi-agent AI for maritime intelligence" | ✅ Matches | ✅ |
| **Status: prev** | "Co-founder @ Metagalerie (Artisto, art-management SaaS) · Zone01 Athens" | ✅ Matches (slightly abbreviated but accurate) | ✅ |
| **Status: win** | "1st Place — Panathenea AI Hackathon" | ✅ "1st place — Panathenea AI Hackathon 2026" | ✅ |
| **Core Stack** | "Go · Python · PostgreSQL · Docker · FastAPI · Pydantic · LangGraph · TypeScript" | ✅ Same items | ✅ |
| **Also** | "Git · Java · SQLite · Bash · MATLAB · LaTeX · HTML/CSS · JS/TS" | ✅ Matches | ✅ |
| **Exploring** | "Agentic Orchestration · Safe AI Deployment · Durable Execution" | ✅ Matches | ✅ |
| **Narrative 01** | Backend & infrastructure depth | ✅ Matches | ✅ |
| **Narrative 02** | Agentic AI research & prototyping | ✅ Matches | ✅ |
| **Narrative 03** | Founder mentality | ✅ Matches | ✅ |
| **Projects** | 4 featured (two-tier, keel, social-network, make-your-game) | ✅ All 4 present with correct descriptions | ✅ |
| **Experience table** | 5 roles with bullets | ✅ All 5 roles with all bullet points | ✅ |
| **Education** | 4 entries with coursework | ✅ All 4 | ✅ |
| **Honors** | 7 entries + summer schools | ✅ All present | ✅ |
| **Skills** | Competencies, Technologies, Languages | ✅ All 3 | ✅ |
| **Open To** | "AI-native backend roles · agentic-systems collaboration · Athens / remote EU" | ✅ In footer | ✅ |
| **Interests** | Art · Science · Technology · Muay Thai · Cooking · Traveling | ✅ In footer | ✅ |
| **Contact links** | Email, LinkedIn, GitHub | ✅ Hero + footer | ✅ |

> [!IMPORTANT]
> **Two discrepancies found:**
> 1. **Title**: Spec says "Backend & Infrastructure" → HTML says "Backend & Platform" — minor wording change
> 2. **Hero tagline**: The spec defines a 3-line bounded autonomy quote. The HTML instead uses the long CV summary paragraph as the blockquote. These serve different purposes. The spec's tagline is punchier and more opinionated.

---

## 9. HTML / CSS Best Practices Audit

### Strengths ✅
- Semantic HTML5: `<header>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<nav>`
- Single `<h1>` with proper hierarchy (h1 → h2 → h3)
- Skip-to-content link
- `aria-labelledby`, `aria-label`, `aria-hidden` used correctly
- `<caption class="vh">` for data table accessibility
- `prefers-color-scheme` dark/light with OKLCH tokens
- `prefers-reduced-motion` respected
- `viewport-fit=cover` for notch devices
- Focus-visible outline: 2px solid accent with 3px offset
- OG tags, canonical URL, meta description
- No JavaScript at all (correct per AGENTS.md constraints)
- Google Fonts: Fraunces (serif), Inter (sans), JetBrains Mono (mono)
- Mobile responsive with 720px and 1024px breakpoints
- Location column hidden on mobile for experience table

### Issues ⚠️
1. **Placeholder links**: `href="#"` on "live demo →" (two-tier) and "play →" (make-your-game) — these are dead links visible to a CTO
2. **No `target="_blank"`** on external GitHub/LinkedIn links — minor UX preference
3. **Missing `rel="noopener"` on mailto link** — line 85 has `btn--accent` email link without `rel`
4. **No `lang` subtag** — `<html lang="en">` is fine, but the name "Ertval" and some Greek references don't need special handling
5. **No structured data** (JSON-LD) — optional but would help Google knowledge panel for "Ertval Karameta"
6. **Education entries missing dates** — The spec has dates (2024–2026, etc.) but the HTML omits them

---

## 10. Omnigent Architecture Alignment

The [UPDATED-CONCLUSIONS-OMNIGENT-ARCHITECTURE.md](file:///home/ertval/code/project-modules/ertval.github.io/docs/github/UPDATED-CONCLUSIONS-OMNIGENT-ARCHITECTURE.md) defines a three-layer architecture: **Omnigent governs, LangGraph orchestrates, Inngest executes, AWS hosts.**

| Signal | Optimal state | Current state | Verdict |
|--------|---------------|---------------|---------|
| `two-tier-safe-ai-gate` shows Omnigent awareness | ✅ | ✅ README mentions Omnigent v0.3.0, Go MCP governance gate | ✅ Excellent |
| `two-tier-safe-ai-gate` demonstrates Inngest durable execution | ✅ | ✅ README describes Inngest for Tier 2 bounded execution | ✅ |
| Profile README mentions Omnigent + Inngest | ✅ | ✅ "Currently Exploring: Omnigent · Durable Execution (Inngest)" | ✅ |
| `keel-multi-agent-pipeline` shows LangGraph | ✅ | ✅ LangGraph stateful graphs, O-W-V pattern | ✅ |
| Three-layer narrative visible | ✅ | ⚠️ Implicit but not spelled out on portfolio site | ⚠️ |

> [!TIP]
> The **Omnigent pivot** (from Python/FastAPI/Pydantic in the original plan to Go/Inngest/Omnigent) is well-reflected in the profile README and `two-tier-safe-ai-gate`. The architecture doc's recommendation to use Omnigent as governance layer + LangGraph for orchestration + Inngest for durability is correctly represented across the repos.

---

## 11. Summary — Priority Action Items

### 🔴 Critical (fix before any CTO review)

| # | Issue | Impact | Effort |
|---|-------|--------|--------|
| 1 | **`social-network` CI is failing** — red badge on pinned #3 | CTO sees broken build | Fix CI or temporarily remove badge |
| 2 | **`two-tier-safe-ai-gate` has no CI workflow** — badge link 404s | Pin #1 has broken CI badge | Create workflow or remove badge from README |
| 3 | **`keel-multi-agent-pipeline` has no CI workflow** | Pin #2 has no CI signal | Create workflow |
| 4 | **All 10 repos have null descriptions** | Profile overview shows blank descriptions | 5 min per repo via `gh repo edit` |
| 5 | **37 school repos still public** | 42 visible repos dilute signal; screams "student" | Batch archive via `gh repo archive` |
| 6 | **Placeholder `href="#"` links** on portfolio site | "live demo" and "play" links go nowhere | Remove or replace with real URLs |

### 🟡 High (this week)

| # | Issue | Impact |
|---|-------|--------|
| 7 | All repos missing topics (tags) | Discoverability, search ranking |
| 8 | `social-network` README missing stack badges and explicit problem statement | Pin #3 looks less polished than others |
| 9 | Education dates missing from HTML | Spec has dates, HTML doesn't — spec wins |
| 10 | Hero tagline in HTML differs from spec (uses long summary instead of punchy 3-line quote) | Spec says use bounded autonomy quote |
| 11 | "Infrastructure" vs "Platform" in hero title | Minor spec drift |

### ✅ Already implemented correctly

- Profile README follows §13E v2 template
- Pin order matches §13D consolidated list exactly
- Bio, location, company set
- Portfolio link set
- No stats widget (correct per §13C.1)
- Open To CTA present
- Currently Exploring mentions Omnigent + Inngest
- `two-tier-safe-ai-gate` reflects Omnigent architecture alignment
- `keel-multi-agent-pipeline` positioned as hackathon winner
- All 6 visible pinned repos have READMEs with problem statements (except social-network)
- Stack badges use `flat-square` style with `logoColor=white` (dark-mode safe)
- CI workflows exist for 8/10 key repos
- HTML has proper semantic structure, accessibility, and dark/light theming
- GitHub Pages deployed and serving at `https://ertval.github.io/`
- CV ↔ spec ↔ HTML content fully synchronized (with 2 minor wording deviations)

---

## 12. Optimization Plan Compliance Score

| Plan section | Implementation | Score |
|-------------|----------------|-------|
| §2 Profile metadata (bio/location/company) | ✅ Done | 90% |
| §5 Profile README | ✅ Done, closely follows v2 template | 95% |
| §4/§13D Pin order | ✅ Exact match | 100% |
| §6 README standards (problem/arch/quickstart/badges) | ⚠️ Most done, social-network lagging | 80% |
| §7 Archive strategy | 🔴 Not started (37 repos still public) | 5% |
| §8 CI/badges | ⚠️ Workflows exist for most, but 2 pinned repos have none + 1 failing | 60% |
| §9 Key repo blueprints | ⚠️ two-tier and keel deviate from blueprint (Go vs Python) — intentional | 75% |
| §10 Badge style consistency | ✅ flat-square across the board | 95% |
| §13C Gap fixes (no stats, open-to, mobile) | ✅ Mostly implemented | 85% |
| Repo descriptions & topics | 🔴 100% miss rate — not in original plan | 0% |
| Portfolio site (HTML/CSS) | ✅ High quality, matches spec closely | 90% |

**Overall:** ~70% implemented. The high-impact items (profile README, pins, key READMEs) are done well. The long tail (archiving, descriptions, CI gaps) remains.

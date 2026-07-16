# README Optimization Report — All 8 Repos

**Generated:** 2026-07-03
**Blueprint:** [`GITHUB-OPTIMIZATION-CONSOLIDATED.md`](./GITHUB-OPTIMIZATION-CONSOLIDATED.md) §6
**Sources:** 4 subagent audits covering all repos

---

## Priority Matrix (All Repos)

### P0 — Must Fix (CTO sees these in 15s scan)

| Gap | social-network | make-your-game | real-time-forum | forum | chaikin | lem-in-e | graphql | groupie-tracker |
|-----|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| **Problem statement** | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| **Stack badges** | ❌ | ❌ | ⚠️ opaque | ❌ | ❌ | ❌ | ❌ | ❌ |
| **CI badge** | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| **Related links** | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |

### P1 — High Impact (CTO reads deeper)

| Gap | social-network | make-your-game | real-time-forum | forum | chaikin | lem-in-e | graphql | groupie-tracker |
|-----|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| **Mermaid architecture** | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| **Quick Start top-fold** | ❌ | ❌ | ✅ | ✅ | ✅ | ⚠️ | ✅ | ⚠️ |
| **Mobile-friendly tables** | ⚠️ | ⚠️ | ⚠️ | ⚠️ | ⚠️ | ⚠️ | ⚠️ | ⚠️ |

### P2 — Polish

| Gap | social-network | make-your-game | real-time-forum | forum | chaikin | lem-in-e | graphql | groupie-tracker |
|-----|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| **Dark/light badges** | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| **Stats widget** | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A |

---

## Repo-by-Repo Fix Summary

### 1. `social-network` (Pinned #3 — Go backend flagship)

| # | Fix | Details |
|---|-----|---------|
| P0 | Add problem statement | "Full-stack social networking reference demonstrating clean vertical-slice Go design with pluggable infrastructure adapters." |
| P0 | Add badge row | Go 1.24, Next.js 15, TypeScript 5, SQLite, CI, License — `style=flat-square` + `logoColor=white` |
| P0 | Add CI badge | `github.com/ertval/social-network/actions/workflows/ci.yml` |
| P1 | Add Related section | Cross-link to `make-your-game`, CV link |
| P1 | Collapse wide tables | Tooling matrix + D1-D6 → bullet lists for mobile |
| P1 | Restructure top fold | Quick Start before deep docs |

### 2. `make-your-game` (Pinned #4 — JS ECS engine)

| # | Fix | Details |
|---|-----|---------|
| P0 | Add problem statement | "Pure-JS ECS game engine demonstrating data-oriented browser architecture — no canvas, no frameworks, 60 FPS DOM with strict performance budgets." |
| P0 | Add badge row | JavaScript ES2026, Vite 6, Biome, Vitest, CI, PRs Welcome, License |
| P0 | Add CI badge | `github.com/ertval/make-your-game/actions/workflows/deploy.yml` |
| P1 | Add Related section | Cross-link to `social-network`, CV link |
| P1 | Restructure top fold | Quick Start (currently line ~850) → above Architecture / Directory / Frame Pipeline |
| P1 | Condense 10+ wide tables | Collapse Command Purpose table, Track table → lists; keep Controls/Scoring as small tables |

### 3. `real-time-forum` (Pinned #5 — Go real-time SPA)

| # | Fix | Details |
|---|-----|---------|
| P0 | Add problem statement | "Self-hosted real-time forum for private communities — replace proprietary group-chat with open, auditable, single-binary SPA." |
| P0 | Add CI badge | `github.com/ertval/real-time-forum/actions/workflows/go.yml` |
| P0 | Add Related section | Cross-link to `forum`, CV link |
| P1 | Add Mermaid diagram | Browser → Frontend :3000 → Backend :8080 → SQLite |
| P1 | Fix badge style | `for-the-badge` → `flat-square` (opaque → transparent) |
| P2 | Mobile table fix | Architecture path/role table → list format |

### 4. `forum` (Pinned #6 — Go hexagonal monolith)

| # | Fix | Details |
|---|-----|---------|
| P0 | Add problem statement | "Lightweight self-hosted community forum with zero external deps — full control without SaaS lock-in." |
| P0 | Add stack badges | Go, SQLite, License — `style=flat-square` |
| P0 | Add CI badge | Per report blueprint: `github.com/ertval/forum/actions/workflows/go.yml` |
| P0 | Add Architecture summary | Exact format from blueprint: "Hexagonal (ports-and-adapters) Go monolith: Core domain: threads, posts, user auth – Adapters: PostgreSQL, REST API, WebSocket – No framework" |
| P0 | Add Related section | Cross-link to `real-time-forum`, CV link |
| P1 | Add Mermaid diagram | Replace ASCII tree with hexagonal module flow |

### 5. `chaikin` (Visible unpinned — Rust algorithmic)

| # | Fix | Details |
|---|-----|---------|
| P0 | Add problem statement | "Chaikin's corner-cutting generates smooth curves from sparse control points — fundamental to CAD/animation. This Rust impl provides real-time interactive exploration." |
| P0 | Add stack badges | Rust — `style=flat-square` |
| P1 | Add architecture flow | Mouse Input → AppState → Chaikin Algorithm → Software Renderer → Pixel Buffer → Display |
| P1 | Add CI badge | Create `.github/workflows/rust.yml` if missing |
| P1 | Add Related section | Link to CV, `lem-in-e` |
| P2 | Condense tables | Controls/directory → lists |

### 6. `lem-in-e` (Visible unpinned — Go algorithmic)

| # | Fix | Details |
|---|-----|---------|
| P0 | Add problem statement | "Routing multiple agents through constrained graph with minimal completion time — solves ant farm topologies using disjoint path discovery + optimal ant distribution (1000 ants ~300ms)." |
| P0 | Add stack badges | Go — `style=flat-square` |
| P1 | Add Mermaid architecture | Input → Parser → Graph → Pathfinder → Simulator → Output |
| P1 | Add CI badge | Create `.github/workflows/go.yml` if missing |
| P1 | Add Related section | Link to CV, `chaikin` |
| P1 | Condense README | ~500 lines; move test results table → `docs/`; add TOC |
| P2 | Mobile sweep | Break wide tables into lists |

### 7. `graphql` (Visible unpinned — Vanilla JS)

| # | Fix | Details |
|---|-----|---------|
| P0 | Add problem statement | "School progression stats scattered across internal tools — this app provides unified dashboard for XP analytics, audit ratios, collaborator metrics via GraphQL API. Zero external deps." |
| P0 | Add Mermaid architecture | User → auth.view → login → event bus → dashboard.api → SVG renderers |
| P1 | Add stack badges | JavaScript, ES2026, GraphQL, SVG — `style=flat-square` |
| P1 | Add CI workflow + badge | Create `.github/workflows/playwright.yml` |
| P1 | Add Related section | Link to CV, LinkedIn |
| P1 | Replace wide stack table | Convert to inline badge row |
| P2 | Extract testing section | Break out of Quick Start |

### 8. `groupie-tracker` (Visible unpinned — Go API client)

| # | Fix | Details |
|---|-----|---------|
| P0 | Add problem statement | "Groupie Trackers API returns inconsistent response formats — this Go app normalizes responses into unified data model with SEO-friendly URLs. Zero external deps." |
| P0 | Add Mermaid architecture | Convert existing ASCII flow → Mermaid (API Fetch → processArtists → SEO Slugs → Cache → Maps → Handlers → Templates) |
| P0 | Add CI workflow + badge | Create `.github/workflows/go.yml` |
| P1 | Add stack badges | Go, Zero Deps, HTML, CSS — `style=flat-square` |
| P1 | Condense Quick Start | 4 commands → 3 (remove redundant build step) |
| P1 | Add Related section | Link to CV, LinkedIn |

---

## Cross-Repo Patterns

1. **100% miss rate on Problem Statement** — every repo opens with features not the problem. Single biggest P0 fix across all 8 repos.
2. **100% miss rate on Related links** — zero cross-pollination between repos. Adds <1min per repo.
3. **100% miss rate on CI badges** — several repos lack CI pipelines entirely. CI must be created before badge links work.
4. **75% miss rate on Stack badges** — only `real-time-forum` has badges, but they use opaque `for-the-badge` style.
5. **75% miss rate on Mermaid diagrams** — only `social-network` and `make-your-game` have Mermaid. Others use text/ASCII.

### Two repos don't exist yet

- **`two-tier-safe-ai-gate`** (P0 — must create per §9 blueprint)
- **`keel-multi-agent-pipeline`** (P1 — sanitized O-W-V prototype)

Both have full README blueprints in `GITHUB-OPTIMIZATION-CONSOLIDATED.md` (§9). Build README per template during repo creation.

---

## Estimated Effort

| Batch | Est. Time | Repos |
|-------|-----------|-------|
| P0: Problem statements (8 repos) | 20 min | All |
| P0: Badge rows (7 repos) | 15 min | All except RTF |
| P0: CI pipelines (5 repos) | 2-3 hours | `chaikin`, `lem-in-e`, `graphql`, `groupie-tracker` (create) + rest (add badge) |
| P0: Related links (8 repos) | 10 min | All |
| P1: Mermaid diagrams (6 repos) | 1 hour | forum, RTF, chaikin, lem-in-e, graphql, groupie-tracker |
| P1: Top-fold restructure (2 repos) | 30 min | social-network, make-your-game |
| P1: Mobile table collapse (6 repos) | 1 hour | All with wide tables |
| P1: Badge style fix (1 repo) | 5 min | real-time-forum |
| **Total** | **~6 hours** | |

---

## Verification Checklist (apply to each repo after changes)

- [ ] README opens with `Problem` (1-2 sentences)
- [ ] Badge row visible on first screen (stack + CI)
- [ ] CI badge shows **passing** (green)
- [ ] Quick Start ≤ 3 commands
- [ ] Architecture section has flow diagram (Mermaid preferred)
- [ ] Related section links to CV + sibling repos
- [ ] All badges use `style=flat-square` with `logoColor=white` (dark-mode safe)
- [ ] No wide tables wider than 800px — verify on GitHub mobile app
- [ ] No `.env`, secrets, or data committed
- [ ] Profile README v2 template from §13E used (no stats widget, open-to CTA)

---

## Key Numbers

| Metric | Value |
|--------|-------|
| Total repos audited | 8 |
| Total P0 gaps found | 32 (4 per repo × 8 repos) |
| Total P1 gaps found | ~25 |
| Repos needing CI creation | 4 (`chaikin`, `lem-in-e`, `graphql`, `groupie-tracker`) |
| Repos needing CI badge only | 4 (rest have workflows but no badge) |
| Repos with Mermaid already | 2 (social-network, make-your-game) |
| Repos needing top-fold reorder | 2 (social-network, make-your-game) |
| Mobile-unfriendly tables | ~30 across all repos |
| Hours to fix everything | ~6 |
| CTO impression improvement | "Student with school projects" → "Engineer with production taste" |

---

## Source Reports

- [`readme-audit-social-myg.txt`](./readme-audit-social-myg.txt)
- [`readme-audit-forum-realtime.txt`](./readme-audit-forum-realtime.txt)
- [`readme-audit-chaikin-lemin.txt`](./readme-audit-chaikin-lemin.txt)
- [`readme-audit-graphql-groupie.txt`](./readme-audit-graphql-groupie.txt)

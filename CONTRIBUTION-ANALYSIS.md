# Vinext Contribution Analysis

> Session date: 2026-04-01 (updated from 2026-03-25)
> Repository: cloudflare/vinext
> Branch: main (synced with upstream)

## Project Overview

Vinext is an open-source project that runs Next.js applications on Vite. At the time of analysis, the project has **30 open issues** and **29 open pull requests**.

### Changes Since Last Analysis (2026-03-25)

- **9 issues closed**: #564, #623, #648, #659, #680, #688, #695, #710, #727
- **9 new issues opened**: #701, #708, #717, #720, #722, #724, #726, #728, #730
- **30+ PRs merged**, including major work: standalone self-host output (#178), nitro route rules (#669), instrumentation-client support (#679), usePathname SSR fix (#689), Pages Router build fix (#711), font handling fixes (#719, #723), and many refactors extracting plugins into separate files
- **Issue #564** (static export E2E) was resolved by our PR #686

---

## Open Issues Summary (30 total)

All issues are **unassigned**, making them available for contribution.

### Critical Bugs

| Issue | Title                                                                              | Difficulty |
| ----- | ---------------------------------------------------------------------------------- | ---------- |
| #730  | App Router interception resolution is not source-aware (multi intercepting routes) | Hard       |
| #672  | RSC streaming crash: `enqueueModel is not a function` (multi-route App Router)     | Hard       |
| #652  | Cross-route client navigation hangs in Firefox (`startTransition` never commits)   | Hard       |
| #639  | App Router client navigation double-flashes Suspense fallbacks                     | Hard       |
| #722  | Incompatible with next-safe-action                                                 | Medium     |
| #720  | Incompatibility issues                                                             | Medium     |
| #585  | SSR dev server fails with "module is not defined" for CJS deps                     | Medium     |
| #572  | `react-server` export condition missing in CF Workers bundle                       | Medium     |
| #537  | Alternating request failures with Drizzle + Postgres on CF Workers                 | Medium     |
| #237  | "Only plain objects" error passing to Client Components                            | Medium     |
| #185  | RSC moduleMap undefined on first request                                           | Medium     |
| #143  | Module doesn't provide export named 'jsx'                                          | Medium     |

### Compatibility / Parity Issues

| Issue | Title                                                               |
| ----- | ------------------------------------------------------------------- |
| #675  | `getInitialProps` support                                           |
| #666  | App Router dev fails on raw CJS packages from node_modules          |
| #654  | Action redirects use hard navigation instead of soft RSC navigation |
| #540  | Vite 8 deprecated config options cause build warnings               |
| #177  | Issues with `next-intl` library                                     |

### Feature Requests / Enhancements

| Issue | Title                                                           | Label            |
| ----- | --------------------------------------------------------------- | ---------------- |
| #728  | Support file:// URLs from import.meta.resolve() in cacheHandler | nextjs-tracking  |
| #726  | Waku-style Layout Persistence for vinext                        |                  |
| #724  | E2E for Standalone Output                                       | good first issue |
| #708  | Update `revalidateTag` shim for two-argument signature          | nextjs-tracking  |
| #701  | Add `experimental.useOffline` — offline detection & retry       | nextjs-tracking  |
| #664  | Native route-aware type generation                              |                  |
| #605  | AST-based route report generation                               | enhancement      |
| #567  | Layout-level `generateStaticParams`                             | enhancement      |
| #566  | Lightweight worker for static exports                           | enhancement      |
| #565  | Pre-rendering usability enhancements                            | enhancement      |
| #563  | Pre-render pipeline performance improvements                    | enhancement      |
| #562  | Populating remote cache during deployment                       | enhancement      |
| #533  | Module federation support                                       |                  |
| #472  | `assetPrefix` support                                           |                  |
| #454  | Stable Next.js API manifest + CI gate                           |                  |
| #407  | `create-vinext-app` scaffolding CLI                             |                  |
| #389  | Pre-compiled regex for config patterns                          |                  |
| #253  | Refactor template code generation                               |                  |
| #199  | Add support for rewrites                                        |                  |
| #80   | Pluggable deployment adapters                                   |                  |
| #9    | Static pre-rendering at build time                              |                  |

### Docs / Infrastructure

| Issue | Title                                              |
| ----- | -------------------------------------------------- |
| #717  | Clarification on MIT License for AI-Generated Code |
| #204  | Systematic audit of Next.js test suite             |
| #73   | Docs: Clerk auth migration pattern                 |

---

## Issues Already Covered by PRs (Do Not Duplicate)

These issues already have active PRs addressing them:

| Issue | PR   | Topic                                             |
| ----- | ---- | ------------------------------------------------- |
| #730  | #721 | Intercepting route source-aware resolution        |
| #722  | #731 | Fix wrapped use server exports (next-safe-action) |
| #675  | #594 | getInitialProps / next/document support           |
| #654  | #698 | Soft RSC navigation for action redirects          |
| #652  | #690 | Firefox navigation hang fix                       |
| #639  | #647 | Prevent Suspense fallback flash                   |
| #605  | #606 | AST-based build report route analysis             |
| #540  | #548 | Remove deprecated Rollup config for Vite 8        |
| #472  | #474 | Support assetPrefix in next.config                |
| #407  | #406 | create-vinext-app CLI                             |
| #389  | #536 | Precompile next.config matchers at build time     |
| #177  | #196 | Extract webpack resolve.alias from next.config    |
| #199  | #217 | Serve static files from public/ for rewrites      |

---

## Open Pull Requests Summary (29 total)

### Bug Fix PRs

| PR   | Title                                                         | Author         | Draft |
| ---- | ------------------------------------------------------------- | -------------- | ----- |
| #731 | [codex] Fix wrapped use server exports                        | southpolesteve | Yes   |
| #721 | fix: allow inherited intercepting routes                      | Debbl          | Yes   |
| #698 | fix: server action redirects use soft RSC navigation (#654)   | yunus25jmi1    | No    |
| #690 | fix: cross-route client navigation hangs in Firefox (#652)    | Divkix         | No    |
| #665 | fix: support CommonJS node_modules in Pages Router dev        | southpolesteve | No    |
| #647 | fix: prevent Suspense fallback flash (#639)                   | —              | No    |
| #548 | fix(vite-8): remove deprecated Rollup config for Vite 8       | yunus25jmi1    | Yes   |
| #488 | fix: replay render-time response headers for cached responses | JaredStowell   | Yes   |
| #217 | fix(rewrites): serve static files from public/                | yunus25jmi1    | Yes   |
| #196 | fix: extract webpack resolve.alias from next.config (#177)    | SeolJaeHyeok   | No    |
| #157 | fix: resolve directory imports for next/font shims            | hoangnv170752  | No    |

### Feature PRs

| PR   | Title                                                     | Author          | Draft |
| ---- | --------------------------------------------------------- | --------------- | ----- |
| #709 | feat(cache): implement Next.js 16 revalidateTag two-phase | james-elicx     | Yes   |
| #653 | feat: lazy per-route cache seeding for Workers            | NathanDrake2406 | No    |
| #606 | Improve build report route analysis with AST parsing      | Boyeep          | Yes   |
| #594 | feat: implement next/document with getInitialProps        | james-elicx     | Yes   |
| #536 | feat: precompile next.config matchers at build time       | SeolJaeHyeok    | Yes   |
| #474 | feat: support assetPrefix in next.config                  | elydelva        | No    |
| #406 | feat: create-vinext-app CLI                               | Divkix          | No    |
| #158 | feat: next/font/google and next/font/local                | dknecht         | No    |
| #104 | feat(deploy): forward unknown CLI flags to wrangler       | dragonkhoi      | No    |
| #76  | feat: add Netlify as a deployment target (PoC)            | serhalp         | Yes   |

### Performance PRs

| PR   | Title                                              | Draft |
| ---- | -------------------------------------------------- | ----- |
| #641 | Build-time precompression + startup metadata cache | No    |
| #404 | Eliminate page probe double-execution              | Yes   |
| #392 | Tee stream for ISR caching                         | Yes   |

### Test / Docs / Infrastructure PRs

| PR   | Title                                       | Draft |
| ---- | ------------------------------------------- | ----- |
| #578 | test: expand Next.js compat coverage        | Yes   |
| #658 | docs: refresh AI guidance for vp and Vite 8 | No    |
| #329 | fix: improve deploy auth UX                 | No    |
| #240 | docs: add field learnings to skill docs     | No    |
| #227 | Automated PR review workflow                | Yes   |

---

## Priority Matrix — What to Work On

> **Legend:** Items marked with a PR badge have an existing pull request. Items marked "No assignee, no PR" are fully open for contribution.

Scoring criteria:

- **Impact** (1-5): How many users are affected or how much it advances the project
- **Effort** (1-5): How much work is required (1 = quick, 5 = weeks of work)
- **Merge Likelihood** (1-5): How likely the PR gets merged (based on maintainer signals, labels, existing PRs)
- **Priority Score** = (Impact × 2 + Merge Likelihood × 2) − Effort

> **Note:** As of 2026-04-01, **no open issues have assignees**. Availability is determined solely by whether an active PR already exists.

### Rank 1: High Priority — Do These First

| Rank | Issue | Title                                               | Status           | Impact | Effort | Merge | Score | Why                                                                                                                                                                |
| ---- | ----- | --------------------------------------------------- | ---------------- | ------ | ------ | ----- | ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1    | #724  | E2E for Standalone Output                           | **Open — no PR** | 4      | 2      | 5     | 16    | Labeled `good first issue` + `help wanted`. Standalone output (#178) just merged — maintainers want test coverage. We already did this exact pattern for #564/#686 |
| 2    | #581  | Remove clientReferenceDedupPlugin                   | **Open — no PR** | 3      | 2      | 5     | 14    | Maintainer consensus from james-elicx and hi-ogawa. Clear scope, low risk removal                                                                                  |
| 3    | #572  | react-server export condition missing in CF Workers | **Open — no PR** | 4      | 3      | 4     | 13    | Deploy-blocking for CF Workers users. No competing PR. Build config fix with clear scope                                                                           |
| 4    | #204  | Systematic audit of Next.js test suite              | **Open — no PR** | 3      | 3      | 5     | 13    | Infrastructure work maintainers value (1 thumbs up). Builds expertise across the codebase. No competing PR                                                         |

### Rank 2: Medium Priority — Strong Opportunities

| Rank | Issue | Title                                        | Status                           | Impact | Effort | Merge | Score | Why                                                                                                              |
| ---- | ----- | -------------------------------------------- | -------------------------------- | ------ | ------ | ----- | ----- | ---------------------------------------------------------------------------------------------------------------- |
| 5    | #666  | App Router dev fails on raw CJS packages     | PR #665 covers Pages Router only | 4      | 3      | 4     | 13    | Blocks real-world usage. Has 1 thumbs up. PR #665 exists but targets Pages Router only — App Router side is open |
| 6    | #537  | Alternating failures with Drizzle + Postgres | **Open — no PR**                 | 4      | 4      | 4     | 12    | 5 comments = active discussion. Affects production CF Workers users. No competing PR                             |
| 7    | #253  | Refactor template code generation            | **Open — no PR**                 | 3      | 3      | 4     | 11    | Recent plugin extraction refactors (#704-706) show maintainers want this. Check what remains                     |
| 8    | #605  | AST-based route report generation            | Has draft PR #606 — may be stale | 3      | 3      | 4     | 11    | Enhancement label. Draft PR #606 exists — could take over or collaborate if stale                                |

### Rank 3: High Impact but High Effort — Plan Carefully

| Rank | Issue | Title                              | Status                         | Impact | Effort | Merge | Score | Why                                                                                                            |
| ---- | ----- | ---------------------------------- | ------------------------------ | ------ | ------ | ----- | ----- | -------------------------------------------------------------------------------------------------------------- |
| 9    | #80   | Pluggable deployment adapters      | Has draft PR #76 (Netlify PoC) | 5      | 5      | 4     | 13    | **15 thumbs up** — highest community demand. Huge scope though. PR #76 (Netlify PoC) is draft — study it first |
| 10   | #9    | Static pre-rendering at build time | **Open — no PR**               | 5      | 5      | 4     | 13    | **9 thumbs up** — second highest demand. 8 comments. Core feature gap. Major undertaking                       |
| 11   | #639  | Suspense fallback double-flash     | Has PR #647 (open, not merged) | 4      | 4      | 3     | 9     | 8 comments = pain point. PR #647 exists but not merged after weeks — may need a different approach             |
| 12   | #672  | RSC streaming crash: enqueueModel  | **Open — no PR**               | 5      | 5      | 3     | 11    | Critical crash but deep RSC internals. High reward if solved                                                   |

### Rank 4: Taken — PRs Already In Flight

These issues have active PRs addressing them. Best contribution is **reviewing/testing the PR** rather than starting fresh.

| Issue | PR   | Topic                                | PR Author       | PR Status | Action             |
| ----- | ---- | ------------------------------------ | --------------- | --------- | ------------------ |
| #654  | #698 | Soft RSC navigation for redirects    | yunus25jmi1     | Open      | Review & test      |
| #652  | #690 | Firefox navigation hang              | Divkix          | Open      | Review & test      |
| #722  | #731 | next-safe-action compat              | southpolesteve  | Draft     | Watch for progress |
| #730  | #721 | Intercepting routes source-aware     | Debbl           | Draft     | Watch for progress |
| #540  | #548 | Vite 8 deprecated config             | yunus25jmi1     | Draft     | Could help finish  |
| #675  | #594 | getInitialProps / next/document      | james-elicx     | Draft     | Watch for progress |
| #585  | #665 | CJS node_modules in Pages Router dev | southpolesteve  | Open      | Review & test      |
| #562  | #653 | Cache seeding for Workers            | NathanDrake2406 | Open      | Review & test      |
| #472  | #474 | assetPrefix support                  | elydelva        | Open      | Review & test      |
| #407  | #406 | create-vinext-app CLI                | Divkix          | Open      | Review & test      |
| #389  | #536 | Precompile next.config matchers      | SeolJaeHyeok    | Draft     | Could help finish  |
| #177  | #196 | next-intl webpack aliases            | SeolJaeHyeok    | Open      | Review & test      |
| #199  | #217 | Rewrites static file serving         | yunus25jmi1     | Draft     | Could help finish  |

### Rank 5: Low Priority / Skip

| Issue            | Title                                 | Why Skip                                                      |
| ---------------- | ------------------------------------- | ------------------------------------------------------------- |
| #717             | MIT License clarification for AI code | Legal/governance, not code                                    |
| #720             | Incompatibility issues                | Vague — needs triage first                                    |
| #726             | Waku-style Layout Persistence         | Architectural RFC, no maintainer signal                       |
| #701, #708, #728 | nextjs-tracking issues                | Auto-generated by tracker. Wait for maintainer prioritization |
| #533             | Module federation                     | Niche use case, no engagement                                 |

---

### Recommended Sequence

Based on the matrix above, here's the suggested order of attack:

```
Week 1:  #724 (E2E standalone — quick win, builds on #686 experience)
         #581 (Remove dedup plugin — small, maintainer-approved)
Week 2:  #572 (react-server export condition — medium, deploy-blocking fix)
         #204 (Test audit — ongoing, builds codebase knowledge)
Week 3+: #537 or #666 (Production bug fixes — higher impact, more investigation)
         Review PRs #698, #690 (help move community PRs forward)
Ongoing: Track #80 and #9 for when scope is clearer
```

---

## Notable Recent Activity (Since 2026-03-25)

### Major Merges

- **#178** — Standalone self-host output (long-running PR, finally merged!)
- **#679** — Instrumentation-client support (by hyoban)
- **#669** — Map route segment revalidate to Nitro routeRules SWR
- **#686** — Static export E2E tests (resolved #564)
- **#689** — Fix usePathname() during SSR of "use client" pages
- **#700** — Fix RSC hydration (don't await createFromReadableStream before hydrateRoot)
- **#711** — Fix Pages Router deploy broken since v0.0.26+

### Code Quality Push

A significant code quality initiative landed: no-explicit-any (#715), prefer `type` over `interface` (#716), additional lint rules (#714), and pnpm supply chain rules (#729).

### Plugin Extraction Refactors

Several large refactors moved code from the monolithic `index.ts` into standalone plugin files:

- `fix-use-server-closure-collision.ts` (#704)
- `fonts.ts` (#705)
- `og-assets.ts` (#706)
- `server-externals-manifest.ts`

### Next.js Tracking

Three new `nextjs-tracking` issues were auto-created by the tracker workflow: #701, #708, #728.

---

## Notes for Contributors

- All issues are **unassigned** — comment on the issue before starting to avoid duplicate work
- First-time PR requires **manual approval** from a maintainer before CI runs
- Deploy previews require a maintainer to comment `/deploy-preview`
- The project uses `pnpm` for package management
- Run `pnpm run check` for formatting (uses `vp check`)
- Run `pnpm test` for the test suite (vitest)
- Pre-existing formatting issues and test failures exist in the repo — these are known

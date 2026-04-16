# Collision Intelligence V2.1 — Design System

**Single source of truth** for every HTML page in this project. V2.1 is a voice-correction pass on V2.0. V2.0 shipped plain-English / mobile-first and lost the industry credibility that made V1 sell to shop owners. V2.1 keeps V2.0's structural improvements (6-page architecture, enforced reading order, progress bar, inline tooltips, dedicated glossary) and transplants V1's voice back: declarative headlines, industry-native vocabulary, stakes-carrying peer-to-peer register.

---

## What Changed From V2.0 → V2.1

| Dimension | V2.0 (shipped April 16) | V2.1 (this rev) |
|---|---|---|
| **Voice** | "Plain English. Explain every term." | **Industry-native with tooltips as safety net.** |
| **Headlines** | Question-led ("Where does the money leak?") | **Declarative ("The Five Leaks Bleeding Every Shop")** |
| **Vocabulary** | Avoided E01, DEG, P-Page, sublet, teardown | **Used freely. Tooltip on first occurrence per page.** |
| **Agent names** | "It tells you which cars will total" | **"E01 Pre-Cognition & Teardown Defender" (restored from V1)** |
| **Layout** | Single-column magazine, 680px max | **Laptop-first, 960px max, multi-column sections on desktop** |
| **Body font** | 18px mobile-first | **16px desktop / 17px mobile (density over thumb reading)** |
| **Drop caps** | On every page lede | **Removed — too magazine, not enough industry** |
| **Register** | Calm, explanatory | **Stakes-carrying, peer-to-peer, urgent where urgency is real** |
| **Audience posture** | "Reading on phone between jobs" | **"Reading on laptop with a coffee, ready to evaluate"** |

**What did NOT change:** 6-page architecture, enforced reading order with bottom Prev/Next, progress bar, inline tooltip pattern (`<span class="term">`), glossary jump-nav, Agent 4 flagship positioning, color palette.

---

## Project Identity

**Name:** Collision Intelligence (V2.1 — Field Edition, Industry-Native Voice)
**Audience:** Independent shop owners, MSO principals, production managers, controllers, lenders — people who know the terms and expect to hear them used correctly.
**Publisher:** Intersection Strategies LLC
**Date:** April 2026

---

## Visual Tone

**Laptop-first industrial editorial.** Think a Friday-afternoon trade-journal feature someone prints and drops on a desk. Dense enough to feel serious. Spaced enough to read clean. Multi-column where it earns the pixels.

**Credibility through vocabulary.** A shop owner should read one sentence in and think "okay, this person has stood in a bay." A controller reading over their shoulder should tap a dotted-underline term and get a clean one-line definition. Neither reader should ever feel talked down to.

---

## Color Palette (unchanged from V1 / V2.0)

```css
:root {
    --bg-primary: #ffffff;
    --bg-secondary: #f6f7f9;
    --bg-tertiary: #eceef2;
    --bg-card: #ffffff;
    --bg-dark: #1a1f2b;

    --accent-charcoal: #1a1f2b;
    --accent-steel: #334155;
    --accent-crimson: #b91c1c;
    --accent-amber: #d97706;
    --accent-emerald: #047857;
    --accent-blue: #1e40af;

    --text-primary: #0f172a;
    --text-secondary: #334155;
    --text-muted: #64748b;
    --text-inverse: #f8fafc;

    --border-light: #e2e8f0;
    --border-medium: #cbd5e1;
    --border-strong: #94a3b8;
}
```

**Accent usage:** Crimson for the single most important number on a page, section eyebrows, flagship badge, the dotted underline on tooltip terms. Emerald for dollar recoveries. Charcoal for frames and surfaces.

---

## Typography

- **Body & UI:** Inter, weights 400/500/600/700/800
- **Monospace:** JetBrains Mono — used for API names, trigger codes, field labels

**Laptop-first scale:**
- Display (hero): **40px mobile → 56px desktop**
- H1: 28px mobile → 40px desktop
- H2: 22px mobile → 28px desktop
- Section eyebrow (uppercase): 12px, letter-spacing 0.16em, color crimson
- Body: **17px mobile → 16px desktop** (density over thumb reading — the reader is sitting down)
- Small: 14px, text-muted

**Line-height:** Body 1.65, headings 1.2.

**No drop caps.** V2.0's drop caps read as magazine-feature; V1's readers wanted trade-journal.

---

## Layout

- **Container max-width: 960px** (laptop-first reading width). 680px still used for body text columns inside wider frames.
- **Wide container: 1120px** for multi-column sections (agent grids, pricing tiers, stat bars).
- Horizontal padding: 20px mobile, 32px desktop.
- Section vertical rhythm: 56px mobile, 88px desktop.
- Every tap/click target minimum 40×40px; primary CTAs 56px tall.

**Multi-column rule:** Sections that light up on desktop (≥1024px) MUST collapse to single column by 640px. No 3-column grids that stack awkwardly on mid-breakpoints — use `repeat(auto-fit, minmax(280px, 1fr))` or explicit breakpoints.

---

## Navigation (unchanged scaffolding)

**Top nav (sticky):** brand + glossary link. Minimal on purpose — reading order is enforced by bottom Prev/Next, not top nav.

**Progress bar:** crimson fill, "Page X of 5" label. On every content page. Glossary shows 100% / "Reference".

**Bottom page-nav:** Prev (white, bordered) + Next (charcoal, filled). 64px tall. Visually dominant.

---

## Component Patterns

### Inline tooltip (THE KEY V2 PATTERN — expand coverage in V2.1)

```html
<span class="term">E01
    <span class="term-def">Total-loss threshold. The point where predicted repair cost × state percentage exceeds ACV and the carrier writes the car off.</span>
</span>
```

**Rule:** Every industry term gets a tooltip on **first occurrence per page**. Subsequent uses on the same page render bare. Every term that gets a tooltip also gets a full glossary entry.

Tooltip-on-first-use acronym list (required coverage per page where mentioned):
`E01`, `ACV`, `P-Page`, `DEG`, `DRP`, `FNOL`, `ADAS`, `ECD`, `ARMS`, `HIRS`, `OEM`, `EPC`, `PHEV`, `BEV`, `HV`, `VIN`, `sublet`, `supplement`, `teardown`, `not-included operation`, `MSO`, `CRIB 188`, `LKQ`, `blend`, `feather-prime-block`, `Secure Share`, `MCP`, `Claude Code Routine`.

### Declarative headline

```html
<h1 class="hero-title">The Five Leaks Bleeding Every Collision Shop.</h1>
```

Every `<h1>` and `<h2>` is declarative. No question-led headers. (V1 rule, re-enforced.)

### Stat-inline callout

```html
<div class="stat-inline">
    <div class="stat-inline-num">22.8%</div>
    <div class="stat-inline-label">Total-loss frequency — Q4 2025 historical high. Source: CCC Crash Course 2025.</div>
</div>
```

### Pullquote (peer voice)

```html
<div class="pullquote">
    <div class="pullquote-text">"You've watched a four-hour teardown become an argument on a Friday afternoon. You know this pain."</div>
    <div class="pullquote-attr">— Shop floor, every shop, every week</div>
</div>
```

### Agent block (restored V1 naming)

```html
<div class="agent flagship">
    <div class="agent-label">Agent 04 · Flagship</div>
    <h2 class="agent-title">E01 Pre-Cognition &amp; Teardown Defender</h2>
    <div class="agent-trigger"><code>trigger: assignment_dropped</code></div>
    <p class="agent-oneliner">...</p>
    <div class="agent-section">...</div>
    <div class="agent-pitch">"I'll stop you from wasting six hours on a car that's going to be totaled anyway."</div>
    <div class="agent-impact">...</div>
</div>
```

---

## Writing Voice

**The two-question test (V2.1):**
1. Would a shop owner recognize this sentence as something a peer said, not something a consultant wrote?
2. Does a controller or lender reading over their shoulder have enough tooltip scaffolding to follow without losing face?

If #1 is no: rewrite. Find the peer register.
If #2 is no: add tooltip coverage.

**Rules:**
- **Second person active.** "You've torn down a BMW X5 at 9 a.m. and watched the assignment flip to total loss by noon. You know this one."
- **Declarative headers.** "The Estimating Battlefield" — not "Where does the money actually leak?"
- **Industry vocabulary used correctly.** E01, DEG ruling, P-Page, DRP matrix, sublet markup, ADAS calibration, OEM repair procedure, appraisal clause. Wrap first occurrence per page in `<span class="term">`.
- **Dollar figures, specific, sourced.** "$28,050/mo recovered estimate lines (modeled on 100 ROs, mid-market mix)." Not "millions of dollars in savings."
- **Stakes up front.** Every section hero paragraph names the dollar exposure or liability exposure before explaining the mechanics.
- **Short paragraphs, tight sentences.** 3–4 sentences, industry rhythm. Not baby-voice short.

**Banned in V2.1 (V2.0 errors we're correcting):**
- Question-led headlines
- "Baby voice" — avoiding industry terms where a peer would use them
- Explanatory parentheticals in body copy instead of tooltips ("P-Pages (the procedure pages)")
- Single-column-only layouts that ignore desktop real estate
- Drop caps (too magazine, not enough trade-journal)
- Phrases like "the boring expensive parts," "what if every car," "three things this fixes" — V2.0 voice artifacts

---

## File Inventory (6 files)

1. **`index.html`** — Hero (declarative: "Five agents. Five leaks. One managed service."), thesis, three outcomes carrying stakes, reading guide, pilot CTA.
2. **`the-problem.html`** — "The Five Leaks Bleeding Every Collision Shop." Five named leaks: **P-Page Scrub Gap, E01 Teardown Waste, The Portal Tax, Sublet Reconciliation Drag, EV Compliance Liability.**
3. **`the-agents.html`** — "Five Named Reflexes. One Operator." V1 agent names restored. Agent 4 as flagship (dark card, top position). Trigger code block for each.
4. **`the-math.html`** — "$33,000/mo Recovered. First Month Payback." Per-agent breakdown with industry-native labels. Three pricing tiers. 90-day pilot.
5. **`how-it-works.html`** — "The Wiring: Trigger Layer → Routine Layer → Output Layer." Names Claude Code Routines, MCP, CCC Secure Share, Mitchell Transactional API, Audatex OAS3. About James. Security. FAQ.
6. **`glossary.html`** — Expanded alphabetical reference covering every term introduced by the voice transplant.

---

## Cross-Page Links (enforced reading order — unchanged)

```
index → the-problem → the-agents → the-math → how-it-works → glossary → (loop)
```

Glossary always reachable from top nav. Bottom Prev/Next on every content page.

---

## Agent Priority Order (unchanged)

**Lead with Agent 4 (E01 Pre-Cognition & Teardown Defender).** Dark-card flagship treatment at top of `the-agents.html`. Other four follow in V1 order: Agent 3 (Status Sync), Agent 1 (P-Page Scrubber), Agent 2 (Sublet Reconciler), Agent 5 (EV Compliance Documenter).

---

## Data (same as V1 / V2.0 — drawn from `source/research-report.md`)

Headline stats (industry-native framing in V2.1):
- **22.8%** total-loss frequency, Q4 2025 historical high (CCC Crash Course)
- **60%** of repairs require ADAS calibration in 2025 (Revv Collision Report)
- **61** ADAS-related lawsuits in 2024, up from 3 in 2018
- **28,000+** shops on CCC ONE footprint
- **$55k** median capex for an in-house static calibration bay (Revv 2025 benchmarking)
- **$21,500/mo** ADAS revenue at optimized shops

Agent recovery (monthly, average 80–120 RO shop):
- Agent 1 (P-Page Scrubber): **+$28,050**
- Agent 4 (E01 / Teardown Defender, flagship): **+$7,480**
- Agent 3 (Status Sync): **+$883**
- Agent 2 (Sublet Reconciler): **+$430**
- Agent 5 (EV Compliance): **+$280 per EV**
- Gross monthly recovery: **+$36,753**; Net after Stack tier ($1,750/mo): **~$33,000**

---

## Accessibility & Rendering

- Pages render correctly at **360 → 768 → 1024 → 1440px**.
- Zero external JavaScript. Tooltip behavior via `:hover` + `:focus-within`.
- Touch/click targets minimum 40×40px; primary CTAs 56px tall.
- Print-friendly: multi-column sections collapse cleanly.

---

## File Count Target

6 HTML files. Target **~4,200–4,800 total lines** (up from V2.0's ~3,600 due to voice density and expanded tooltip coverage; still well under V1's 13,639).

If any page exceeds 900 lines: cut. If any page falls under 450 lines: you're being too terse — the voice transplant means restoring stakes, not thinning.

# Collision Intelligence V2 — Design System

**Single source of truth** for every HTML page in this project. V2 is an Opus 4.7 redesign of the V1 Opus 4.6 briefing. Same research, same agents, same company — fundamentally different approach to how a non-technical shop decision-maker moves through the material on a phone.

---

## What Changed From V1

| V1 (Opus 4.6) | V2 (Opus 4.7) |
|---|---|
| 13 pages | **6 pages** |
| Desktop-first, 7-link top nav | **Mobile-first, large touch nav + bottom "Next →" on every page** |
| "Industry-native. Use terms without apology." | **"Explain every term inline. Glossary one tap away."** |
| Declarative stat-led headers | **Question-led story-led headers** |
| Dense multi-column editorial | **Single-column magazine feature** |
| Reader chooses order | **Reading order enforced visually (1 → 2 → 3 → 4 → 5 → Glossary)** |
| Industrial briefing ("sits on a production manager's desk") | **Conversational briefing ("a shop owner reads this on their phone between jobs")** |

**What did NOT change:** Core research, the five agents, the thesis, the pricing tiers, the color palette (same brand family).

---

## Project Identity

**Name:** Collision Intelligence (V2 — Field Edition)
**Tagline:** Built for the shop owner, the manager, and the tech lead — all reading together.
**Publisher:** Intersection Strategies LLC
**Date:** April 2026

---

## Visual Tone

**Magazine feature, not briefing document.** Think a long-form print story — wide margins, big drop caps, room to breathe, one idea per screen on mobile. The reader feels guided, not barraged. Every page answers one question.

**Confidence without density.** A shop owner reading this between two repair orders should never feel talked-down-to, but also should never hit a sentence that makes them stop and Google a term.

---

## Color Palette (unchanged from V1 for brand continuity)

```css
:root {
    /* Base */
    --bg-primary: #ffffff;
    --bg-secondary: #f6f7f9;
    --bg-tertiary: #eceef2;
    --bg-card: #ffffff;
    --bg-dark: #1a1f2b;

    /* Brand */
    --accent-charcoal: #1a1f2b;
    --accent-steel: #334155;
    --accent-crimson: #b91c1c;
    --accent-amber: #d97706;
    --accent-emerald: #047857;
    --accent-blue: #1e40af;

    /* Text */
    --text-primary: #0f172a;
    --text-secondary: #334155;
    --text-muted: #64748b;
    --text-inverse: #f8fafc;

    /* Borders */
    --border-light: #e2e8f0;
    --border-medium: #cbd5e1;
    --border-strong: #94a3b8;
}
```

**Accent usage rule (V2):** Even MORE sparing than V1. Crimson reserved for the single most important number on a page. If everything is emphasized, nothing is.

---

## Typography

- **Body & UI:** Inter, weights 300/400/500/600/700/800
- **Monospace (rare in V2 — only for API names):** JetBrains Mono

**Mobile-first scale:**
- Display (hero): 36px mobile → 64px desktop
- H1: 28px mobile → 40px desktop
- H2: 22px mobile → 28px desktop
- H3 label (uppercase): 12px mobile → 13px desktop, letter-spacing 0.12em
- Body: **18px mobile** → 17px desktop (bigger on mobile for thumb reading)
- Small: 14px, color: text-muted

**Line-height:** Body 1.7, headings 1.2. Generous.

**Drop caps:** First letter of each page's lede paragraph gets a 72px drop cap. Magazine feel.

---

## Layout

- Container max-width: **680px** (narrative reading width) for body content, 1040px for wide sections
- Horizontal padding: **20px mobile, 40px desktop** (generous on small screens for thumb reach)
- Section vertical rhythm: **64px mobile, 120px desktop**
- Every tap target minimum **48px × 48px**

---

## Navigation (mobile-first, identical on every page)

**Top (always visible):**

```html
<nav class="nav">
    <div class="nav-inner">
        <a href="index.html" class="nav-brand">COLLISION INTELLIGENCE</a>
        <a href="glossary.html" class="nav-glossary" aria-label="Open glossary">Glossary</a>
    </div>
</nav>
```

Top nav is **minimal** — brand + glossary. That's it. The reading order is enforced via bottom "Next →" buttons.

**Bottom (on every content page):**

```html
<div class="page-nav">
    <a href="the-problem.html" class="page-nav-prev">← Previous</a>
    <a href="the-math.html" class="page-nav-next">Next →</a>
</div>
```

Bottom nav is **large, touch-friendly (56px tall), and visually dominant** so the reader never wonders "where do I go next?"

**Page progress indicator** (top of each content page, under nav):

```html
<div class="progress-bar">
    <div class="progress-track">
        <div class="progress-fill" style="width: 40%"></div>
    </div>
    <div class="progress-label">Page 2 of 5</div>
</div>
```

---

## Footer (identical on every page)

```html
<footer class="footer">
    <div class="container">
        <div class="footer-brand">COLLISION INTELLIGENCE</div>
        <div class="footer-sub">Intersection Strategies LLC · Version 2.0 — April 2026</div>
        <div class="footer-links">
            <a href="index.html">Start Over</a>
            <a href="glossary.html">Glossary</a>
            <a href="mailto:james@intersection-strategies.com">Contact</a>
        </div>
    </div>
</footer>
```

---

## Page Structure Template

Every content page follows this structure:

1. **DOCTYPE + head** (Inter + JetBrains Mono, viewport, title)
2. **Sticky top nav** (brand + glossary)
3. **Progress bar** (X of 5)
4. **Hero** — one question, one-line answer, optional drop-capped lede
5. **Content** — single-column body, 680px max
6. **Bottom page-nav** — Prev / Next large buttons
7. **Footer**

---

## Component Patterns

### Drop-capped lede
```html
<p class="lede"><span class="dropcap">T</span>he rest of the paragraph flows normally...</p>
```

### Inline term definition (THE KEY V2 PATTERN)
```html
<dfn class="term" data-def="The point where insurance writes the car off as a total loss">E01</dfn>
```
Renders with a dotted underline. On hover/tap, shows a tooltip with the plain-English definition. Also linked from the glossary.

### Big number callout
```html
<div class="big-number">
    <div class="big-number-value">$33,000</div>
    <div class="big-number-label">per month of leverage the average shop is leaving on the table</div>
</div>
```

### Story card (replaces V1's pain-card)
```html
<div class="story">
    <div class="story-tag">WHAT HAPPENS TODAY</div>
    <h3>The estimator opens a PDF invoice from the calibration vendor.</h3>
    <p>They eyeball the markup, type each line into the estimate manually, and upload the PDF to the insurer portal. Every single job. 15 minutes each time. 40 times a week.</p>
</div>
```

### Agent block (replaces V1's agent-capsule — now expandable)
```html
<details class="agent">
    <summary class="agent-summary">
        <div class="agent-label">Agent 4 · Flagship</div>
        <h3>It tells you which cars are going to total before you tear them down.</h3>
        <div class="agent-expand">Tap to see how ↓</div>
    </summary>
    <div class="agent-body">
        <!-- trigger, pain, what-it-does, pitch -->
    </div>
</details>
```

### Before/After comparison
```html
<div class="compare">
    <div class="compare-before">
        <div class="compare-label">Without this agent</div>
        <p>...</p>
    </div>
    <div class="compare-after">
        <div class="compare-label">With this agent</div>
        <p>...</p>
    </div>
</div>
```

---

## Writing Voice

**The two-question test:** Before writing any sentence, ask:
1. Would a shop owner stop reading to Google a term in this sentence?
2. Is this sentence telling a story or stating a fact?

If #1 is yes: rewrite or add inline definition.
If #2 is "stating a fact": wrap it in a story.

**Rules:**
- **Second person active.** "You tear down a BMW X5. Four hours in, the adjuster tells you it's a total loss."
- **Questions as headers.** "Where does the money actually leak?" not "Revenue Leakage Analysis."
- **Dollar figures, not percentages, when possible.** "$28,050 per month" beats "22.8% improvement."
- **Define on first use.** Every industry term gets a `<dfn>` wrapper with inline tooltip.
- **Short paragraphs.** 3-4 sentences max. Mobile reading.
- **No jargon clusters.** If a sentence has more than one industry term, split it.

**Banned in V2 (from V1 that slipped through):**
- "Editorial" or "industrial briefing" positioning language — V2 is a field document
- "Internal-facing" language — V2 is written as if the reader is a prospect, not an internal stakeholder
- Multi-column desktop-first layouts
- "Industry-native" voice — V2 translates, doesn't assume

---

## File Inventory (6 files)

1. **`index.html`** — The briefing landing. Hero, the thesis, three outcomes, "Start reading →" CTA.
2. **`the-problem.html`** — "Where the money leaks." Five friction points told as short stories, jargon-free.
3. **`the-agents.html`** — "Five agents, one system." All five agents inline (expandable cards), Agent 4 featured.
4. **`the-math.html`** — "What it's worth." One hero number ($33K/mo), per-agent dollar impact, pricing.
5. **`how-it-works.html`** — "The machinery." Simplified architecture, about James, security — all one page.
6. **`glossary.html`** — Plain-English dictionary of every industry term used in the hub. Alphabetical.

---

## Cross-Page Links (enforced reading order)

```
index.html → the-problem.html → the-agents.html → the-math.html → how-it-works.html
                                                                        ↓
                                                                   glossary.html
                                                                   (accessible from top nav always)
```

Every content page has Prev/Next at bottom. Index has "Start Reading →" as single CTA. How-it-works has "Start Over" as its Next button (loops back to index).

---

## Agent Priority Order (unchanged from V1)

**Lead with Agent 4 (E01 Pre-Cognition).** In V2's single-agents-page, Agent 4 is rendered first and with distinct flagship styling. Other agents follow.

---

## Data to Use (from source/research-report.md — unchanged from V1)

Key stats (translated to plain English):
- Total loss frequency 22.8% → **"Nearly 1 in 4 cars now gets totaled."**
- 60% of repairs need calibration → **"More than half the cars you touch need sensor recalibration now."**
- 61 ADAS lawsuits in 2024 → **"61 lawsuits against shops in 2024 over sensor calibration alone. In 2018, there were 3."**
- 28,000+ CCC ONE shops → **"28,000 shops use CCC. None of them have agents like this wired in yet."**
- $21,500/mo ADAS revenue at optimized shops → **"The top 21% of shops pull $21,500/month just on sensor work."**

---

## Accessibility & Rendering

- All pages render correctly at **360px first** (Pixel/iPhone SE baseline), then 768px, 1024px, 1440px+
- Zero external JavaScript. Inline SVG only when essential (V2 uses fewer SVGs than V1).
- Touch targets minimum 48×48px. Buttons 56px tall.
- `<dfn>` tooltips work on hover (desktop) AND tap (mobile) — use `:focus-within` CSS trick, no JS.
- Print-friendly: pages should collapse cleanly if a shop owner prints one.

---

## File Count Target

6 HTML files. ~3,500 total lines (vs V1's 13,639). If any page exceeds 700 lines, you're being too thorough — cut.

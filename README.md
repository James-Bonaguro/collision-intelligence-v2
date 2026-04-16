# Collision Intelligence — V2 (Field Edition)

**Opus 4.7 redesign of the V1 briefing.**
April 2026 · Intersection Strategies LLC

---

## Why Two Versions

This is the A/B test. V1 was built by Opus 4.6 the same day Anthropic's Claude Code Routines dropped publicly. V2 was built by Opus 4.7 the same week, with real field feedback on V1 feeding the redesign brief.

- **V1 repo:** [collision-intelligence](https://github.com/James-Bonaguro/collision-intelligence) — 13 pages, exhaustive internal briefing
- **V2 repo (this one):** 6 pages, mobile-first field edition, plain-English

Both reference the same source research (`source/research-report.md`) and describe the same five agents with the same ROI math. What differs is how the content is delivered.

---

## What Changed From V1

| Dimension | V1 (Opus 4.6) | V2 (Opus 4.7) |
|---|---|---|
| **Pages** | 13 | 6 |
| **Total lines** | 13,639 | ~3,500 |
| **Nav model** | Desktop-first, 7-link top nav | Mobile-first, brand + glossary only; enforced reading order via bottom "Next →" |
| **Voice** | "Industry-native. Use terms without apology." | "Explain every term inline. Glossary one tap away." |
| **Headers** | Declarative ("Estimating Battlefield") | Question-led ("Where does the money leak?") |
| **Layout** | Dense multi-column editorial | Single-column magazine-feature |
| **Per-agent pages** | 5 separate deep-dive pages | Consolidated into one `the-agents.html` |
| **Jargon** | E01, DEG, P-Page assumed known | Inline `<dfn>` tooltips + dedicated glossary |
| **Body font size** | 16px | 18px (mobile-first) |
| **Tap targets** | ~40px | ≥48px, page-nav buttons 64px |
| **Reader journey** | Reader chooses order from nav | Visual progress bar + enforced 1→5 flow |

**What did NOT change:** The color palette (industrial charcoal + crimson), the five agents, the research backing, the pricing tiers, the thesis ("the trigger is the product").

---

## File Inventory

| # | File | Purpose |
|---|------|---------|
| 1 | `index.html` | Landing. Hero, three outcomes, thesis, reading guide, CTA. |
| 2 | `the-problem.html` | Page 1 of 5. Five leaks told as stories — jargon-free, dropcap lede, inline term tooltips. |
| 3 | `the-agents.html` | Page 2 of 5. Five agents on one page. Agent 4 rendered as flagship (dark card, top position). |
| 4 | `the-math.html` | Page 3 of 5. $33,000/mo hero number. Per-agent breakdown table. Three pricing tiers. 90-day pilot outline. |
| 5 | `how-it-works.html` | Page 4 of 5. Three-layer diagram. About James. Security & trust. FAQ. |
| 6 | `glossary.html` | Page 5 of 5. Plain-English dictionary of every industry term used in the hub. Alphabetical jump-nav. |

Plus: `DESIGN_SYSTEM.md` (single source of truth) and `source/research-report.md` (ground-truth research, unchanged from V1).

---

## How to View

Open `index.html` in any modern browser. Tested at 360px mobile → 1440px+ desktop. Best experience: **phone or tablet**, which was the explicit design target.

The reading order is enforced: every page has a big "Next →" button at the bottom. A shop owner on a phone should never wonder where to go next.

---

## Mobile-First Design Notes

- Body copy is **18px on mobile**, 17px desktop. Mobile readers need bigger text.
- Every interactive target is **≥48×48px**. Page-nav buttons are **64px tall**.
- Progress bar at top of every content page shows "Page X of 5" — reduces cognitive load.
- Single-column layout at every breakpoint. No 3-column grids on desktop that then stack awkwardly on mobile.
- Zero external JavaScript. Tooltips work via pure CSS (`:hover` + `:focus-within`).
- Drop caps at the start of each page's lede add magazine feel without bloat.

---

## How to Use in a Shop Conversation

Same pathway as V1 — **but designed to be handed over**, not narrated.

1. Hand them your phone or tablet with `index.html` open.
2. Let them scroll the three outcomes and hit "Start reading."
3. Stay quiet. The document is written to guide them through the five pages in under ten minutes.
4. When they finish, ask what resonated. Don't lecture. The document did the talking.

If they bring up an unfamiliar term mid-read, the glossary link is always in the top right. One tap.

---

## Parent Context

Part of the **Intersection Strategies LLC** trigger-based agent product line. See `..\CLAUDE.md` in the parent directory for the business context.

Sibling projects:
- **V1 briefing** — [collision-intelligence](https://github.com/James-Bonaguro/collision-intelligence)
- **Insurance broker proof** — [Broker](https://github.com/James-Bonaguro/Broker)

---

## Field Testing

This is V2 of a 2-way A/B test. Both versions go into the field with local collision shops. The goal is to learn which approach wins with real shop decision-makers — the comprehensive internal-briefing format (V1) or the simplified mobile-first field format (V2). Whichever wins becomes the external-facing standard.

Take both into a shop. Watch which one gets read. That's the answer.

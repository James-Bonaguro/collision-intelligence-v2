# Collision Intelligence — V2.1 (Field Edition, Voice-Corrected)

**Industry-native rewrite of V2.0.**
April 2026 · Intersection Strategies LLC

---

## The Learning Arc

This repo is the second generation of a three-version learning cycle.

- **V1** (Opus 4.6, 13 pages, 13,639 lines): exhaustive internal briefing. Industry-native voice. Approved by field readers including James's uncle (Mercedes-Benz dealership owner). Repo: [collision-intelligence](https://github.com/James-Bonaguro/collision-intelligence).
- **V2.0** (Opus 4.7, 6 pages, ~3,500 lines, April 16): mobile-first redesign with aggressive plain-English. **Failed the field test by a warm network connect for discovey.** Quot: *"There's no emotion in this; there's no reason anyone should care. It's like I'm talking to a baby."* The plain-English brief was the wrong interpretation of "simplify."
- **V2.1** (Opus 4.7, 6 pages, this repo, April 16 same-day correction): **voice transplant in place.** V1's industry-native voice, peer-to-peer register, and declarative headlines — transplanted onto V2.0's 6-page structural bones.

Field deployment strategy: V1 stays live as the maximalist reference. V2.1 replaces V2.0 at the same URL (`james-bonaguro.github.io/collision-intelligence-v2`). Both go into shop visits; whichever reads better becomes the external-facing standard.

---

## What V2.1 Corrects

| Dimension | V2.0 (failed) | V2.1 (this version) |
|---|---|---|
| **Voice** | Plain-English, "explain every term" | Industry-native, tooltip on first use only |
| **Headlines** | Question-led ("Where does the money leak?") | Declarative ("The Five Leaks Bleeding Every Collision Shop") |
| **Vocabulary** | Avoided E01, DEG, P-Page, sublet, teardown | Uses them freely with inline tooltips |
| **Agent names** | Softened ("It tells you which cars will total") | V1 canonical ("E01 Pre-Cognition & Teardown Defender") |
| **Layout** | Single-column 680px mobile-first | Laptop-first 960px, multi-column desktop sections |
| **Body font** | 18px mobile-first | 16px desktop / 17px mobile (density over thumb-reading) |
| **Drop caps** | Every page lede | Removed — too magazine, not enough industry |
| **Register** | Calm, explanatory | Stakes-carrying, peer-to-peer, urgent where urgency is real |
| **Audience posture** | Phone between jobs | Laptop with a coffee, evaluating |

## What V2.1 Keeps From V2.0

- 6-page architecture: `index`, `the-problem`, `the-agents`, `the-math`, `how-it-works`, `glossary`
- Enforced reading order — big Prev/Next buttons at the bottom of every page
- Progress bar at top of every content page (Page X of 5)
- Inline term tooltips via pure CSS (no JavaScript)
- Dedicated glossary page with alphabetical jump-nav
- Agent 04 flagship treatment — dark card, crimson "Flagship · Lead With This" ribbon, top position
- Color palette (charcoal + crimson)
- Trigger code blocks on each agent (new in V2.1)

---

## File Inventory

| # | File | Purpose |
|---|------|---------|
| 1 | `index.html` | Landing. Hero: "Five agents. Five leaks. One managed service." Three outcomes, thesis, reading guide, CTA. |
| 2 | `the-problem.html` | Page 1 of 5. The Five Leaks — P-Page Scrub Gap, E01 Teardown Waste, The Portal Tax, Sublet Reconciliation Drag, EV Compliance Liability. Industry-native voice with first-use tooltips. |
| 3 | `the-agents.html` | Page 2 of 5. Five agents with V1 names restored. Trigger code block per agent. Agent 04 (E01 Pre-Cognition & Teardown Defender) as flagship. |
| 4 | `the-math.html` | Page 3 of 5. $33,000/mo hero. Industry-native breakdown table (E01 teardown defense, P-Page scrub recovery, ECD sync leverage, Sublet markup capture, EV compliance billing). Three tiers (Single-Agent / Stack / Enterprise MSO). 90-day pilot as three windows. |
| 5 | `how-it-works.html` | Page 4 of 5. Three-layer diagram (Trigger / Routine / Output). Named stack: Claude Code Routines, MCP, CCC Secure Share, Mitchell Transactional API, Audatex/Solera OAS3, Enterprise ARMS, Hertz HIRS, I-CAR RTS. Security posture (6 cards), FAQ (6 questions). |
| 6 | `glossary.html` | Page 5 of 5. Plain-English dictionary of every term in the hub. Alphabetical jump-nav. Expanded for V2.1 with MCP, Claude Code Routines, MSO, CRIB 188, LKQ, I-CAR RTS, ImageAttachment API, OAS3, Portal Tax, Workfile, and more. |

Plus: `DESIGN_SYSTEM.md` (single source of truth for V2.1 voice rules) and `source/research-report.md` (ground-truth research, unchanged from V1).

---

## How to View

Open `index.html` in any modern browser. **Laptop-first** (tested 360px → 1440px+, optimized for 1024–1440). The document assumes a reader who is sitting down to evaluate, not skimming on a phone.

The reading order is enforced: every page has a "Next →" button at the bottom and a progress bar at the top.

---

## V2.1 Design Notes

- Body copy: **16px desktop, 17px mobile**. Tighter than V2.0 to allow more information density on the page a shop owner will actually read from.
- Container: **960px primary**, 1120px where the nav needs more room. Multi-column grids at ≥1024px.
- Every interactive target is **≥48×48px**; page-nav buttons are **64px tall**.
- Zero external JavaScript. Tooltips work via pure CSS (`:hover` + `:focus-within`).
- Trigger code blocks on each agent use JetBrains Mono to signal technical credibility without feeling like developer documentation.
- Industry terms (`<span class="term">`) use a dotted crimson underline with a dark-card tooltip on first occurrence per page. Every term also appears in the glossary.

---

## How to Use in a Shop Conversation

Same pathway as V1 — **but designed to be handed over**, not narrated.

1. Hand them your laptop with `index.html` open (or your tablet in landscape).
2. Let them scroll the three outcomes and hit "Start reading."
3. Stay quiet. The document is written to carry a shop owner through the five pages in ten minutes.
4. When they finish, ask what resonated. Don't lecture.

If an adjacent reader (controller, partner, lender) sees an unfamiliar term, the glossary link is always in the top right. One tap.

---

## Parent Context

Part of the **Intersection Strategies LLC** trigger-based agent product line. See `..\CLAUDE.md` in the parent directory for the business context.

Sibling projects:
- **V1 briefing** (maximalist reference) — [collision-intelligence](https://github.com/James-Bonaguro/collision-intelligence)
- **Insurance broker proof** — [Broker](https://github.com/James-Bonaguro/Broker)

---

## Field Testing

V1 vs. V2.1 A/B test. Both go into shop visits with local collision shops this week.

The question: does V1's density + ornate formatting win, or does V2.1's cleaner structure with the same voice win? The winner becomes the external-facing standard. Take both into a shop. Watch which one gets read. That's the answer.

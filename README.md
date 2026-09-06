# 🌱 Neev — a situation-led investing course + practice app (India)

**Neev** (नींव — *foundation*) teaches investing to Indian beginners the way money problems actually
arrive in real life: **situation → the right way to decide.** Every lesson opens with a scene you
could genuinely be in this week, shows the tempting-but-wrong reflex, busts the myth behind it, then
hands you a framework to reason the call yourself. It **never recommends a specific stock or fund** —
it trains judgement, and you practise with virtual money on real market data.

> Status: **all 9 modules · 52 lessons · fully trilingual (English / हिंदी / Hinglish)** in an interactive app. Video for Lesson 3 is scripted (see `content/`) but not yet produced.

---

## What's in this folder

```
neev/
├── index.html                     # ▶ The full interactive app prototype (open this)
├── README.md
├── content/
│   ├── module-1.json              # Module 1 — 6 lessons, machine-readable (7-beat + myth schema)
│   └── video-storyboard-lesson-3.md  # Shot-by-shot video plan for the FFmpeg/Manim pipeline
└── design/
    ├── lesson-mockup.html         # Early lesson-screen mockup (2 phones)
    ├── compounding-simulator.html # Standalone compounding simulator
    └── course-blueprint.html      # Situation-led course design: all 7 modules + Module 1 in full
```

**Open `index.html` in any browser** — no build step, no server. Progress (XP, streak, badges) is
saved in `localStorage` on your device.

---

## The 7-beat lesson

Every lesson follows the same story shape so the method is consistent and repeatable:

1. **Situation** — a specific, relatable Indian scene
2. **The myth** — a common false belief, struck through → the truth
3. **The reflex** — what most people do on autopilot
4. **The real question** — what the scene is actually forcing (usually "when do I need it / can I bear it")
5. **The framework** — the concept that answers it (max 2 terms, each defined once)
6. **Your call** — the redirect: depends on *your* horizon, liquidity, risk capacity — never a named product
7. **Your move today** — one action with virtual money on real data + a reflection

## The course — all 9 modules built (52 lessons, fully trilingual)

`get money → budget → clear debt → understand options → gauge your risk → make a plan → dodge mistakes → tax & paperwork → run it yourself`

Every module is written in full in **English, हिंदी, and Hinglish**, and unlocks when the previous one is complete.

1. **Paisa aaya — ab kya?** (Foundations) — 6 lessons
2. **Budgeting: paisa kahan jaata hai?** — 50-30-20, 40-30-30, needs vs wants, pay-yourself-first — 4
3. **Loans & debt: sambhaalo, khatam karo** — good/bad debt, EMI/amortization, credit-card trap, avalanche vs snowball, prepayment, closing to NOC — 6
4. **Kahaan rakhein? Options** — equity vs debt, one stock vs a basket, gold, fixed vs market-linked, direct vs managed, match type to goal — 6
5. **Kitna risk theek hai?** — drawdowns, capacity vs tolerance, diversification, concentration risk, risk = horizon, sleep test — 6
6. **Plan banao** — goal-based investing, lumpsum vs SIP, allocation, step-up, rebalancing, review cadence — 6
7. **Galtiyan jo mehngi padti hain** — return chasing, timing, FOMO/herd, over-monitoring, scam red flags, panic selling — 6
8. **Tax, fees aur paperwork** — capital gains, fees compounding, KYC/demat/folio, nominee, tax-saving trap, reading statements — 6
9. **Sab jodo: chalao** *(capstone)* — write your plan, backtest, stress a crash, half-yearly review, squad, graduation — 6

## App features in the prototype

- **Lesson player** — the 7 beats with staggered reveal, myth-bust card, quiz (with confetti), practical action, reflection, and a completion screen
- **Compounding simulator** — lumpsum/SIP, live curve with a highlighted "bend", 5/15/25-yr comparison
- **Virtual portfolio** — buckets donut + sample market row (live app fetches real AMFI/exchange data)
- **Squad** — friends leaderboard + weekly streak challenge
- **Scorecard (You)** — XP with Hindi growth levels (Beej → Ankur → Paudha → Ped → Van), streak flames, achievement badges, concept-mastery bars, investor archetype
- Light/dark theme, offline-friendly, single file

## Hard content rules (enforced in every lesson)

- No specific instrument, fund, or stock is ever named or recommended
- India-specific tax/fee/regulatory points, always flagged `(verify current rate before relying on this)`
- Max 2 technical terms per lesson, each defined in one plain sentence
- Every lesson ends in a practical action tied to a **real fetchable** data point
- No invented statistics, no fear-based language

## Roadmap

- [x] Write all 9 modules (52 lessons), fully trilingual + detailed, with Deep Dives
- [x] Multi-module engine with progressive unlock; PWA / offline; language switch
- [ ] Push to GitHub + enable Pages for a shareable, installable link
- [ ] Wire the practical actions to a live data source (AMFI daily NAV flat file is the easy on-ramp)
- [ ] Build the time-compression / backtest + stress-test engine the capstone references
- [ ] Produce Lesson 3 video from the storyboard (Manim + TTS + FFmpeg)
- [ ] Reconcile `content/module-1.json` with the in-app trilingual content
- [ ] Real Squad invites; server-side progress

---

*Prototype for personal + friends use first. Educational content only — not investment advice.*

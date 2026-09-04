# 🌱 Neev — a situation-led investing course + practice app (India)

**Neev** (नींव — *foundation*) teaches investing to Indian beginners the way money problems actually
arrive in real life: **situation → the right way to decide.** Every lesson opens with a scene you
could genuinely be in this week, shows the tempting-but-wrong reflex, busts the myth behind it, then
hands you a framework to reason the call yourself. It **never recommends a specific stock or fund** —
it trains judgement, and you practise with virtual money on real market data.

> Prototype status: **content + interactive app prototype**. Video is scripted but not yet produced.

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

## The course (situation-led arc)

`get money → understand options → gauge your risk → make a plan → dodge costly mistakes → tax & paperwork → run it yourself`

1. **Paisa aaya — ab kya?** (built, 6 lessons)
2. Kahaan rakhein? Options samjho
3. Kitna risk theek hai?
4. Ab plan banao
5. Galtiyan jo mehngi padti hain
6. Tax, Fees aur Paperwork
7. Sab jodo: portfolio chalao *(capstone)*

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

- [ ] Wire the practical actions to a live data source (AMFI daily NAV flat file is the easy on-ramp)
- [ ] Time-compression / historical backtest engine (Module 7)
- [ ] Produce Module 1 videos from the storyboard (Manim + TTS + FFmpeg)
- [ ] Write Modules 2–7 content
- [ ] Real Squad invites; server-side progress

---

*Prototype for personal + friends use first. Educational content only — not investment advice.*

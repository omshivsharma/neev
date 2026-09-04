# Lesson 3 Video Storyboard — "Return on Your Returns" (Compounding)

**Runtime:** ~78 sec · **Orientation:** vertical 1080×1920 · **Streak credit:** viewer must reach 0:55 (70%)
**Voice:** Hinglish, warm, unhurried — Indian-English neural TTS (Azure `en-IN` Neerja / Google `en-IN` Wavenet), Hindi words kept in Latin script in the SSML so the voice reads them naturally.
**Pipeline:** reuses your birthday-generator FFmpeg stack. New here: 2 Manim clips replace 2 Ken-Burns stills; everything else is Ken-Burns-on-image + text overlay + crossfade, exactly as before.

---

## Shot list

| # | Time | Visual (source) | On-screen text | Voiceover (Hinglish) | Transition |
|---|------|-----------------|----------------|----------------------|------------|
| 1 | 0:00–0:09 | **Image** — a single ₹200-ish scene: one Swiggy-style food order on a table. Slow Ken Burns push-in. | `₹200. Bas itna.` (lower third) | "Yeh ₹200 — ek chhota Swiggy order jitna paisa. Chalo isse kaam pe lagate hain." | Cut → crossfade |
| 2 | 0:09–0:25 | **Image** — same note with a small coin stacking beside it; gentle Ken Burns up. | `Saal 1: return on ₹200` | "Invest karo, aur har saal thoda return milta hai. Pehle saal — return on your ₹200. Simple." | Crossfade |
| 3 | 0:25–0:43 | **Manim clip A** — original ₹200 block; a smaller "return" block lands on top; next year an arrow shows the *return itself* earning its own tiny return. Labels animate in. | `Return on your return` | "Lekin agle saal? Aapko return milta hai apne original paise pe — AUR pichhle saal ke return pe bhi. Paisa khud paisa banata hai. Isko compounding kehte hain." | Match-cut to curve |
| 4 | 0:43–0:58 | **Manim clip B** — a growth curve draws left-to-right: long flat stretch, then a clear upward *bend* in later years. A dot rides the curve; the bend gets a highlight ring. | `Asli kamaal — baad mein` | "Shuru mein curve flat lagta hai — lagta hai kuch ho hi nahi raha. Sabar rakho. Asli kamaal baad ke saalon mein hota hai, jab snowball bada ho jaata hai." | Crossfade |
| 5 | 0:58–1:10 | **Manim clip B (cont.) / split** — two curves side by side: "Shuru 25 saal" vs "Shuru 35 saal", the earlier-start curve pulling clearly higher. | `Time = sabse bada lever` | "Do cheezein sab decide karti hain — kitna time, aur kya aap paisa beech mein nikaalte ho. Jaldi shuru karo, woh time hi jeet hai." | Crossfade |
| 6 | 1:10–1:18 | **Screen-record** — the app's compounding simulator, finger drags the years slider 5 → 25, curve bends live. Ends on app logo. | `App mein khud dekho →` | "Baaki? Aaj app mein khud dekhte hain. Apne ₹500 ko aage chala ke, woh bend dhoondo." | Fade to card |

---

## Full narration script (paste into TTS, one block)

> Yeh ₹200 — ek chhota Swiggy order jitna paisa. Chalo isse kaam pe lagate hain.
> Invest karo, aur har saal thoda return milta hai. Pehle saal — return on your ₹200. Simple.
> Lekin agle saal? Aapko return milta hai apne original paise pe — aur pichhle saal ke return pe bhi. Paisa khud paisa banata hai. Isko compounding kehte hain.
> Shuru mein curve flat lagta hai — lagta hai kuch ho hi nahi raha. Sabar rakho. Asli kamaal baad ke saalon mein hota hai, jab snowball bada ho jaata hai.
> Do cheezein sab decide karti hain — kitna time, aur kya aap paisa beech mein nikaalte ho. Jaldi shuru karo, woh time hi jeet hai.
> Baaki? Aaj app mein khud dekhte hain. Apne ₹500 ko aage chala ke, woh bend dhoondo.

**TTS notes**
- Rate ~0.94 (slightly slow, beginner-friendly). Add a 350–500 ms pause between shots (SSML `<break>`), which also gives room for text overlays to land.
- Keep "compounding", "return", "invest", "slider" in English; let the neural voice handle them — don't phonetically respell.
- Render narration first, read each segment's real duration, THEN set each shot's on-screen length to match (audio drives timing, not the reverse).

---

## Asset checklist

**Images (3)** — real/stock, not invented data:
- [ ] `01_order.jpg` — a single modest food order on a table (context, no branding).
- [ ] `02_coin.jpg` — the same setup with a small coin stack (the "return").
- [ ] (curve visuals come from Manim, not stills.)

**Manim clips (2)** — clean, one idea each, brand colors `#0E8C6B` (accent) + `#D9922B` (gold for the bend):
- [ ] `manimA_return_on_return.mp4` — stacking blocks: principal → return → return-on-return.
- [ ] `manimB_bend.mp4` — the flat-then-bend curve, plus the 25-vs-35 split at the end.

**Screen recording (1):**
- [ ] `sim_scrub.mp4` — 6 sec capture of the compounding simulator, years slider dragged 5→25.

**Audio:**
- [ ] `vo.wav` — full narration (above).
- [ ] Optional soft bed track under −22 dB, ducked beneath VO.

---

## Manim scene notes (fits your Python stack)

**Clip A — return on return (~14s)**
- `Square` for the ₹200 principal (accent fill). `.animate` a smaller square ("Return Y1") landing on top.
- Year 2: a still-smaller gold square lands on the *return* square, with an arrow + label "return earns its own return".
- Keep labels in a light sans; hold the final frame 1s for the match-cut.

**Clip B — the bend (~20s incl. split)**
- `Axes` (hide numbers — this is a shape, not a data claim). Plot `y = P*(1+r)^x` with `create()` animation so the curve draws in.
- Add a `Dot` with `MoveAlongPath`. When x enters the later years, flash a gold `Circle` ring at the bend + text "yahan se steep".
- Split: two curves, start-at-25 vs start-at-35 (shift the second's start right along x). Earlier curve ends visibly higher. Label both.
- **No axis numbers / no y-values** — the video teaches the *shape*; real numbers live only in the app simulator (keeps the "no invented statistics" rule and means this clip never goes stale).

---

## FFmpeg assembly (same pattern as birthday generator)

1. Ken-Burns the 2 stills to clips (`zoompan`), each cut to its VO segment length.
2. Concatenate: `01 → 02 → manimA → manimB → sim_scrub` with 300 ms `xfade` crossfades.
3. Overlay lower-third text per shot via `drawtext` (or pre-baked PNG overlays with alpha) on the brand green bar.
4. Mux `vo.wav` (+ ducked bed) over the full timeline; normalize to −16 LUFS.
5. Export 1080×1920, H.264, ~30 fps.
6. Burn a subtle gold progress tick at the 0:55 mark reference is handled in-app, not in the file.

**Golden rule for this pipeline:** never bake a rupee *value* or a percentage into the video. The video teaches the concept (evergreen, render once); every real, current number appears in the app layer after the video. That's why Manim clips show shape, not figures.

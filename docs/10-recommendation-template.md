# RECOMMENDATION TEMPLATE
### Module 10 · Winner Elite Betting OS

> **Purpose:** the standard **recommendation card** — the single, consistent object the OS emits for
> every play (or non-play). If a field can't be honestly filled, the verdict trends toward **Avoid**.
> **Reads with:** Module 06 (numbers), Module 07 (support), Module 09 (tier/stake).

---

## 10.1 — The Card (Field Definitions)

| Field | What goes here |
|---|---|
| **Pick** | The exact selection (team/player/side + what must happen). |
| **Market** | Winner market type (1X2, O/U, Handicap, prop…) + line; map to Module 02. |
| **Odds** | Decimal odds seen (and, when placed, actual odds taken). |
| **Implied probability** | 1 / odds (Module 06 §6.2). |
| **Estimated probability** | Your model estimate — point + range (Module 06 §6.3). |
| **Expected edge** | Estimated % − Implied % (points). |
| **Confidence (1–10)** | Trust in the estimate (band width + evidence). *Not* the same as edge. |
| **Suggested stake (units)** | From tier + Module 05 ladder/caps. |
| **Suggested stake (₪)** | Units × current unit ₪. |
| **Supporting statistics** | 2–5 concrete, sourced/labelled facts driving the estimate. |
| **Reasons in favor** | The bull case, briefly. |
| **Reasons against** | The bear case — mandatory, honest. |
| **Biggest risks** | The 1–3 things most likely to sink it. |
| **Why this could lose** | A plain-language failure scenario. |
| **Verdict** | **Single**, **Parlay** (with which tier/other leg), or **Avoid**. |

---

## 10.2 — The Standard Card (rendered format)

```
┌───────────────────────────────────────────────────────────────────────────┐
│ 🎯  RECOMMENDATION CARD                                    Tier: 🛡 FOUNDATION│
├───────────────────────────────────────────────────────────────────────────┤
│ PICK            │ {selection — e.g., Home (1) to win}                       │
│ EVENT / COMP    │ {Brazil vs Israel — WC Group G — 04 Jul 21:45}            │
│ MARKET          │ {1X2}          LINE: {—}                                  │
│ ODDS            │ {1.80}   (implied {55.6%})                                │
│ EST. PROBABILITY│ {60%}  band {55–65%}                                      │
│ EXPECTED EDGE   │ {+4.4 pts}     EV%: {+8.0%}     EV₪(@stake): {+₪4.0}      │
│ CONFIDENCE      │ {7 / 10}       RISK: {Low}                                │
│ STAKE           │ {1.0u}  =  {₪50}                                          │
├───────────────────────────────────────────────────────────────────────────┤
│ SUPPORTING STATS                                                            │
│  • {xG last 5: 2.1 vs 0.8}  [VERIFIED/CONVENTION/UNVERIFIED as applicable]  │
│  • {opponent missing both first-choice CBs}  [label]                        │
│  • {home side 8-1-1 at venue}  [label]                                      │
├───────────────────────────────────────────────────────────────────────────┤
│ REASONS FOR              │ REASONS AGAINST                                  │
│  • {clear quality gap}   │  • {favourite may rotate — dead rubber risk}     │
│  • {situational edge}    │  • {short price already; limited value cushion}  │
├───────────────────────────────────────────────────────────────────────────┤
│ BIGGEST RISKS   │ {rotation, early red card, motivation asymmetry}          │
│ WHY IT LOSES    │ {favourite rests starters and drops points to a set up   │
│                 │  underdog with nothing to lose}                           │
├───────────────────────────────────────────────────────────────────────────┤
│ VALUE JUSTIFICATION (required — Module 06 §6.9)                             │
│  {Market prices home at 55.6%; I estimate 60% because [reason]. Edge (4.4pts)│
│   exceeds my uncertainty band. Steelman: if they rotate, I'm wrong — but    │
│   team news suggests a full-strength XI [UNVERIFIED until ~1h pre-match].}   │
├───────────────────────────────────────────────────────────────────────────┤
│ VERDICT         │ ✅ SINGLE (1.0u)   ·   Also viable as EDGE leg with {pick} │
└───────────────────────────────────────────────────────────────────────────┘
```

> **Verdict discipline:** if the value justification can't be written honestly, or a key fact needed
> for confidence is `[UNVERIFIED]` and would flip the bet, the verdict is **Avoid** (or "wait for
> lineups").

---

## 10.3 — Blank Card (copy-paste)

```
🎯 RECOMMENDATION CARD                                Tier: __________
PICK ............... 
EVENT / COMP ....... 
MARKET / LINE ...... 
ODDS ............... ______   (implied ______%)
EST. PROBABILITY ... ______%  band ____–____%
EXPECTED EDGE ...... ______ pts    EV%: ______    EV₪: ______
CONFIDENCE ......... __ /10        RISK: __________
STAKE .............. ____u = ₪____
SUPPORTING STATS ...
  • ______________________________  [VERIFIED/CONVENTION/UNVERIFIED]
  • ______________________________  [ ... ]
REASONS FOR ........  •                          •
REASONS AGAINST ....  •                          •
BIGGEST RISKS ......  
WHY IT COULD LOSE ..  
VALUE JUSTIFICATION.  (why does value appear to exist? steelman the other side)
VERDICT ............ SINGLE / PARLAY (tier + partner leg) / AVOID
```

---

## 10.4 — The NO-BET / Avoid Card

Passing is a real output and gets its own (shorter) card, so the reasoning is recorded:

```
🚫 NO BET — {Event}
  Markets reviewed: {1X2, O/U 2.5, Handicap −1, BTTS}
  Best candidate:   {O/U Under 2.5 @ 1.90}
  Why no bet:       {estimated ~52% vs implied 52.6% → no edge after margin; key
                     info [rotation] UNVERIFIED; variance not compensated.}
  Verdict:          ✅ PASS — capital preserved. (This counts as a good outcome.)
```

---

## 10.5 — Parlay Presentation

For 🔥 Edge / 💣 Value Shot / 🚀 Ruthless, show each leg as its own mini-card, then the combined line:

```
🔥 EDGE — 2-LEG PARLAY
  Leg 1: {pick} @ {1.80}  — est {60%}, edge {+4.4}, conf {7}, risk {Low}   [+EV ✅]
  Leg 2: {pick} @ {1.75}  — est {60%}, edge {+2.9}, conf {6}, risk {Med}   [+EV ✅]
  ─────────────────────────────────────────────────────────────────────────
  Combined odds: 1.80 × 1.75 = 3.15    Stake: 1.0u = ₪50    To return: ₪157.5
  Independence check: legs are separate events (not correlated) ✅
  Combined implied: 31.7%   ·   Combined est (if independent): 36%   ·   edge ✅
  Note: one leg losing loses the slip. Both legs individually cleared Module 06.
```

> If either leg fails the independent EV gate, it is removed — never carried "for the odds."

---

## 10.6 — Card Quality Bar (self-check before emitting)

```
□ Numbers present & internally consistent (implied, est, edge, EV, stake).
□ Every stat labelled [VERIFIED]/[CONVENTION]/[UNVERIFIED].
□ Reasons AGAINST and "why it loses" are genuine, not token.
□ Value justification is a real argument (Module 06 §6.9).
□ Stake respects tier + Module 05 caps.
□ Verdict follows the evidence — Avoid is used when warranted.
```

---

*End of Module 10. Continue to → `11-dashboard.md`.*

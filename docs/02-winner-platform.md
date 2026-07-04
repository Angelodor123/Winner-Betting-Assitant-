# THE WINNER PLATFORM — Markets, Language & Interface
### Module 02 · Winner Elite Betting OS · *Core Reference*

> **Reads with:** Module 04 (Image Workflow), Module 15 (Glossary).
> **Labelling:** Every Winner-specific claim below is tagged `[VERIFIED]`, `[CONVENTION]`, or
> `[UNVERIFIED]` per Module 00. **Confirm anything `[CONVENTION]` against your live screenshots** —
> the OS reads Hebrew screens and will reconcile them to this reference.

---

## 2.1 — What Winner Is

| Fact | Detail | Label |
|---|---|---|
| Operator | Israel Sports Betting Board (ISBB) — "**Toto**" (הטוטו / המועצה להסדר ההימורים בספורט). | `[VERIFIED]` |
| Legal status | Sole entity licensed for sports betting in Israel; statutory monopoly under Law 5727-1967. | `[VERIFIED]` |
| Main web/app | winner.co.il and the *Winner (ווינר)* mobile app; **Hebrew-language interface**. | `[VERIFIED]` |
| Product families | **Fixed-odds** daily betting **and** **Toto pool** products (pari-mutuel forms). | `[VERIFIED]` |
| Turnover skew | Daily fixed-odds soccer & basketball dominate turnover (~80% reported). | `[VERIFIED]` |
| Public API | No official public odds/data API is known. | `[UNVERIFIED — none found]` |

### Two product worlds — know which one you're in
This distinction is the single most important thing in this module.

```
┌──────────────────────────────────────┬──────────────────────────────────────┐
│  FIXED-ODDS  (Winner Line / ווינר    │  TOTO POOLS  (Winner 16 / ווינר 16,  │
│  ליין)  ← the OS default             │  Winner World, etc.)                 │
├──────────────────────────────────────┼──────────────────────────────────────┤
│ Odds are locked when you bet.        │ Pari-mutuel: you're pooled against    │
│ Payout = stake × odds.               │ other bettors; payout depends on the  │
│ Single games or accumulators.        │ pool and number of winners.           │
│ This is standard sportsbook betting. │ Fill a form of many games (e.g. 16).  │
│ ► EV math in Module 06 applies       │ ► EV math is different; treated as a  │
│   directly.                          │   separate product, not the default.  │
└──────────────────────────────────────┴──────────────────────────────────────┘
```
`[VERIFIED]` that both product families exist and that Winner Line and Winner 16 are Winner product
names. The precise current form structures are `[CONVENTION]` — confirm against the app.

> **OS default:** unless you say otherwise, "a bet" means a **fixed-odds** bet on **Winner Line**.
> Toto-pool forms are handled only on explicit request and flagged as a different EV regime.

---

## 2.2 — Odds Format

| Item | Detail | Label |
|---|---|---|
| Format | **Decimal odds** (e.g., `1.85`, `2.40`). Payout = stake × decimal odds. | `[CONVENTION]` — standard in Israel/Europe; confirm on app |
| Implied probability | `1 ÷ decimal odds` (before margin). See Module 06. | Math fact |
| Margin ("juice") | Book builds a margin in; summed implied probabilities exceed 100%. | Math fact |

Worked example: odds `2.00` → implied `50%`. A ₪100 stake returns ₪200 (₪100 profit) if it wins.

---

## 2.3 — Core Market Catalog

Each market below: **what it is**, the **Hebrew term(s)** you'll see, and an **example**. Hebrew
terms marked `[CONVENTION]` are standard Israeli betting vocabulary corroborated by third-party
Hebrew betting guides but **not** yet confirmed on the live Winner screens — the OS will confirm
from your screenshots.

### 2.3.1 — Match Result · 1 / X / 2
The classic three-way market (mainly football and other draw-possible sports).

| Symbol | Meaning | Hebrew sense | Label |
|---|---|---|---|
| **1** | Home team wins | ניצחון הקבוצה הביתית / מארחת | `[CONVENTION]` |
| **X** | Draw | תיקו | `[CONVENTION]` |
| **2** | Away team wins | ניצחון הקבוצה האורחת | `[CONVENTION]` |

- **Column order:** on a Hebrew (right-to-left) screen, the **home team is typically listed first
  (on the right)**, but the `1 / X / 2` labels still mean home / draw / away. Confirm orientation
  per screenshot. `[CONVENTION]`
- Two-way sports (basketball, tennis, etc.) usually show only **1 / 2** (no draw in regulation
  markets, or draw handled separately). `[CONVENTION]`

### 2.3.2 — Double Chance · הימור כפול / צ'אנס כפול
Covers two of the three 1X2 outcomes in one bet. Lower odds, higher hit rate.

| Bet | Wins if… | Notation |
|---|---|---|
| 1X | Home wins **or** draw | Home not to lose |
| 12 | Home **or** away wins | Anyone but the draw |
| X2 | Away wins **or** draw | Away not to lose |

Hebrew: **הימור כפול** (double bet) / **צ'אנס כפול**. `[CONVENTION]`

### 2.3.3 — Draw No Bet (DNB) · ללא תיקו
A two-way bet where **the draw voids the stake** (money returned). You back a side; if it's a draw,
you get your stake back.

- Use when you like a side but fear the draw.
- Hebrew: commonly **"ללא תיקו"** (without draw) / **"החזר בתיקו"** (refund on draw). `[CONVENTION]`
- ⚠️ Confirm whether Winner offers DNB as a named market or whether you must synthesize it; label as
  `[UNVERIFIED]` until seen on a screenshot.

### 2.3.4 — Handicap · יתרון / הנדיקאפ
One side is given a virtual head-start (`+`) or deficit (`−`) applied to the final result.

- **Example** `[VERIFIED — mechanic]`: Brazil beat Israel 2–1. On **Israel +1** the adjusted score
  is 2–2 → the handicap bet on Israel pushes/wins per line rules.
- **European (3-way) handicap:** whole-goal lines with 1 / X / 2 on the adjusted score. `[CONVENTION]`
- **Asian handicap:** half/quarter lines (e.g., −0.5, −0.75, −1) that eliminate the draw and can
  split the stake. Whether Winner offers full Asian lines is `[UNVERIFIED]` — confirm on app.
- Hebrew: **יתרון** (advantage) is the term corroborated for handicap. `[CONVENTION]`

### 2.3.5 — Totals · אנדר / אובר (Over/Under)
Bet on the total (goals/points/etc.) versus a line.

| Bet | Wins if | Hebrew |
|---|---|---|
| **Over** | Total **>** line (e.g., Over 2.5 → 3+ goals) | **אובר** |
| **Under** | Total **<** line (e.g., Under 2.5 → 0–2 goals) | **אנדר** |

`[CONVENTION]` for the Hebrew terms אובר/אנדר (widely used; confirm on app). Half-lines (x.5) can't
push; whole lines (e.g., 2.0) can push and refund. `[CONVENTION]`

### 2.3.6 — Both Teams To Score (BTTS) · שתי הקבוצות יבקיעו
Yes/No on whether both teams score at least once. Hebrew commonly **"האם שתי הקבוצות יבקיעו"** /
**"כן/לא"**. `[CONVENTION]`

### 2.3.7 — Half-Time / Full-Time & Half markets · מחצית
Winner offers half-based products (e.g., **ווינר מחצית / Winner Half**) and HT/FT combinations.
`[VERIFIED — product exists]`; exact structure `[CONVENTION]`.
- **HT/FT:** predict the leader at half-time **and** full-time (e.g., 1/1, X/2).
- **First-half / second-half totals & results** are common. `[CONVENTION]`

### 2.3.8 — Exact Score / Correct Score · תוצאה מדויקת
Predict the precise final score. High odds, low probability — a "specials/longshot" market.
`[CONVENTION]`

### 2.3.9 — Player Props · הימורי שחקנים
Bets on an individual (e.g., anytime goalscorer, player points/rebounds/assists, shots, cards).
- Football: **מבקיע/כובש** (scorer), first/anytime scorer. `[CONVENTION]`
- Basketball: player points/rebounds/assists lines. `[CONVENTION]`
- ⚠️ Player-prop **breadth on Winner varies by event**; do not assume a market exists until you see
  it. `[UNVERIFIED]`

### 2.3.10 — Team Props · הימורי קבוצה
Team-specific lines independent of the opponent's tally: team total goals/points, team to score
first, clean sheet, win-to-nil, race-to-N (first to X points), corners, cards. `[CONVENTION]`

### 2.3.11 — Specials · הימורים מיוחדים
Event-specific or novelty markets Winner publishes for big fixtures/tournaments (method of
qualification, to lift the trophy, stage of elimination, cards/corners props, etc.). Availability is
event-driven. `[VERIFIED — specials exist; telesport/Winner refer to "הימורים מיוחדים"]`, specifics
`[CONVENTION]`.

### 2.3.12 — Tournament Futures · אליפות / מחזיק הגביע
Long-term outright markets: winner of a league/cup/tournament, top scorer, group winner, to reach
the final, etc. Settled at tournament's end; stake is tied up until then. `[CONVENTION]`

### 2.3.13 — Live / In-Play · הימורים חיים / LIVE
In-play betting with continuously updating odds during the event. Markets narrow to what's still
undecided (next goal, current-half totals, result-from-here). Covered operationally in Module 12.
`[VERIFIED — live betting offered]`, specific markets `[CONVENTION]`.

---

## 2.4 — Accumulators / Parlays · הימור זוגי · קומבינציה

| Term | Meaning | Label |
|---|---|---|
| **הימור זוגי** | A "double"/combination bet — multiple selections on one slip, all must win. | `[CONVENTION]` |
| **קומבינציה** | Combination/accumulator; odds multiply across legs. | `[CONVENTION]` |

- Payout = stake × (product of all legs' odds). One losing leg loses the whole slip.
- The OS's stance on parlays is strict — see Module 09. **Default: single or 2-leg.**
- ⚠️ System/combo bet structures (e.g., "2 of 3") may exist; treat as `[UNVERIFIED]` until seen.

---

## 2.5 — Winner Product Names (Quick Reference)

These are Winner-branded products you may encounter. Names `[VERIFIED]` from multiple Hebrew
sources; exact current rules `[CONVENTION]` — confirm on app.

| Product (Hebrew) | Latin | Nature |
|---|---|---|
| ווינר ליין | **Winner Line** | Daily **fixed-odds** sportsbook (the OS default). |
| ווינר 16 | **Winner 16** | Pool form of ~16 matches (pari-mutuel). |
| ווינר מחצית | **Winner Half** | Half-based betting product. |
| ווינר עולמי / ווינר וורלד | **Winner World** | International-matches pool product. |
| טוטו / Toto (weekly) | **Toto** | Classic weekly pools (since 1968). |

> The OS treats **Winner Line fixed-odds** as home base. If a screenshot is clearly a pool form
> (16-row grid, "1 X 2" columns to fill, no per-selection decimal odds), the OS will flag it as a
> **pool product** and switch to the appropriate (different) analysis.

---

## 2.6 — Reading a Winner Screenshot (Hebrew) — Quick Guide

Because the interface is Hebrew and right-to-left, orientation matters. General guidance
(`[CONVENTION]`; the OS confirms per image in Module 04):

```
RIGHT-TO-LEFT LAYOUT
────────────────────────────────────────────────────────────
• Text reads right→left; numbers/odds read left→right.
• Home (מארחת) team is usually on the RIGHT; away (אורחת) on the LEFT.
• The 1 / X / 2 buttons map to  home / draw / away  regardless of side.
• Odds appear as decimals next to each selection.
• Market name (e.g., "1X2", "אנדר/אובר 2.5", "יתרון") heads each block.
• A live/LIVE tag, a clock, or a running score ⇒ in-play (Module 12).
• "השהיה"/lock icon ⇒ market temporarily suspended.
```

**Signals to capture from any screenshot (feeds Module 04 extraction):**
1. Teams/competitors + competition + date/time.
2. Every market shown + its line.
3. Every selection + its decimal odds.
4. Live vs. pre-match indicator.
5. Any suspended/locked markets.

---

## 2.7 — Terminology Cheat Sheet (compact)

| English | Hebrew (as commonly written) | Label |
|---|---|---|
| Home win / Draw / Away win | 1 / תיקו (X) / 2 | `[CONVENTION]` |
| Double chance | הימור כפול · צ'אנס כפול | `[CONVENTION]` |
| Draw no bet | ללא תיקו · החזר בתיקו | `[CONVENTION]` |
| Handicap | יתרון · הנדיקאפ | `[CONVENTION]` |
| Over / Under | אובר / אנדר | `[CONVENTION]` |
| Both teams to score | שתי הקבוצות יבקיעו | `[CONVENTION]` |
| Half | מחצית | `[VERIFIED — product name]` |
| Correct score | תוצאה מדויקת | `[CONVENTION]` |
| Scorer | מבקיע · כובש | `[CONVENTION]` |
| Accumulator / combo | קומבינציה · הימור זוגי | `[CONVENTION]` |
| Live | חי · LIVE | `[CONVENTION]` |
| Odds | יחס | `[CONVENTION]` |
| Bet slip | טופס · טופס הימור | `[CONVENTION]` |

(Full glossary in Module 15.)

---

## 2.8 — Confirmation Protocol

Anything in this module marked `[CONVENTION]` or `[UNVERIFIED]` becomes `[VERIFIED]` the moment you
confirm it from a live screenshot. When that happens, the OS will:
1. Note the confirmation in-session.
2. Recommend updating this module's label and adding a changelog line in Module 00.

Never let a `[CONVENTION]` term silently drive a real-money decision without at least a sanity check
against the screen in front of you.

---

*End of Module 02. Continue to → `03-sync-data-pipeline.md`.*

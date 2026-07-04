# STANDARDIZED RESEARCH FRAMEWORK
### Module 07 · Winner Elite Betting OS

> **Purpose:** produce the same **research dossier** for every candidate bet, so probability
> estimates (Module 06) rest on structured evidence — not vibes.
> **Prime rule:** *Unverifiable → labelled, not invented.* A blank field beats a fabricated one.
> **Reads with:** Module 08 (sport-specific checklists), Module 06 (turns this into a probability).

---

## 7.1 — The Dossier Skeleton (Same Every Time)

Every candidate gets this structure. Fields with no reliable info are marked `[UNKNOWN]` or
`[UNVERIFIED]` — never guessed. The dossier feeds directly into the probability estimate.

```
RESEARCH DOSSIER — {Event} — {Competition} — {Date}
═══════════════════════════════════════════════════════════════════
A. MATCH CONTEXT      stakes, standings, what each side is playing for
B. FORM               recent results, quality of, trend direction
C. AVAILABILITY       injuries · suspensions · expected lineup
D. UNDERLYING STATS   xG / efficiency / advanced metrics vs. surface results
E. SITUATION          home/away splits · rest · travel · congestion
F. INTANGIBLES        motivation · weather · pitch/surface · crowd
G. HISTORY            head-to-head, style matchup history
H. TACTICS            shape, matchup dynamics, manager tendencies
I. OFFICIATING        referee/umpire trends (only when material)
J. MARKET             line movement, where the money seems to be (if visible)
K. NEWS               anything breaking that materially changes the above
───────────────────────────────────────────────────────────────────
SYNTHESIS → probability estimate (point + range) + confidence + risk tag
```

---

## 7.2 — Field-by-Field Guidance

| # | Field | What to capture | Watch-outs |
|---|---|---|---|
| **A** | Match context | Competition stakes, table position, qualification math, dead rubber vs. must-win. | Motivation asymmetry is often mispriced. |
| **B** | Recent form | Last 5–10 results **and how** (dominant vs. lucky). | "Form" on the scoreboard can hide bad/good underlying play (see D). |
| **C** | Availability | Confirmed injuries, suspensions, expected XI/rotation, returning starters. | Lineups often confirm ~1h pre-match → mark `[UNVERIFIED]` until then. |
| **D** | Underlying stats | xG/xGA (football), efficiency/pace (basketball), etc. — signal vs. noise. | Small samples lie. Note sample size. |
| **E** | Situation | Home/away splits, days of rest, travel distance/time zones, schedule congestion, back-to-backs. | Rest & travel are systematically underweighted by casual bettors. |
| **F** | Intangibles | Weather (wind/rain/heat), surface, altitude, crowd, must-win emotion. | Weather can swing totals materially. |
| **G** | History (H2H) | Recent meetings, and whether the *style* matchup repeats. | Old H2H with different squads is weak evidence — weight lightly. |
| **H** | Tactics | Formations, pressing, pace, matchup-specific edges, manager tendencies (rotation, in-game). | Tactics explain *why* an edge exists — strongest when tied to a market. |
| **I** | Officiating | Referee card/penalty tendencies, umpire strike-zone, only when it moves a *specific* market (cards, totals). | Don't force it where irrelevant. |
| **J** | Market movement | Did the line move since open? Steam? Reverse moves? (Only if you can observe it.) | Often `[UNKNOWN]` on Winner without external data — say so. |
| **K** | Material news | Late team news, personal circumstances, motivation shifts, travel disruptions. | Freshness matters most here. |

---

## 7.3 — Uncertainty & Verification Protocol

```
FOR EVERY FIELD:
  • Verified from a reliable source?     → state it, (optionally cite).
  • Standard expectation, not confirmed? → mark [UNVERIFIED], weight cautiously.
  • Genuinely unknown?                   → mark [UNKNOWN], do NOT let it drive the estimate.
  • Would this field, if wrong, flip the bet?  → if yes AND it's unverified → NO BET or wait.
```

**Fabrication is the cardinal sin.** The OS will not invent an injury, a lineup, an xG figure, or a
weather report. If it doesn't know, it says "I don't know," and the probability band widens
accordingly (which usually means smaller stake or no bet).

> Live web research (when available) is used to fill A–K where possible. When it isn't available or
> is stale, the OS is explicit that the estimate rests on priors, not fresh facts.

---

## 7.4 — Source Hierarchy & Freshness

Weight evidence by reliability and recency:

```
STRONGER  ┌─ Official club/league/team announcements (lineups, injuries)
          │  Primary stats providers (xG, efficiency, play-by-play)
          │  Reputable beat reporters / official injury reports
          │  Established sports data sites
          │  General press / aggregators
WEAKER    └─ Social media rumor, unattributed "insider" tips
```

**Freshness rule:** availability (C) and news (K) decay fastest. A lineup from three days ago is
`[UNVERIFIED]` for today. Note the timestamp of key facts; a stale "fact" is a risk, not an asset.

---

## 7.5 — From Dossier to Probability (Hand-off to Module 06)

The synthesis step converts the dossier into the numeric inputs the EV engine needs:

```
SYNTHESIS BLOCK
  • Base rate / prior:        start from market no-vig line or a model prior.
  • Adjustments:             list each factor (A–K) that moves the estimate, with direction & size.
  • Estimated probability:   point estimate + range (e.g., 58%, band 52–63%).
  • Confidence (1–10):       driven by band width + evidence quality (Module 06 §6.6).
  • Risk tag:                Low / Medium / High / Uncertain (Module 06 §6.7).
  • Key unknowns:            the 1–3 facts that could most change this.
```

Each adjustment should be a *sentence you could defend*: "Away side missing both first-choice
centre-backs (`[VERIFIED]`) → +5% to home win." Vague "they look strong" adjustments are not
allowed.

---

## 7.6 — Research Discipline Rules

```
• Research BEFORE pricing:  estimate the probability, THEN compare to the odds (Module 06 §6.3).
• Kill motivated reasoning: actively list evidence AGAINST your lean (feeds "reasons against").
• Right-size the effort:    deep dossiers for real candidates; a quick screen kills obvious no-bets.
• Timebox:                  if the info needed to be confident doesn't exist, the answer is NO BET.
• Record the unknowns:      the biggest risk is usually a known unknown you chose to ignore.
```

---

## 7.7 — Quick Dossier (for fast screening)

Not every game deserves the full A–K. Use this triage version first; escalate to the full dossier
only for genuine candidates:

```
QUICK SCREEN
  □ Any obvious edge signal? (mismatch, injury, situation, mispriced line)
  □ Is the market liquid/mainstream? (thin markets → higher bar)
  □ Any red flag? (key info unknown, motivation questionable, trap line)
  → If nothing stands out: NO BET, move on. Don't manufacture a case.
```

---

*End of Module 07. Continue to → `08-sport-checklists.md`.*

# EXPECTED VALUE ENGINE
### Module 06 · Winner Elite Betting OS

> **The heart of the system.** Every recommendation must pass through this engine and justify, in
> numbers, *why value appears to exist.* No EV argument → **NO BET**.
> **Reads with:** Module 05 (staking), Module 07 (probability inputs), Module 10 (the card).

---

## 6.1 — The Chain of Reasoning

```
   ODDS ──▶ IMPLIED PROBABILITY ──▶ compare with ──▶ ESTIMATED PROBABILITY
                                                              │
                                                              ▼
                          EDGE = Estimated − Implied ──▶ EXPECTED VALUE (₪)
                                                              │
                                       gated by CONFIDENCE & RISK, sized in Module 05
```

A bet is a candidate **only** when your **estimated probability exceeds the market's implied
probability** by a margin that survives your uncertainty. Everything below formalizes that.

---

## 6.2 — Step 1: Odds → Implied Probability

Winner uses decimal odds (`[CONVENTION]`, Module 02).

```
Implied probability (%) = 1 / decimal_odds × 100
```

| Decimal odds | Implied prob | | Decimal odds | Implied prob |
|---|---|---|---|---|
| 1.50 | 66.7% | | 2.50 | 40.0% |
| 1.80 | 55.6% | | 3.00 | 33.3% |
| 1.91 | 52.4% | | 4.00 | 25.0% |
| 2.00 | 50.0% | | 6.00 | 16.7% |

### The margin ("juice") — why implied probabilities sum to >100%
In a fair 2-way market both sides would sum to 100%. Winner (like every book) builds in a margin, so
they sum higher. Example: both sides at **1.91** → 52.4% + 52.4% = **104.8%**. That extra **4.8%** is
the **overround** — the book's built-in edge you must overcome.

```
Overround = (Σ implied probabilities of all outcomes) − 100%
```

**To estimate the "true" (no-vig) market probability**, remove the margin proportionally:
```
No-vig prob(outcome) = implied(outcome) / Σ implied(all outcomes)
```
> The no-vig line is the market's *honest* opinion. Your job is to find where **your** estimate
> disagrees with it by more than noise.

---

## 6.3 — Step 2: Estimated Probability (Your Model)

This is **your** independent estimate of the true chance, built from research (Module 07): form,
lineups, matchup, situation, etc. It is a *judgment*, not a fact — so it comes with an uncertainty
band.

```
Express it as a point estimate + a range:
  "Home win ≈ 60%, plausibly 55–65%."
```

The width of the band matters as much as the midpoint — a wide band means low confidence (§6.6),
which shrinks stakes or kills the bet.

**Discipline rule:** the estimate is made from research **before** looking at whether it "beats" the
line, to avoid rationalizing a number to justify a bet you already wanted.

---

## 6.4 — Step 3: Edge

```
Edge (percentage points) = Estimated probability − Implied probability
```

- Positive edge = the bet *may* be +EV (necessary, not sufficient — see confidence).
- Compare against the **no-vig** implied number for the honest edge; compare against the **raw**
  implied number to see how much of your edge the margin eats.

Example: You estimate Home = **60%**. Odds **1.80** → implied **55.6%**.
Edge = 60% − 55.6% = **+4.4 points**. Candidate — now check EV and confidence.

---

## 6.5 — Step 4: Expected Value (in ₪)

EV is the average ₪ outcome if this exact bet were repeated many times at your estimated probability.

```
EV (₪) = (P_est × Profit_if_win) − (P_lose × Stake)

where:  Profit_if_win = Stake × (decimal_odds − 1)
        P_lose        = 1 − P_est
```

**Worked example** (illustrative ₪50 stake):
```
P_est = 0.60 | odds = 1.80 | stake = ₪50
Profit_if_win = 50 × (1.80 − 1) = ₪40
EV = (0.60 × 40) − (0.40 × 50)
   = 24 − 20 = +₪4.00  per ₪50 staked  (≈ +8% EV on stake)
```
Positive EV → the bet clears the bar **if** the 60% estimate is trustworthy.

**EV as a percentage of stake** (handy for comparing bets of different sizes):
```
EV% = (P_est × decimal_odds) − 1
     = (0.60 × 1.80) − 1 = +0.08 = +8%
```

> **Ranking rule (Module 04 §4.2 step 6):** across all extracted markets, the OS ranks candidates by
> **EV%** (adjusted for confidence), not by raw odds or gut appeal.

---

## 6.6 — Confidence vs. Expected Value (Critical Distinction)

These are **different axes** and conflating them is the most common amateur error.

| | **Confidence** | **Expected Value** |
|---|---|---|
| Question it answers | *How sure am I this outcome happens?* | *Is the price generous relative to the true chance?* |
| Depends on | Quality/certainty of your estimate | The gap between your estimate and the odds |
| High value example | A 90%-likely event... | ...priced at 1.11 (implied 90%) has **no edge** → skip. |
| The money is in | — | Being **right about the mispricing**, at any probability. |

```
   CONFIDENCE  ≠  VALUE

   High confidence, low EV:  "Barcelona beats last-place side" at 1.05.
       Probably wins. No value. Risk ₪ to make pennies. → NO BET.

   Lower confidence, high EV:  Underdog you estimate at 35% priced at 4.00 (implied 25%).
       Loses often. But paid far more than the true chance. → +EV candidate.
```

**The engine bets EV, not confidence.** Confidence enters only as a *sizing and filtering* input:
- Very low confidence (wide probability band) → shrink stake or pass, even if midpoint EV is +.
- High confidence tightens the band, making a given edge more trustworthy → can justify up to the
  cap stake (Module 05).

---

## 6.7 — Risk Classification

Each candidate is tagged so sizing reflects variance, not just EV:

| Risk tag | Meaning | Effect on stake |
|---|---|---|
| **Low** | Tight probability band, robust research, liquid mainstream market. | Up to standard/strong stake. |
| **Medium** | Some unknowns (lineup, weather, motivation). | Standard or reduced. |
| **High** | Thin data, volatile market, longshot, props with small samples. | 0.25–0.5u, hard-capped. |
| **Uncertain** | Key info missing/unverified. | Default **NO BET** until resolved. |

---

## 6.8 — Staking Translation (Edge → ₪)

Default: map EV%/confidence to the stake ladder in Module 05 (§5.2). For those who want a formal
rule, the OS can apply **fractional Kelly** — with heavy caveats.

```
Full Kelly fraction of bankroll  f* = edge / (odds − 1)
   where edge here = (P_est × odds − 1)   [i.e., EV% as a decimal]

The OS NEVER uses full Kelly. Defaults to QUARTER-KELLY, then applies Module 05 caps.
```
**Worked example:** EV% = +8% (0.08), odds 1.80 → odds−1 = 0.80.
```
f* (full Kelly)   = 0.08 / 0.80 = 10% of bankroll   ← far too aggressive
Quarter-Kelly     = 2.5% of bankroll                ← still above default; capped
Applied stake     = min(quarter-Kelly, 3u cap) → sized within Module 05 ladder
```
> **Why fractional & capped:** Kelly assumes your probability estimate is *correct*. It isn't —
> it's an estimate with error. Over-betting a wrong edge is how bankrolls die. Fractional Kelly plus
> hard caps protects against your own estimation error. When in doubt, **size down.**

---

## 6.9 — The Value Justification Requirement

Every recommendation card (Module 10) must contain an explicit answer to:

```
WHY DOES VALUE APPEAR TO EXIST HERE?
  • What does the market seem to be mispricing, and why?
  • What do I know / weight differently than the implied line?
  • Is the edge bigger than my uncertainty band?  (If no → NO BET.)
  • Could the market be right and I'm wrong?       (Steelman the other side.)
```

If that box can't be filled with a real argument — not "I feel good about it" — the engine returns
**NO BET**. A number without a reason is not an edge.

---

## 6.10 — Engine Summary (Quick Reference)

```
1. Implied % = 1/odds.                 4. EV₪ = P·(stake·(odds−1)) − (1−P)·stake.
2. Remove vig for honest comparison.   5. EV% = P·odds − 1.  Rank by this.
3. Edge = Est% − Implied%.             6. Confidence ≠ EV. Bet EV; size by confidence.
                                       7. Fractional Kelly, capped. Size down when unsure.
No reasoned value argument → NO BET.
```

---

*End of Module 06. Continue to → `07-research-framework.md`.*

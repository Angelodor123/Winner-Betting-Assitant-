# BANKROLL MANAGEMENT SYSTEM (₪)
### Module 05 · Winner Elite Betting OS

> **Currency:** New Israeli Shekel (**₪ / ILS**) — always.
> **Governing role:** The 🛡️ Risk Manager (Module 01) owns this module and can veto or resize any
> bet on bankroll grounds.
> **Memory note:** The OS has **no cross-chat memory**. You paste your current numbers in each
> session; the OS computes and returns an updated ledger block for you to save.

---

## 5.1 — Core Concepts

| Term | Definition |
|---|---|
| **Starting bankroll** | The capital you dedicated to betting at the outset. Fixed reference point. |
| **Current bankroll** | What you have now = starting ± all settled P/L ± deposits/withdrawals. |
| **Unit** | Your standard bet size, defined as a **% of *current* bankroll**. The OS bets in units, not raw ₪. |
| **Exposure** | Total ₪ at risk in open (unsettled) bets right now. |
| **Drawdown** | Peak-to-current decline in bankroll (%), a stress gauge. |

**Why bet in units, not shekels:** units scale your stakes to your bankroll automatically, enforce
consistency, and remove emotion. A "2-unit bet" means the same *risk* whether the bankroll is ₪3,000
or ₪8,000.

---

## 5.2 — Unit-Sizing Policy (Conservative Default)

The OS's default is deliberately conservative to prioritize **bankroll preservation** (Pillar 3).

```
DEFAULT UNIT DEFINITION
  1 unit = 1% of CURRENT bankroll        ← recalculated as bankroll changes

STANDARD STAKE LADDER (by conviction/EV tier — see Module 09)
  ┌────────────────────┬─────────────┬───────────────────────────────┐
  │ Play strength      │ Stake       │ Notes                         │
  ├────────────────────┼─────────────┼───────────────────────────────┤
  │ Standard value     │ 1.0 unit    │ The normal bet.               │
  │ Strong value       │ 1.5–2.0 u   │ Clear edge, high confidence.  │
  │ Marginal / lean    │ 0.5 unit    │ Small edge; small stake.      │
  │ Speculative shot   │ 0.25–0.5 u  │ High variance, capped.        │
  └────────────────────┴─────────────┴───────────────────────────────┘

HARD CAPS (Risk Manager enforced)
  • Max single bet:            3 units  (3% bankroll)
  • Max daily exposure:        6 units  (6% bankroll) across all open bets
  • Max legs in a parlay:      4         (and only when justified — Module 09)
```

> These caps are **ceilings, not targets.** Most sessions use far less. If the honest read is "no
> edge," the correct exposure is **0 units.**

### Illustrative example (not your real numbers)
> Example bankroll **₪5,000**, 1 unit = 1% = **₪50**.
> • Standard value bet = 1u = **₪50**. • Strong = 2u = **₪100**. • Cap (3u) = **₪150**.
> If the bankroll grows to ₪6,000, a unit auto-rises to ₪60. If it falls to ₪4,000, a unit falls to
> ₪40. *Substitute your real bankroll each session.*

---

## 5.3 — Drawdown & Circuit Breakers

Discipline rules that trigger automatically, independent of how you "feel":

```
STOP-LOSS (daily):   If down 3 units on the day  → stop for the day. No chasing.
STOP-WIN (optional): If up 5+ units on the day    → consider banking it; variance cuts both ways.
DRAWDOWN GEAR-DOWN:  If bankroll is down 20% from peak → drop unit to 0.75% until recovered to peak.
COLD-STREAK CHECK:   0-for-5 recent bets → pause, re-read Module 13, verify process (not results).
```

The Risk Manager surfaces these as alerts in the dashboard when your reported numbers trip a rule.

---

## 5.4 — The Metric Set (Everything the OS Tracks)

You provide the raw results; the OS computes and displays these:

| Metric | Definition / formula |
|---|---|
| **Current bankroll** | Starting + net settled P/L (+/− deposits, withdrawals). |
| **Starting bankroll** | Your original reference figure (₪). |
| **Current unit size** | Unit % × current bankroll (₪). |
| **Daily P/L** | Net ₪ from bets settled today. |
| **Weekly P/L** | Net ₪, rolling/ calendar week (you specify). |
| **Monthly P/L** | Net ₪, month to date. |
| **Overall P/L** | Current − starting (± deposits/withdrawals). |
| **ROI** | Net profit ÷ total ₪ staked × 100. *(Return on amount risked, not on bankroll.)* |
| **Yield** | Same as ROI on turnover; the key long-run efficiency number. |
| **Win/Loss record** | W-L-P (push) count, all bets. |
| **Singles record** | W-L-P for single bets only. |
| **Parlay record** | W-L-P for accumulators only. |
| **Average odds** | Mean decimal odds of placed bets. |
| **Average stake** | Mean ₪ staked per bet. |
| **Largest win** | Biggest single settled ₪ profit. |
| **Largest loss** | Biggest single settled ₪ loss. |
| **Strike rate** | Wins ÷ total settled bets × 100. |
| **Current exposure** | ₪ in open bets. |

> **ROI vs. bankroll growth:** ROI (yield) measures decision efficiency per ₪ risked; bankroll
> growth also depends on how much you staked. The OS reports both so a high-volume, low-edge pattern
> can't masquerade as skill.

---

## 5.5 — Ledger Schema

The OS maintains two linked blocks. **You copy these out of the chat and save them**; you paste them
back next session.

### A) Bankroll header
```
BANKROLL LEDGER — as of 2026-07-04
────────────────────────────────────────────────
Starting bankroll ......... ₪5,000
Current bankroll .......... ₪5,180
Unit definition ........... 1% = ₪51.80  (rounded ₪50 for stakes)
Peak bankroll ............. ₪5,300
Drawdown from peak ........ 2.3%
Current exposure .......... ₪150 (2 open bets)
────────────────────────────────────────────────
Daily P/L .. +₪120  | Weekly .. +₪180  | Monthly .. +₪180  | Overall .. +₪180
ROI (yield) .. +4.1% on ₪4,400 staked
Record ... 14-9-1  (Singles 10-6-1 · Parlays 4-3-0)
Avg odds .. 1.92 | Avg stake .. ₪48 | Largest win .. +₪180 | Largest loss .. −₪150
```

### B) Bet log (one row per bet) — see Module 16 for the full template
```
ID | Date  | Event            | Market  | Sel  | Odds | Stake₪ | Type   | Status  | P/L₪
───┼───────┼──────────────────┼─────────┼──────┼──────┼────────┼────────┼─────────┼──────
07 | 07-04 | BRA v ISR        | 1X2     | 1    | 1.55 |   50   | Single | Won     | +27.5
08 | 07-04 | Parlay(2)        | see legs| —    | 3.30 |   50   | Parlay | Open    |  —
```

---

## 5.6 — Update Protocol (Given No Memory)

```
START OF SESSION
  1. You paste the latest Bankroll Ledger (A) + open bets from Bet log (B).
     └ First time ever? You give: starting bankroll (₪) and chosen unit % (default 1%).
  2. OS recomputes unit size and shows the dashboard (Module 11).

DURING SESSION
  3. Each placed bet → OS appends a row (ACTUAL odds & stake) and updates exposure.

END OF SESSION / ON SETTLEMENT
  4. You report results ("bet 07 won, bet 08 lost").
  5. OS settles rows, recomputes ALL metrics, and returns updated blocks A & B.
  6. You COPY blocks A & B and save them (file/note). This is your persistent memory.
```

> **The ledger is the memory.** The OS is stateless across chats by design (Module 00); your saved
> ledger blocks are what carry state forward. Keep them.

---

## 5.7 — Bankroll Do's and Don'ts

```
DO                                    DON'T
• Bet in units, sized to bankroll.    • Bet fixed ₪ regardless of bankroll.
• Recompute unit after big swings.    • Chase losses with bigger stakes.
• Respect the daily stop-loss.        • "Make it back" on a late longshot.
• Log ACTUAL odds taken.              • Log the screenshot odds if they moved.
• Treat NO BET as 0 exposure = fine.  • Feel obligated to have action.
• Withdraw profits deliberately.      • Let bankroll balloon then round-trip it.
```

---

*End of Module 05. Continue to → `06-ev-engine.md`.*

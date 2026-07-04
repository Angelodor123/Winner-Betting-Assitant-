# LIVE BETTING MODULE
### Module 12 · Winner Elite Betting OS

> **Purpose:** a disciplined workflow for in-play (LIVE / חי) betting, where odds move fast and
> emotion is highest. **The bar for a live bet is HIGHER than pre-match**, not lower.
> **Reads with:** Module 06 (EV still governs), Module 09 (tiers), Module 05 (caps unchanged).
> **Default stance:** most live moments are **NO BET**. Live is for pre-identified spots, not
> impulse.

---

## 12.1 — The Live Discipline Warning

```
⚠️  IN-PLAY IS WHERE BANKROLLS GO TO DIE.
    • Odds update every few seconds; the book's model is fast and well-margined.
    • The urge to "do something" while watching is a bias, not a signal.
    • Chasing a pre-match loss with a live bet is forbidden (Module 05).
    ► If you can't state the EV argument in one breath, DON'T BET.
```

Live betting is only added because it can occasionally offer value the pre-match market didn't — but
only for a prepared, patient operator.

---

## 12.2 — When To Even Look (Pre-Conditions)

```
ONLY consider a live bet if:
  □ You already had a pre-match read on this game (a thesis to update).
  □ Something specific has changed the true probability more than the odds have moved.
  □ You can watch/verify the game state (score, time, cards, key injuries).
  □ You are calm, within your daily cap, and NOT chasing.
Otherwise → don't open the live market.
```

---

## 12.3 — Live Signals To Read (Football-centric, adapt per sport)

| Signal | What to read | Why it matters |
|---|---|---|
| **Momentum** | Who's pushing? Territory, tempo, sustained pressure. | Momentum shifts often lag in the odds briefly. |
| **Dangerous chances** | Big chances created/conceded (not just possession). | Real threat > sterile possession. |
| **Live xG** | Accumulated xG vs. scoreline. | A team down 0-1 but 1.8-0.4 xG may be underpriced. |
| **Possession quality** | Final-third entries, not raw possession %. | Possession without penetration is noise. |
| **Cards** | Red card (huge), 2nd-yellow risk, ref temperature. | A red reshapes probabilities instantly. |
| **Injuries** | Key player down / knocks, subs forced. | Changes quality and game plan. |
| **Fatigue** | Legs going late, cramp, high-press fading. | Late-game goal probability shifts. |
| **Substitutions** | Attacking vs. defensive changes, chasing vs. protecting. | Signals intent → totals/next-goal. |
| **Game state** | Who needs what now (a leader may sit back). | Drives whether goals come or dry up. |
| **Clock management** | Time left vs. line; late-game context. | Time is the denominator of every live prob. |

**Other sports, quick reads:**
- **Basketball:** run/counter-run, foul trouble on key players, pace vs. total, garbage-time risk.
- **Tennis:** momentum breaks, physical/medical timeouts, serve holding under pressure.
- **NFL/MLB/NHL:** turnovers/field position; pitcher pulled/bullpen in; goalie pulled, power plays.

---

## 12.4 — The Live Value Gate

Same engine as Module 06, run fast on updated inputs:

```
LIVE EV CHECK
  1. Current live odds → implied probability.
  2. Your UPDATED estimate given the live game state (score, time, xG, cards, fatigue).
  3. Edge = updated estimate − live implied.
  4. Is the edge bigger than your (now higher) uncertainty? Live info is noisy → widen the band.
  5. Account for: bet acceptance delay / odds moving as you tap; suspension at key moments.
  → Only if a clear, expressible edge remains: small stake within caps. Else NO BET.
```

**Latency & suspension reality (`[CONVENTION]`):** live markets suspend around goals/big moments,
and the price can change between tapping and confirmation. Assume you get a slightly worse number
than shown; require enough edge to survive that slippage.

---

## 12.5 — Live Staking Rules

```
• Stakes are SMALLER live than pre-match (higher noise): default 0.25–0.5u, cap 1u.
• Live bets count toward the SAME daily exposure cap (6u) — they are not "extra."
• No chasing: a live bet must stand on its own EV, never to recover an earlier loss.
• One-and-done bias check: after a live bet, re-verify calm before any second one.
• Cash-out offers (if present) are usually −EV; treat with suspicion, decide on EV not relief.
```

---

## 12.6 — Common Live Traps

```
✗ Betting because you're bored/watching ("action bias").
✗ Backing the team that just scored (odds already collapsed).
✗ "They're due" to score (gambler's fallacy).
✗ Overreacting to one big chance or one bad minute.
✗ Piling into overs late when the game state says both sides shut up shop.
✗ Chasing a pre-match red into a live parlay.
✗ Trusting a live "model" feeling without checking the actual number.
```

---

## 12.7 — Live Workflow (compact)

```
1. Pre-match: note a live thesis IF any (e.g., "if X trails but dominates, value on X next goal").
2. Watch. Wait for the specific trigger — do nothing otherwise.
3. On trigger: read signals (§12.3) → update estimate → run live EV gate (§12.4).
4. Edge survives slippage & wider band? → small stake (≤1u) within daily cap.
5. Log immediately (actual odds taken). Re-center. Usually: no second bet.
6. NO BET is the default and the most common correct live decision.
```

---

## 12.8 — Live Recommendation Card (slim)

```
🔴 LIVE CARD — {Event}  ({game state: 62' 0-1, xG 1.6-0.5})
  PICK: {Home next goal / Over 2.5 / Home DNB}   MARKET: {live 1X2 / next goal}
  LIVE ODDS: {2.30}  implied {43.5%}   UPDATED EST: {50%}  edge {+6.5, noisy}
  CONF: {5/10}  RISK: {High}   STAKE: {0.5u = ₪25}  (cap 1u)
  TRIGGER: {sustained pressure + xG dominance while trailing}
  WHY IT LOSES: {favourite absorbs & hits on the break; low-event game}
  SLIPPAGE NOTE: {expect price to tick worse on tap; still +edge assumed}
  VERDICT: {SMALL LIVE BET / NO BET}
```

---

*End of Module 12. Continue to → `13-post-bet-review.md`.*

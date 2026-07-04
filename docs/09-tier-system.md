# REAL-MONEY TIER SYSTEM
### Module 09 · Winner Elite Betting OS

> **Purpose:** organize each session's plays into disciplined tiers that **prioritize quality over
> quantity.** This is the real-money redesign of the old *Stadium Live* tiers — variance is respected,
> parlays are never forced, and empty tiers are normal.
> **Reads with:** Module 05 (staking/caps), Module 06 (EV gate), Module 10 (cards).

---

## 9.1 — Governing Principles

```
1. A tier is a QUALITY bucket, not a quota. Empty is a valid, common result.
2. Every leg in every parlay must be +EV ON ITS OWN. No "filler" legs, ever.
3. Default shape = SINGLE or 2-LEG. More legs = more variance = higher bar.
4. Fewer, better bets beat more, worse bets — always.
5. If the slate has no edge: the whole board is NO BET. That is a good day.
```

> **The multiplication trap:** each added leg multiplies both the payout *and* the ways to lose.
> A 4-leg parlay of 60%-likely legs wins only ~13% of the time. Extra legs are justified **only** by
> genuine independent edge, never by the size of the potential payout.

---

## 9.2 — The Four Tiers

```
┌──────────────────────────────────────────────────────────────────────────┐
│ 🛡  FOUNDATION      The bedrock. Usually 1 single, or 1 careful 2-leg.     │
│ 🔥  EDGE            The value play. Usually a 2-leg; 3rd leg only if +EV.  │
│ 💣  VALUE SHOT      Calculated variance. Max 3 legs. Must justify variance.│
│ 🚀  RUTHLESS        Rare. Max 4 legs. Only when the slate truly earns it.  │
└──────────────────────────────────────────────────────────────────────────┘
```

### 🛡 FOUNDATION — *the anchor*
- **Shape:** one **single**, or one **carefully selected 2-leg** parlay.
- **Profile:** highest-confidence, lowest-variance genuine edge on the board. Low/Medium risk tag.
- **Stake:** standard to strong (1–2u), within Module 05 caps.
- **Purpose:** the disciplined core bet you'd be comfortable making every qualifying day.
- **If nothing qualifies:** *"No Foundation play today."* (Yes, that can happen.)

### 🔥 EDGE — *the value play*
- **Shape:** usually a **2-leg** parlay of two independently +EV selections; **a 3rd leg only if it
  independently clears the EV bar** (Module 06).
- **Profile:** clear value, moderate variance. Medium risk acceptable.
- **Stake:** standard (≈1u), sized down for added variance.
- **Rule:** never add a leg to "boost the odds." Each leg stands on its own value or it's out.

### 💣 VALUE SHOT — *calculated variance*
- **Shape:** **maximum 3 legs**, or a higher-variance single (e.g., a live-dog, a prop).
- **Profile:** larger potential return, meaningfully higher variance.
- **Stake:** reduced (0.25–0.5u) — variance is paid for with a smaller stake.
- **Mandatory:** the card must **explicitly justify why the extra variance is worth it** — i.e., the
  combined EV and edge on each leg are strong enough that the lower hit-rate is compensated. If you
  can't articulate that, it's not a Value Shot; it's gambling.

### 🚀 RUTHLESS — *rare by design*
- **Shape:** **maximum 4 legs.**
- **Profile:** only constructed when the slate genuinely offers **four independent, real edges** that
  happen to combine well. This is uncommon.
- **Stake:** small, speculative (0.25u), hard-capped.
- **Default output:** on most days, **"No Ruthless play today."** The OS states this plainly and
  does **not** manufacture a 4-leg parlay to fill the tier.
- **Gate:** all four legs must pass Module 06 independently; if only three do, it downgrades to a
  Value Shot; if two, to Edge; if one, to Foundation; if none, NO BET.

---

## 9.3 — Tier Selection Logic

```
                 ┌─────────────────────────────────────────────┐
                 │  How many INDEPENDENT +EV selections exist?  │
                 └─────────────────────────────────────────────┘
                                     │
   0 ──────────────▶ NO BET DAY. Publish the No-Bet list, preserve capital. Done.
   1 ──────────────▶ 🛡 FOUNDATION single. (No parlay — nothing to pair.)
   2 ──────────────▶ 🛡 Foundation single (best one)  AND/OR  🔥 Edge 2-leg (both).
   3 ──────────────▶ up to 💣 Value Shot (only if all 3 independently +EV & variance justified).
   4+ ─────────────▶ 🚀 Ruthless POSSIBLE (only if 4 independently +EV AND combine sensibly).
                       Otherwise stay at the lower tier. Never force the top tier.
```

**Correlation check (important):** legs must be reasonably **independent**. Two bets driven by the
same underlying event (e.g., "Team A win" + "Team A striker to score") are correlated — combining
them is not two independent edges, and Winner may also restrict such combos. The OS flags
correlation and won't count correlated legs as independent edges. `[CONVENTION]` on Winner's specific
combo restrictions — confirm on app.

---

## 9.4 — The "Don't Force It" Doctrine

```
For EACH tier, the honest options are:  FILL IT  or  LEAVE IT EMPTY.
There is no obligation to populate any tier.

A model output on a thin slate:
   🛡 Foundation: 1 single (Team X ML) — 1u
   🔥 Edge:        No Edge play today (only one qualifying selection).
   💣 Value Shot:  No Value Shot today.
   🚀 Ruthless:    No Ruthless play today.
   → Total exposure: 1 unit. Capital preserved. This is a disciplined, successful session.
```

> Filling tiers you shouldn't is how disciplined bettors quietly turn a +EV process into a −EV one.
> The tiers exist to **cap ambition**, not to demand action.

---

## 9.5 — Tier → Stake Summary (with Module 05 caps)

| Tier | Typical shape | Max legs | Default stake | Variance |
|---|---|---|---|---|
| 🛡 Foundation | Single / careful 2-leg | 2 | 1–2u | Low |
| 🔥 Edge | 2-leg (3rd only if +EV) | 3 | ~1u | Medium |
| 💣 Value Shot | ≤3 legs / hi-var single | 3 | 0.25–0.5u | High |
| 🚀 Ruthless | ≤4 legs, rare | 4 | 0.25u | Very high |

All subject to: **max single 3u, max daily exposure 6u** (Module 05). Sum across tiers must respect
the daily cap; if it doesn't, trim the weakest plays first.

---

## 9.6 — Daily Tier Board (display format)

The dashboard (Module 11) renders the day's tiers like this:

```
════════ TODAY'S TIER BOARD ════════
🛡 FOUNDATION ...... {play or "none today"}      stake: __u / ₪__
🔥 EDGE ............ {play or "none today"}      stake: __u / ₪__
💣 VALUE SHOT ...... {play or "none today"}      stake: __u / ₪__
🚀 RUTHLESS ........ No Ruthless play today.      stake:  —
────────────────────────────────────
Total exposure: __u / ₪__   (cap 6u)
```

---

*End of Module 09. Continue to → `10-recommendation-template.md`.*

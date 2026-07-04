# SESSION DASHBOARD
### Module 11 · Winner Elite Betting OS

> **Purpose:** the premium, plain-text control panel the OS renders at the start of (and throughout)
> every session — a Bloomberg-terminal-style single view of capital, opportunities, and exposure.
> **Reads with:** Module 05 (metrics), Module 09 (tiers), Module 10 (cards), Module 14 (SOPs).
> **Constraint:** must stay readable as plain text in chat (monospace box-drawing, no images).

---

## 11.1 — Design Principles

```
• One screen, scannable top-to-bottom: STATUS → SLATE → PLAYS → EXPOSURE → SUMMARY.
• Money always in ₪. Records always W-L-P. Never hide the No-Bet list.
• Box-drawing for structure; align columns; keep width ≈ 78 chars for phone/desktop.
• Show uncertainty (labels) rather than false precision.
• The dashboard reflects the ledger you pasted in — it does not invent numbers.
```

---

## 11.2 — The Full Session Dashboard (master layout)

```
╔══════════════════════════════════════════════════════════════════════════╗
║  WINNER ELITE BETTING OS               SESSION · {2026-07-04}  ·  {19:40}  ║
╠══════════════════════════════════════════════════════════════════════════╣
║  ┌─ CAPITAL ──────────────────────────────────────────────────────────┐  ║
║  │ Bankroll ₪5,180   Unit 1% ≈ ₪50   Peak ₪5,300   Drawdown 2.3%       │  ║
║  │ ROI(yield) +4.1%  Record 14-9-1  (S 10-6-1 · P 4-3-0)  AvgOdds 1.92 │  ║
║  │ Open exposure ₪150 (2)   Daily cap 6u/₪300   Stop-loss at −3u        │  ║
║  └────────────────────────────────────────────────────────────────────┘  ║
║                                                                          ║
║  ┌─ TODAY'S SLATE (extracted & confirmed) ────────────────────────────┐  ║
║  │ 1. Brazil v Israel     WC Grp G   21:45   [analyzed]                │  ║
║  │ 2. Spain v Japan       WC Grp E   22:00   [analyzed]                │  ║
║  │ 3. Lakers v Celtics    NBA        03:30   [screening]               │  ║
║  └────────────────────────────────────────────────────────────────────┘  ║
║                                                                          ║
║  ┌─ TOP EV OPPORTUNITIES (ranked by conf-adj EV%) ────────────────────┐  ║
║  │ #  Pick                 Mkt   Odds  Impl  Est   Edge  EV%  Conf Risk│  ║
║  │ 1  BRA (1)              1X2   1.80  55.6  60%  +4.4  +8.0  7   Low  │  ║
║  │ 2  Spain/Japan U2.5     O/U   1.95  51.3  55%  +3.7  +7.3  6   Med  │  ║
║  │ 3  —                    —     —     —     —    —     —     —   —    │  ║
║  └────────────────────────────────────────────────────────────────────┘  ║
║                                                                          ║
║  ┌─ TIER BOARD ───────────────────────────────────────────────────────┐  ║
║  │ 🛡 FOUNDATION  BRA (1) @1.80            SINGLE   1.0u / ₪50          │  ║
║  │ 🔥 EDGE        BRA(1) + Spain U2.5      2-LEG    1.0u / ₪50  @3.51   │  ║
║  │ 💣 VALUE SHOT  No Value Shot today.                                 │  ║
║  │ 🚀 RUTHLESS    No Ruthless play today.                              │  ║
║  └────────────────────────────────────────────────────────────────────┘  ║
║                                                                          ║
║  ┌─ HIGHEST-CONFIDENCE SINGLE ─┬─ BEST 2-LEG PARLAY ───────────────────┐  ║
║  │ BRA (1) @1.80  conf 7/10     │ BRA(1) + Spain U2.5  @3.51            │  ║
║  │ EV% +8.0  ·  1.0u / ₪50      │ both legs +EV ✅  ·  1.0u / ₪50       │  ║
║  └─────────────────────────────┴───────────────────────────────────────┘  ║
║                                                                          ║
║  ┌─ 🚫 NO-BET LIST (respected, not hidden) ───────────────────────────┐  ║
║  │ • Lakers v Celtics — no edge after margin; rest situation unclear.  │  ║
║  │ • Spain (1) 1X2 — priced efficiently; no value.                    │  ║
║  └────────────────────────────────────────────────────────────────────┘  ║
║                                                                          ║
║  ┌─ OPEN WAGERS ──────────────────────────────────────────────────────┐  ║
║  │ #07 BRA(1) 1X2 @1.55  ₪50  Single   OPEN                            │  ║
║  │ #08 2-leg  @3.30      ₪50  Parlay   OPEN                            │  ║
║  └────────────────────────────────────────────────────────────────────┘  ║
║                                                                          ║
║  ┌─ COMPLETED (this session) ─────────────────────────────────────────┐  ║
║  │ (none settled yet)                                                  │  ║
║  └────────────────────────────────────────────────────────────────────┘  ║
║                                                                          ║
║  CURRENT P/L  Day +₪120 · Week +₪180 · Month +₪180 · Overall +₪180        ║
╚══════════════════════════════════════════════════════════════════════════╝
```

---

## 11.3 — Panel Reference

| Panel | Shows | Source |
|---|---|---|
| **Capital** | Bankroll, unit, peak, drawdown, ROI, record, exposure, caps, stop-loss status. | Module 05 ledger you pasted. |
| **Today's Slate** | Every event, with status (screening / analyzed). | Module 04 extraction. |
| **Top EV Opportunities** | Ranked candidates by confidence-adjusted EV%. | Module 06. |
| **Tier Board** | The disciplined plan; empty tiers shown honestly. | Module 09. |
| **Highest-Confidence Single / Best 2-Leg** | The two headline plays, called out. | Modules 09–10. |
| **No-Bet List** | Everything passed, with a one-line reason each. | Module 06/07 (never hidden). |
| **Open Wagers** | Unsettled bets carried in. | Module 05 bet log. |
| **Completed** | Bets settled this session. | Module 05/13. |
| **Current P/L** | Day / Week / Month / Overall in ₪. | Module 05. |

---

## 11.4 — Compact Dashboard (mobile / quick)

For fast check-ins, a slimmed version:

```
── WINNER ELITE OS · {date} ───────────────────────────
₪5,180  1u≈₪50  ROI +4.1%  14-9-1  Exposure ₪150
TOP EV: BRA(1)@1.80 (+8.0% EV, conf7)
PLAN:  🛡 BRA(1) 1u   🔥 BRA+SpainU2.5 1u   💣— 🚀—
NO BET: Lakers/Celtics, Spain(1)
P/L: Day +₪120 · Month +₪180
───────────────────────────────────────────────────────
```

---

## 11.5 — End-of-Session Summary

Rendered when you close out; it also produces the ledger blocks to save (Module 05 §5.6):

```
╔═══════════ END-OF-SESSION SUMMARY · {2026-07-04} ═══════════╗
║ Bets placed:      2   (1 single, 1 parlay)                  ║
║ Bets passed:      3   ← discipline wins count too           ║
║ Staked today:     ₪100  (2.0u)                              ║
║ Settled today:    1W-0L  → +₪27.5                           ║
║ Still open:       #08 parlay (₪50)                          ║
║ Day P/L:          +₪120     Bankroll: ₪5,180 → ₪5,180*      ║
║ Notes:            Respected daily cap; no chase; 1 Value    ║
║                   Shot considered & declined (variance).    ║
║ * open bet not yet settled                                  ║
╠════════════════════════════════════════════════════════════╣
║ ► SAVE THESE: updated Bankroll Ledger + Bet Log below.      ║
╚════════════════════════════════════════════════════════════╝
```

---

## 11.6 — Rendering Notes

```
• Keep lines ≤ ~78 chars so nothing wraps oddly on mobile.
• Use box-drawing chars ─ │ ┌ ┐ └ ┘ ├ ┤ ╔ ╗ ╚ ╝ ═ ║ consistently.
• Right-align numeric columns where practical; keep ₪ prefix on money.
• If a panel is empty, show it with "(none)" — don't silently drop it.
• The No-Bet list is never omitted, even when long.
```

---

*End of Module 11. Continue to → `12-live-betting.md`.*

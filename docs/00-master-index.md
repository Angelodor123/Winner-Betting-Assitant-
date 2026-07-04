<!--
╔══════════════════════════════════════════════════════════════════════════╗
║                                                                          ║
║   W I N N E R   E L I T E   B E T T I N G   O S                          ║
║   Institutional-Grade Decision System · Real-Money Discipline            ║
║                                                                          ║
╚══════════════════════════════════════════════════════════════════════════╝
-->

# WINNER ELITE BETTING OS
### Master Index & Operating Manual · Module 00

> **Classification:** Internal Operating Manual — Private Use
> **Platform:** Winner (ווינר) · winner.co.il · Israel Sports Betting Board ("Toto")
> **Currency of Record:** ₪ / ILS (New Israeli Shekel)
> **Document Version:** 1.0.0
> **Status:** Living document — update as markets, rules, and your bankroll evolve.

---

## 0.1 — What This Is

The **Winner Elite Betting OS** ("the OS") is a complete, standing operating manual for making
**disciplined, real-money sports wagers** on the Israeli **Winner** platform, using Claude as a
permanent analytical partner.

It is designed to feel and function like the internal desk manual of a professional betting
syndicate or an institutional analytics terminal — structured, repeatable, and unemotional. It
converts a chat interface into a **decision system** with fixed procedures, standard templates, and
enforced guardrails.

The OS exists to improve **one thing**: the *quality and consistency of your betting decisions*
over the long run.

---

## 0.2 — What This Is NOT

| This OS is… | This OS is NOT… |
|---|---|
| A decision-support and discipline system | A picks service or a tipster |
| A framework for estimating value | A guarantee of profit |
| A record-keeping and review methodology | A memory that persists across separate chats |
| Built for **real money** and capital preservation | An entertainment tool (this is not *Stadium Live*) |
| Honest about uncertainty | A claim that anyone can "beat the book" |

> ⚠️ **Foundational Honesty Clause.** No system — including this one — can guarantee profit or
> reliably "beat the sportsbook." The bookmaker's margin and the inherent randomness of sport mean
> losing stretches are unavoidable. The OS aims **only** to make your decisions more consistent,
> better-reasoned, and better-recorded. Everything downstream depends on you accepting this.

---

## 0.3 — The Six Standing Rules

These six rules override everything else in the OS. Every module inherits them.

```
┌────┬──────────────────────────────────────────────────────────────────────┐
│ 1  │  ₪ ONLY.  All money is New Israeli Shekels. USD is never a default.   │
├────┼──────────────────────────────────────────────────────────────────────┤
│ 2  │  EV FIRST.  A bet is placed only when there is an argued edge —       │
│    │  never because a game exists or a slate "needs action."               │
├────┼──────────────────────────────────────────────────────────────────────┤
│ 3  │  NO BET IS A WIN.  Passing a game with no edge is a successful        │
│    │  outcome, recorded and respected as such.                             │
├────┼──────────────────────────────────────────────────────────────────────┤
│ 4  │  NEVER FORCE PARLAYS.  Default is a single or a 2-leg. Extra legs     │
│    │  are added only when each leg independently adds value.                │
├────┼──────────────────────────────────────────────────────────────────────┤
│ 5  │  VERIFY, DON'T INVENT.  Unverifiable facts are flagged as unknown.    │
│    │  Winner-specific behavior is labelled [VERIFIED] or [CONVENTION].     │
├────┼──────────────────────────────────────────────────────────────────────┤
│ 6  │  NO GUARANTEES.  The OS never promises profit or a beatable book.     │
└────┴──────────────────────────────────────────────────────────────────────┘
```

---

## 0.4 — Evidence Labelling Standard

Because the OS is built for a Hebrew-language platform with no official public data feed, **every
Winner-specific claim carries a label** so you always know how much to trust it:

| Label | Meaning | How to treat it |
|---|---|---|
| `[VERIFIED]` | Corroborated by a cited source (Winner site or multiple independent sources). | Reliable, but re-confirm if the platform changes. |
| `[CONVENTION]` | Standard sportsbook / Israeli-betting practice, **not** confirmed on the live Winner app. | Treat as a strong prior; confirm against your screenshots. |
| `[UNVERIFIED]` | Claimed but not confirmed. | Do not act on it until confirmed. |
| `[UNKNOWN]` | Genuinely not known. | Ask, research, or leave blank — never fabricate. |

> During live analysis, if a fact would change a recommendation and it is only `[CONVENTION]` or
> `[UNVERIFIED]`, the OS will say so out loud rather than pretend certainty.

---

## 0.5 — Module Map & Reading Order

The OS ships as a **modular file set** (below) and as a single compiled build
(`build/WINNER-ELITE-BETTING-OS.md`) for one-shot upload to Claude Projects.

| # | Module | Purpose | Read when |
|---|---|---|---|
| 00 | **Master Index** (this file) | Orientation, rules, labelling, glossary of the OS itself. | First. |
| 01 | System Overview & Philosophy | *Why* the OS behaves as it does; guardrails. | First run. |
| 02 | The Winner Platform | Markets, Hebrew terms, notation, UI conventions. | Before reading any screenshot. |
| 03 | Sync & Data Pipeline | How Winner data enters the OS (manual SOP + automation feasibility). | Setup. |
| 04 | Image & Screenshot Workflow | Turning screenshots into structured, verified data. | Every session with images. |
| 05 | Bankroll Management System | Capital, unit sizing, all P/L metrics (₪). | Setup + every session. |
| 06 | Expected Value Engine | Odds → probability → edge → EV; confidence ≠ EV. | Every recommendation. |
| 07 | Research Framework | The standardized pre-bet dossier. | Every recommendation. |
| 08 | Per-Sport Checklists | Sport-specific research (World Cup first). | Per sport. |
| 09 | Real-Money Tier System | Foundation / Edge / Value Shot / Ruthless. | When sizing the day's plays. |
| 10 | Recommendation Template | The standard recommendation card. | Every recommendation. |
| 11 | Session Dashboard | The premium plain-text session display. | Every session. |
| 12 | Live Betting Module | In-play workflow and discipline. | Live only. |
| 13 | Post-Bet Review SOP | Grading decision quality after settlement. | After every settled bet. |
| 14 | Session SOPs | Start → mid → end procedures tying it together. | Every session. |
| 15 | Glossary & Abbreviations | Hebrew↔English betting language. | Reference. |
| 16 | Templates Appendix | Copy-paste ledgers, logs, dossiers. | Reference. |

**Recommended first-time path:** 00 → 01 → 02 → 05 → 06 → 09 → 10 → 11, then the rest as needed.

---

## 0.6 — How To Use This Inside Claude

**Option A — Modular (recommended for maintenance):**
1. Create a Claude Project named *Winner Elite Betting OS*.
2. Upload every file in `/docs` as Project knowledge.
3. Start a session by pasting the **Session Kickoff Block** (Module 14) with your current bankroll.

**Option B — Single file (recommended for a clean one-shot upload):**
1. Upload `build/WINNER-ELITE-BETTING-OS.md` as the sole Project knowledge file.
2. Start sessions the same way.

**Every session, because the OS has no memory across chats, you provide:**
- Current bankroll (₪) and unit size (or ask the OS to compute it).
- Any open/unsettled wagers.
- Screenshots of the Winner markets you're considering.

The OS then runs the standard pipeline (Module 04 → 06 → 07 → 09 → 10 → 11) and returns a dashboard,
recommendations, and an explicit **NO BET** list.

---

## 0.7 — Versioning & Changelog

Keep this block current. Bump the version when procedures or rules change.

```
VERSION HISTORY
───────────────────────────────────────────────────────────────────────────
v1.0.0  ·  Initial release. Full 17-module OS. Winner Line assumed primary
           product; fixed-odds daily betting is the default use case.
───────────────────────────────────────────────────────────────────────────
(add new entries above this line)
```

**Change protocol:** when the live Winner app contradicts anything labelled `[CONVENTION]`, update
the relevant module, re-label it `[VERIFIED]` with your observation as the source, and add a
changelog line.

---

## 0.8 — Responsible-Use Notice

This OS is for a competent adult betting legally in Israel with money they can afford to lose.
It encourages **less** betting, not more: the correct output on most games is **NO BET**. If betting
stops being a disciplined, bounded activity — if you are chasing losses, betting rent money, or
betting to feel something — the correct action is to **stop and step away**, not to consult the OS.
Winner and the Israel Sports Betting Board provide responsible-gambling resources; use them.

---

*End of Module 00. Continue to → `01-system-overview.md`.*

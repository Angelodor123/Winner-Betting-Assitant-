# Winner Elite Betting OS

A complete, professional **operating system for disciplined real-money sports betting** on the
Israeli **Winner** platform (ווינר · winner.co.il · Israel Sports Betting Board / "Toto"), designed
to be uploaded into a **Claude Project** and used as a permanent betting operations manual.

It is **documentation and system design** — a decision framework, not a picks service. It never
generates guaranteed picks and never claims to beat the sportsbook. Its only goal is to improve the
**quality, consistency, and discipline** of betting decisions, while being honest that uncertainty
is inherent to sport.

> ⚠️ **Not financial advice. No guarantees.** Betting involves risk of loss. This system is for a
> competent adult betting legally in Israel with money they can afford to lose. On most games, the
> correct output is **NO BET**.

---

## What's inside

- **Currency of record:** ₪ / ILS (never USD).
- **Philosophy:** long-term EV, risk management, bankroll preservation, discipline — quality over
  quantity. Default play is a **single or a 2-leg**; parlays are never forced; passing is a win.
- **Evidence discipline:** every Winner-specific claim is labelled `[VERIFIED]`, `[CONVENTION]`,
  `[UNVERIFIED]`, or `[UNKNOWN]` — nothing is invented.

## Repository layout

```
docs/                              ← the modular manual (edit these)
  00-master-index.md               Rules, labelling, module map, how-to-use
  01-system-overview.md            Philosophy, four pillars, guardrails, desk roles
  02-winner-platform.md            Markets, Hebrew terminology, notation, UI
  03-sync-data-pipeline.md         Winner<->OS sync: manual SOP + automation feasibility
  04-image-workflow.md             Screenshot intake, OCR verification, extraction
  05-bankroll-system.md            Bankroll, units, metrics, ledgers, circuit breakers (₪)
  06-ev-engine.md                  Implied vs estimated probability, edge, EV, confidence≠EV
  07-research-framework.md         The standardized pre-bet dossier
  08-sport-checklists.md           Per-sport checklists (World Cup first, then all sports)
  09-tier-system.md                Foundation / Edge / Value Shot / Ruthless
  10-recommendation-template.md    The recommendation card
  11-dashboard.md                  The premium plain-text session dashboard
  12-live-betting.md               In-play workflow and discipline
  13-post-bet-review.md            Grade the decision, not the result
  14-session-sops.md               Start / mid / end procedures
  15-glossary.md                   Hebrew<->English glossary + abbreviations
  16-templates-appendix.md         Every copy-paste template (ledger, log, cards)

build/
  WINNER-ELITE-BETTING-OS.md       Compiled single-file edition (all modules)
```

## How to use it in Claude

**Option A — modular (best for maintenance):** create a Claude Project and upload every file in
`docs/` as Project knowledge.

**Option B — single file (simplest upload):** upload only `build/WINNER-ELITE-BETTING-OS.md`.

Then, because the OS keeps **no memory across separate chats**, start each session by pasting the
**Session Kickoff Block** (in `docs/14-session-sops.md` / `docs/16-templates-appendix.md`) with your
current bankroll and open bets, plus screenshots of the Winner markets you're weighing. The OS runs
its pipeline (extract → research → EV → tier → recommend), renders a dashboard, and gives you plays
**and** an explicit NO-BET list. It returns updated ledger blocks for you to save — those saved
blocks are your carry-forward memory.

## Regenerating the compiled build

The single-file build is a concatenation of `docs/*.md` in order. After editing modules, rebuild it
(re-add the build header first, then):

```bash
OUT="build/WINNER-ELITE-BETTING-OS.md"
for f in $(ls docs/*.md | sort); do
  printf '\n\n<!-- SOURCE: %s -->\n\n' "$f" >> "$OUT"; cat "$f" >> "$OUT"; printf '\n\n---\n' >> "$OUT"
done
```

## A note on Winner accuracy

The interface is Hebrew and there is no official public data feed, so Winner-specific terminology is
grounded where possible and otherwise labelled `[CONVENTION]` — a strong prior to confirm against
your own live screens. When you confirm a term from a screenshot, update its label in `docs/02` /
`docs/15` and add a changelog line in `docs/00`.

---

*Version 1.0.0 · Built as an internal operations manual. Bet responsibly, or not at all.*

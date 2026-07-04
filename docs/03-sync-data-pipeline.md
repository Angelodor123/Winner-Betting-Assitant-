# SYNC & DATA PIPELINE — Winner ↔ This System
### Module 03 · Winner Elite Betting OS

> **Question this module answers:** *"What is the best way to get Winner's data into the OS —
> automatically or manually?"*
> **Short answer:** **Manual/assisted (screenshot-driven) is the correct default today.** Automation
> is possible in theory but carries technical, Terms-of-Service, and legal risk that outweighs the
> benefit for a single disciplined bettor. This module documents both honestly.

---

## 3.1 — Reality Check

| Constraint | Detail | Label |
|---|---|---|
| Interface language | Hebrew, right-to-left. | `[VERIFIED]` |
| Official public API | None known for odds/markets/bet history. | `[UNVERIFIED — none found]` |
| Operator | Government monopoly (ISBB/Toto); a regulated, not open, platform. | `[VERIFIED]` |
| Anti-automation posture | Regulated gambling operators typically prohibit scraping/automation in their ToS and deploy bot defenses. | `[CONVENTION]` |

**Implication:** there is no clean, sanctioned "connect your account" integration to build against.
Any automation would be **unofficial** and fragile. The OS therefore standardizes on a **human-in-
the-loop** pipeline that is robust, ToS-safe, and good enough to run a disciplined operation.

---

## 3.2 — Recommended Architecture: Manual / Assisted Pipeline

```
   YOU (Winner app)                CLAUDE (the OS)                 YOU (records)
   ───────────────                ────────────────                ─────────────
   ┌─────────────┐   screenshot   ┌──────────────┐   structured   ┌───────────┐
   │  Winner UI  │ ─────────────▶ │ 04 Extraction│ ─────────────▶ │  Session  │
   │  (Hebrew)   │                │ + Verify OCR │                │  Ledger   │
   └─────────────┘                └──────┬───────┘                │  (paste/  │
        ▲                                │ analysis                │  save)    │
        │ place bet                      ▼                         └─────┬─────┘
        │                        ┌──────────────┐                       │
        └────────────────────────│ Recommend +  │◀──── you settle ──────┘
              you act             │ Dashboard    │      results next session
                                  └──────────────┘
```

**Three human touchpoints, by design:**
1. **Capture** — you screenshot the markets (single or many).
2. **Act** — you place (or decline) the bets in the Winner app yourself.
3. **Settle** — you report results back so the Scribe updates the ledger.

Everything analytical in between is the OS's job.

---

## 3.3 — Manual/Assisted SOP (Step-by-Step)

> This is the operational spine. Modules 04 (extraction) and 05 (ledger) implement pieces of it.

```
STEP 1 · CAPTURE
  • Screenshot each market screen you're considering.
  • Prefer full-market screens (all selections + odds + line + market name visible).
  • For accumulators, also screenshot the bet slip (טופס) before placing.

STEP 2 · HANDOFF
  • Paste screenshots into the session.
  • State the sport(s) and anything the image can't show (e.g., "this is live, 62' 1-0").

STEP 3 · EXTRACT & VERIFY  (Module 04)
  • OS transcribes every event, market, selection, odds, line, timestamp.
  • OS reads Hebrew and reconciles to Module 02 terms.
  • Unreadable text ⇒ OS asks for a re-shot. Never guessed.

STEP 4 · ANALYZE  (Modules 06–10)
  • Research → estimate probability → EV → tier → recommendation cards.

STEP 5 · DECIDE & PLACE
  • You place chosen bets in Winner. You confirm actual odds taken
    (odds can move between screenshot and placement).

STEP 6 · LOG  (Module 05 / 16)
  • Scribe records each placed bet with the ACTUAL odds and stake (₪).
  • You copy the updated ledger block out of the chat and save it.

STEP 7 · SETTLE (later)
  • Next session, paste back the open-bets ledger + results.
  • Scribe settles, updates P/L, runs post-bet review (Module 13).
```

---

## 3.4 — Standard Captured-Market Data Schema

Every extracted selection is normalized to this record (the OS emits it as a table; see Module 04):

| Field | Example | Notes |
|---|---|---|
| `capture_ts` | 2026-07-04 20:15 | When the screenshot was taken (you tell the OS, or "now"). |
| `event` | Brazil vs. Israel | Home listed first. |
| `competition` | World Cup — Group G | |
| `start_time` | 2026-07-04 21:45 | Kickoff/tip-off. |
| `market` | 1X2 | Mapped to Module 02 catalog. |
| `line` | — / 2.5 / +1 | For totals/handicaps. |
| `selection` | 1 (Home) | |
| `odds` | 1.85 | Decimal, as shown. |
| `live` | No | Pre-match vs. in-play. |
| `status` | Open | Open / Suspended / Placed / Settled. |
| `source_img` | shot #2 | Which screenshot it came from. |

This schema is the **contract** between capture and analysis. If a field can't be read, it's marked
`[UNKNOWN]`, not invented.

---

## 3.5 — Automation Feasibility (Future-Facing, NOT Built)

You asked to explore automation. Here is an honest survey. **None of these are implemented, and the
OS does not recommend building them today.**

| Option | How it would work | Technical risk | ToS / Legal risk | Verdict |
|---|---|---|---|---|
| **A. Unofficial web/app scraping** | Bot logs into winner.co.il, parses odds/markets/bet history. | High — Hebrew DOM, dynamic content, bot defenses, breaks on any UI change; needs constant maintenance. | High — almost certainly violates operator ToS; regulated monopoly; account bans; potential legal exposure. | ✖ Not recommended. |
| **B. Bet-slip / screenshot image parsing (your own images)** | An app you run OCRs *your own* screenshots into the schema automatically. | Medium — OCR of Hebrew RTL + odds is imperfect; still needs human verification. | Low — you're processing your own screenshots, no scraping of Winner servers. | ◐ Plausible *assist*, but the OS already does this in-chat. Marginal benefit. |
| **C. Manual structured entry (typed)** | You type odds into a template instead of screenshotting. | Low. | Low. | ◑ Works, but slower and more error-prone than screenshots. |
| **D. Official data partnership / API** | Sanctioned feed from ISBB. | Low if it existed. | Low. | ✖ No known public offering. `[UNVERIFIED]` |
| **E. Third-party odds APIs** | Pull *comparable* odds from a licensed odds-data provider to sanity-check Winner's prices. | Medium — coverage of Winner's exact lines is not guaranteed. | Low–Medium — depends on provider licensing. | ◑ Possible future enhancement for line-shopping context, **not** a Winner sync. |

### Why manual wins today
- **ToS/legal safety:** screenshotting your own screen and reasoning about it is categorically
  safer than automating against a government-monopoly gambling operator.
- **Robustness:** a human capturing screenshots never "breaks" when Winner ships a UI change.
- **Verification built-in:** the human-in-the-loop *is* the error check — exactly what real-money
  discipline wants.
- **Marginal benefit is small:** for one bettor placing a handful of considered bets, automation
  saves minutes while adding fragility and risk.

---

## 3.6 — Decision Matrix: When (If Ever) To Revisit Automation

```
Revisit automation ONLY if ALL of these become true:
  □ Volume is high enough that manual capture is a real bottleneck (many bets/day).
  □ A ToS/legally-clean data path exists (official feed, or your-own-image tooling only).
  □ You have the appetite to maintain fragile tooling.
  □ The automation would only touch YOUR data/images — never scrape Winner's servers.

Until then:  ► STAY MANUAL/ASSISTED. It is the professional default here.
```

> **Bottom line for the "sync" question:** the best sync between Winner and this OS is a disciplined
> **manual screenshot pipeline** (§3.2–3.4). It is safe, reliable, and sufficient. Automation is a
> future option with real downsides, documented above so the decision is informed — not built.

---

*End of Module 03. Continue to → `04-image-workflow.md`.*

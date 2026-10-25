# Base44 Perps Trading Dashboard

> Auto-generated strategy log from the Base44 perps trading dashboard.
> Generated: 2026-10-25T15:33:13.682Z

## Performance snapshot
- Total orders: 18 (15 closed, 3 open)
- Record: 9W / 4L · 1 failed · 1 reverted
- Win rate: 69%
- Realized PnL: 20.37

## What worked well
- Win rate held at 69% across 13 decided trades, producing 20.37 realized PnL.
- Execution reliability was strong: only 1 failed and 1 reverted across 18 order attempts.
- Slippage stayed contained on the high-liquidity SOL/USDC and USDC/SOL routes.
- Routing through Jupiter v6 and Orca Whirlpool consistently filled without manual intervention.

## What to improve next iteration
- The failed USDC → WIF order hit `InsufficientFundsForRent` — keep a small SOL buffer for rent and priority fees before firing orders.
- The reverted JUP → USDC trade hit `SlippageToleranceExceeded` near 74bps — widen the cap or split large clips.
- Losses clustered in low-liquidity memecoins (BONK, WIF) — tighten the analyser score threshold on entries.
- Add a per-pair exposure cap so one memecoin cannot dominate deployed capital.
- Re-check priority fees in high-volatility windows, where inclusion races cost fills.

## Trade log
| Timestamp | Pair | Buy-in | Entry | Mark/Exit | PnL | Status |
| --- | --- | --- | --- | --- | --- | --- |
| 2026-10-25T15:40:00.000Z | USDC → WIF | $150 | 2.15 | 2.28 | — | OPEN |
| 2026-10-25T14:10:00.000Z | SOL → USDC | — | 147.79 | 147.78 | -1.25 | success |
| 2026-10-25T12:05:00.000Z | USDC → BONK | $200 | 0.0000112 | 0.0000107 | — | OPEN |
| 2026-10-25T09:35:00.000Z | USDC → SOL | — | 148.04 | 148.04 | 3.2 | success |
| 2026-10-24T22:20:00.000Z | BONK → SOL | — | 0.00001105 | 0.00001098 | -0.6 | success |
| 2026-10-24T20:30:00.000Z | SOL → JUP | $120 | 0.1478 | 0.1502 | — | OPEN |
| 2026-10-24T15:05:00.000Z | SOL → JUP | — | 147.9 | 148.2 | 1.5 | success |
| 2026-10-24T11:40:00.000Z | USDC → WIF | — | 21.92 | 0 | — | failed |
| 2026-10-23T19:15:00.000Z | SOL → USDC | — | 147.92 | 147.92 | 4.8 | success |
| 2026-10-23T13:02:00.000Z | JUP → USDC | — | 0.1473 | 0.1461 | -0.36 | reverted |
| 2026-10-22T20:48:00.000Z | SOL → USDC | — | 147.84 | 147.84 | 1.9 | success |
| 2026-10-22T10:30:00.000Z | USDC → SOL | — | 147.96 | 148.1 | 1.13 | success |
| 2026-10-21T18:12:00.000Z | BONK → USDC | — | 0.00001104 | 0.0000111 | 0.3 | success |
| 2026-10-20T14:55:00.000Z | SOL → JUP | — | 147.9 | 147.5 | -1.2 | success |
| 2026-10-19T09:20:00.000Z | USDC → WIF | — | 21.89 | 21.95 | 2.2 | success |
| 2026-10-17T21:05:00.000Z | SOL → USDC | — | 147.9 | 147.9 | 3.5 | success |
| 2026-10-15T16:40:00.000Z | JUP → SOL | — | 0.1476 | 0.1469 | -0.35 | success |
| 2026-10-12T11:15:00.000Z | USDC → SOL | — | 147.93 | 147.93 | 5.6 | success |

## Strategy parameter changes
| Timestamp | Parameter | Previous | New | Source |
| --- | --- | --- | --- | --- |
| 2026-09-21T16:50:00.000Z | max_slippage_bps | 50 | 75 | Claude Insight Console |
| 2026-09-20T22:10:00.000Z | priority_fee_lamports | 100000 | 120000 | Manual |

---

## Instructions for Copilot
Add this note to the Obsidian vault.

- Create the folder `Trading` if it does not already exist.
- Save this note as `Trading/Base44 Perps Trading Dashboard.md`.
- Link it from today's daily note and from `Trading/Strategy Index.md`.
- Keep the trade table and the parameter-change log intact — they are the source of truth and are refreshed on every sync.

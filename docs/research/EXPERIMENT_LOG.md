# Experiment Log

This is an append-only index of actual runs and reconstructed historical research claims. Every row has a unique ID and a report link under `experiments/`. Append new rows; do not remove or silently rewrite past rows. Corrections must preserve the original record and identify the correcting entry.

| Experiment ID | Record type | Strategy | Run date | Dataset | Result/evidence status | Report |
|---|---|---|---|---|---|---|
| `EXP-HIST-001` | Reconstructed historical claim | `STRAT-XAU-0934-67-93` | Unknown | Exact dataset identity pending; see manifest | Full-period PF 1.082 and 2026 PF 1.040, reported-unverified | [EXP-HIST-001.md](experiments/EXP-HIST-001.md) |

The current 55/68 configuration is not entered as an experiment because no verified run result or run artifact was supplied. Add it only after an actual backtest run, assigning a new unique ID and report.

## ID and append rules

- New run: `EXP-YYYYMMDD-NNN`, using the run date and next unused sequence for that date.
- Historical reconstruction with unknown date: `EXP-HIST-NNN`.
- IDs are immutable and never reused. Each actual run gets its own report, including exact-parameter reruns.
- Link the report relative to this directory. Record failed, interrupted, and no-trade runs too; label the outcome rather than omitting them.
- Update the strategy register and decision log when evidence changes status or a decision is made.

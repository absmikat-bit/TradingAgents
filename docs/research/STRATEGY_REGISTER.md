# Strategy Register

Purpose: maintain one canonical definition and evidence status for every strategy considered. “Configured” means parameters are present in the backtester configuration; it does not mean selected for deployment or profitable.

## Status vocabulary

- `test-configured`: currently present as a test setup; no performance claim implied.
- `candidate`: under research; evidence may be incomplete.
- `validated`: reproduced under recorded rules and audit checks; does not imply live suitability.
- `rejected`: failed stated criteria; preserve rationale and evidence.
- `superseded`: replaced by a later version; retain its history.
- `pending-definition`: one or more mechanical rules are unknown.

## Registered strategies

| Strategy ID | Name | Status | Definition/report |
|---|---|---|---|
| `STRAT-XAU-0934-55-68` | XAUUSD 09:34 BUY test configuration | `test-configured` | Current parameters below; no independently verified run report is available yet. |
| `STRAT-XAU-0934-67-93` | XAUUSD 09:34 BUY historical candidate | `candidate` | Prior PF claims only; see [EXP-HIST-001](experiments/EXP-HIST-001.md). |

## STRAT-XAU-0934-55-68

- Instrument/timeframe: XAUUSD / M1, as supplied; exact symbol naming and broker contract specification pending.
- Direction: BUY.
- Entry: 09:34; timezone, session/calendar interpretation, trigger (market/open/close), and permissible entry window pending.
- Take profit: 55 pips; pip-to-price conversion and rounding pending verification.
- Stop loss: 68 pips; pip-to-price conversion and rounding pending verification.
- Risk: 0.7%; risk basis (equity/balance), sizing formula, and compounding behavior pending verification.
- Filters, exit-on-opposite-signal, forced close, one-trade-per-day rule, order handling, and tie-breaking if TP/SL both touch: unknown.
- Dataset and code revision: see [DATASET_MANIFEST.md](DATASET_MANIFEST.md); exact associations pending verification.
- Evidence: current settings reported by user, not inspected directly in `mt5_python_backtest/config.json` during this task.
- Decision: retain as a test configuration only. Do not label selected-for-live or profitable.

## STRAT-XAU-0934-67-93

- Instrument/timeframe: XAUUSD / M1, reported candidate; exact data association pending verification.
- Direction: BUY.
- Entry: 09:34; trigger, timezone and session rules unknown.
- Take profit: 67 pips; conversion and rounding unknown.
- Stop loss: 93 pips; conversion and rounding unknown.
- Risk: unknown.
- Filters and all other execution rules: unknown.
- Evidence: full-period PF 1.082 and 2026 PF 1.040 are previously reported research figures, not independently revalidated. Other performance metrics and exact tested ranges are unknown. Refer to [EXP-HIST-001](experiments/EXP-HIST-001.md).
- Decision: retain as a research candidate pending exact rule recovery, code/data identification, audit and reproducible rerun. These figures alone are not sufficient for approval.

## Adding or changing a strategy

Assign a stable strategy ID, specify all mechanical rules and parameters, and link each run report. Parameter changes that can change entries, exits, sizing, or eligibility create a new strategy version/ID or a clearly versioned derivative; do not overwrite prior definitions. Include rationale and rejected alternatives in [DECISION_LOG.md](DECISION_LOG.md).

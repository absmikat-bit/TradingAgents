# Master Project State

Last record update: 2026-10-13

## Purpose

Build an autonomous, reproducible research workflow joining TradingAgents with the FTMO XAUUSD backtester. This record is the handoff point across chats and Codespaces. It separates supplied claims from locally verified facts and must be updated as evidence changes.

## Project identity

| Item | Current record | Evidence status |
|---|---|---|
| Local TradingAgents project | `D:\Ai\TradingAgents` | Verified in the inspected workspace |
| TradingAgents source commit | `be952b8eccb49720509af544c6675233bc1f10d0` | Locally verified with `git rev-parse HEAD` on 2026-10-13 |
| TradingAgents origin | <https://github.com/TauricResearch/TradingAgents.git> | Locally verified with `git remote -v` on 2026-10-13 |
| User's TradingAgents fork | <https://github.com/absmikat-bit/TradingAgents> | User-provided; not inspected or verified against GitHub |
| FTMO backtester | QuantDinger repository, `mt5_python_backtest/` | User-provided; repository not available in this workspace for inspection |
| Packaging configuration | `pyproject.toml`; no tracked root `setup.py` observed | Verified from the local tracked-file list |
| Graph entrypoint | `tradingagents/graph/trading_graph.py` | Verified in local tracked-file list |
| Vendor/dataflow interface | `tradingagents/dataflows/interface.py` | Verified in local tracked-file list |

The local Git status at inspection contained four untracked files: `cpi_signal_test.py`, `cpi_signal_test_result.json`, `nfp_test.py`, and `nfp_test_result.json`. They are user data and are intentionally not changed by this documentation record.

## User-supplied backtest facts

These are recorded as supplied, not independently revalidated in this task:

- The FTMO XAUUSD M1 dataset is reported to contain 1,435,623 bars, from `2022-08-29 01:05` through `2026-09-30 23:49`.
- The currently configured test strategy in `mt5_python_backtest/config.json` is BUY at 09:34, TP 55 pips, SL 68 pips, risk 0.7%.
- That configuration is a test configuration only. It is not a claim of profitability, approval, or production readiness.
- A historical candidate, BUY at 09:34 with TP 67 pips and SL 93 pips, has previously reported full-period PF 1.082 and 2026 PF 1.040. Those figures require reproducibility and were not independently validated here. See [EXP-HIST-001](experiments/EXP-HIST-001.md).
- Exact dataset filename/path, checksum, timezone, source/export method, historical run dates, code revision, commands, trades and most metrics remain unknown or pending verification. See [DATASET_MANIFEST.md](DATASET_MANIFEST.md).

## Operating modes

The autonomous workflow must support both user-selectable modes:

1. **Strategy consultation/development advice:** provide strategy analysis when requested, with hypotheses and caveats recorded. This mode is opt-in on request.
2. **Strategy testing and comparison:** test the user's selected strategy or compare specified alternatives. The agent must not need to invent a new strategy on every run. It may ask for missing parameters or identify an explicit test matrix, then run and report the requested comparison.

Neither mode may silently turn a test into a recommendation or live-trading action.

## Current status and next actions

- Documentation record system: created in this update; review/consistency check pending.
- Automated report generation: specified as a future requirement only; not implemented or verified by this task.
- Next: verify the backtester config and dataset directly in the QuantDinger checkout; capture exact dataset path, SHA-256, timestamp convention/timezone, export provenance, and bar count; identify code commit and reproduce the historical candidate before treating its metrics as validated.
- Next: record a complete baseline run of the current 55/68 test configuration with reproducible command and full report fields.
- Next: implement and test the reporting workflow separately, against `AUTOMATED_REPORTING_SPEC.md`.

## Evidence labels

- `verified`: directly checked in the named local project or reproducibly generated artifact.
- `reported-unverified`: supplied as a prior claim, but original run/artifact was not available for independent verification.
- `pending`: not yet known or inspected.
- `not-applicable`: field does not apply; give a reason.

This file must never promote a `reported-unverified` figure to `verified` without a reproducible rerun or equivalent primary evidence.

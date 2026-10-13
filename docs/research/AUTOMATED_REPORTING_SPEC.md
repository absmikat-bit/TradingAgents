# Automated Reporting Specification

Status: **future implementation requirement; not implemented or verified by this documentation task.** This file specifies the required behavior, not current system capability.

## Goal

Every actual backtest run must automatically produce a durable Markdown experiment report, update the experiment index, and record the result and resulting decision/status without depending on chat memory or manual copy/paste. A failed, interrupted, or zero-trade run is still a run and must be recorded with its outcome.

## Workflow contract

1. Before execution, resolve a unique experiment ID, strategy ID/version and complete parameter set, exact code revision, exact dataset identity, requested evaluation periods, and cost assumptions. Refuse to imply reproducibility when required identity fields are missing; record missing fields as unknown and surface them to the user.
2. Capture the exact effective configuration, not only defaults or a config-file path. Record command, working directory, runtime/tool versions, run start/end and exit status.
3. On completion or failure, create `docs/research/experiments/<EXPERIMENT_ID>.md` from the experiment template, filling results from machine-readable backtest output where possible. Preserve stdout/stderr or structured output as a linked artifact when practical; never place secrets in reports or logs.
4. Append exactly one row for the experiment to `EXPERIMENT_LOG.md`, linking its report. Prevent duplicate IDs and duplicate index rows on retries.
5. Record result state and decision disposition (for example `pending review`, `pass`, `reject`, or `inconclusive`) with explicit criteria and rationale. A metric threshold must not silently make a live-trading decision. Add a dated entry to `DECISION_LOG.md` when a human or authorized workflow decision is made; do not invent a decision if the run only generated evidence.
6. Update strategy evidence/status and dataset references when warranted, retaining prior definitions and history. Do not overwrite an existing report on rerun; a rerun gets a new ID.
7. Ensure report and index writes are recoverable: write a temporary report, validate it and its ID/link, then atomically publish it and append the index. If a process fails between writes, detect/reconcile the incomplete record on restart without duplicating it.

## Required report fields

Each report must capture, when available, and explicitly mark unknown/not-applicable otherwise:

- Experiment ID, run status, strategy ID/name/version, hypothesis, objective, run timestamp, operator/workflow, and decision status.
- Mechanical entry and exit rules; instrument, timeframe, direction, entry time and timezone; TP, SL, filters, sizing/risk, all test parameters, and order/tie-breaking behavior.
- Exact dataset ID and file path, SHA-256, source/provenance, schema, timestamp convention, requested and actual date range, row/bar count before and after exclusions, and transformations.
- Code repository, full commit hash, dirty/uncommitted state if relevant, exact test command, working directory, runtime/dependency versions, and linked raw result artifacts.
- Trade count, wins/losses, win rate, profit factor with formula/convention, net R, expectancy per trade, max drawdown with unit/basis, maximum losing streak, and any additional relevant metric definitions.
- Annual and monthly breakdown, including periods with no trades and any partial periods.
- Spread, slippage, commission/swap/transaction-cost assumptions; base and stress scenarios, with stress parameters and outcomes.
- Train, validation and untouched out-of-sample boundaries and separate results. Document selection/leakage controls and whether parameters were tuned against any period.
- Audit findings, unresolved limitations, reproducibility status, pass/reject/inconclusive decision, criterion-by-criterion reasoning, rejected alternatives where relevant, and next experiment/action.

## Mode support

The workflow must expose the two user-selectable modes in `MASTER_PROJECT_STATE.md`: (1) consultation/development advice when requested; and (2) direct testing/comparison of user-selected strategies. Mode 2 must accept already-defined strategies and parameter matrices without requiring a newly invented strategy. Consultation output is not a backtest result unless a run actually occurs.

## Acceptance checks

- A successful run produces one complete report and one index row with matching unique ID and working relative link.
- A failed/interrupted/no-trade run also produces a report and accurately records status; partial metrics are not presented as complete.
- Repeated invocation/recovery cannot create duplicate rows or overwrite an existing experiment report.
- All unknowns are explicit; no missing values are fabricated, and no credential material is recorded.
- Given a report's code revision, data checksum, parameters, command and documented environment, another operator can reproduce or explain any mismatch.
- Train/validation/out-of-sample periods and cost assumptions are visible in summaries; no single aggregate PF is presented as sufficient evidence by itself.
- Tests cover report generation, index update, unique-ID collision, failure recovery, idempotency and secret redaction.
- The two workflow modes are independently tested, including mode 2 executing a user-provided strategy without agent-invented strategy content.

## Implementation boundary

Do not claim this requirement is satisfied until the workflow is implemented, tests pass, and a real backtest demonstrates report/index generation. Update the status here and in `MASTER_PROJECT_STATE.md` only with evidence and code references.

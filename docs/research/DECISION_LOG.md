# Decision Log

Record decisions that affect research direction, strategy status, data, methods, or acceptance criteria. Add new entries at the end. Do not erase superseded decisions; append a reversal or replacement with a link to the earlier entry.

## DEC-2026-10-13-001: Keep 55/68 configuration test-only

- Date: 2026-10-13 (recorded with this research system)
- Decision: Treat the reported current BUY 09:34, TP 55 pips, SL 68 pips, 0.7% risk configuration as a test configuration, not as a profitable, approved, or production-ready strategy.
- Evidence: User supplied this configuration; the external QuantDinger backtester/config was not available for direct inspection in this task.
- Alternatives considered: declaring the setup selected based on configuration presence; rejected because configuration presence is not performance evidence.
- Consequences: exact mechanics and a reproducible baseline experiment are still required.
- Next action: inspect config and rules in the QuantDinger checkout, run a fully documented baseline, and audit data/execution assumptions.

## DEC-2026-10-13-002: Preserve the 67/93 candidate as unverified

- Date: 2026-10-13 (recorded with this research system)
- Decision: Retain BUY 09:34 TP 67 / SL 93 as a research candidate, and preserve the reported PF values (full period 1.082; 2026 1.040) only as reported-unverified figures.
- Evidence: User-provided historical figures; original run output, code revision, exact periods and dataset identity were not inspected.
- Alternatives considered: accept the metrics as validated; rejected because they cannot currently be independently reproduced or audited.
- Consequences: no profitability or deployment claim; report is reconstructed with unknowns explicit in [EXP-HIST-001](experiments/EXP-HIST-001.md).
- Next action: recover original artifacts if available and perform an exact reproducibility run with complete costs and out-of-sample checks.

## DEC-2026-10-13-003: Support two user-selectable workflow modes

- Date: 2026-10-13
- Decision: The target autonomous workflow must offer strategy consultation/development advice when requested and direct testing/comparison of user-selected strategies. Testing mode must not require the agent to invent a new strategy every time.
- Evidence: Project requirement supplied by the user.
- Alternatives considered: forcing strategy generation before every test; rejected because it prevents straightforward evaluation of user-defined candidates.
- Next action: implement selection and run/report orchestration as a separate code change; record actual behavior only after tests verify it.

## DEC-2026-10-13-004: Automated reports are a future requirement

- Date: 2026-10-13
- Decision: Require future backtest execution to create a Markdown report and update the experiment index automatically, including result and decision status. This task documents the contract only; reporting is not implemented here.
- Evidence: User requirement; implementation has not been inspected or built.
- Next action: implement and test against [AUTOMATED_REPORTING_SPEC.md](AUTOMATED_REPORTING_SPEC.md), then update project state with verified implementation evidence.

# Research Records

This directory is the durable, Markdown source of truth for TradingAgents + FTMO XAUUSD backtesting research. Record facts and decisions here rather than relying on chat history. Unknown or unverified details must stay explicitly marked; never fill gaps by inference.

## Current state

- TradingAgents checkout: `D:\Ai\TradingAgents`
- Inspected source commit: `be952b8eccb49720509af544c6675233bc1f10d0` (locally verified when these records were seeded)
- Existing origin: <https://github.com/TauricResearch/TradingAgents.git> (locally verified)
- User's fork: <https://github.com/absmikat-bit/TradingAgents> (user-provided; remote not inspected or configured here)
- Backtester: QuantDinger repository, `mt5_python_backtest/` (user-provided; that repository is not present in this workspace)
- Current test configuration and dataset claims: see [MASTER_PROJECT_STATE.md](MASTER_PROJECT_STATE.md) and [DATASET_MANIFEST.md](DATASET_MANIFEST.md). They have not been independently inspected in the backtester repository.

## Record map

- [MASTER_PROJECT_STATE.md](MASTER_PROJECT_STATE.md): project facts, workflow goals, current status, and verification boundaries.
- [STRATEGY_REGISTER.md](STRATEGY_REGISTER.md): strategy definitions, status, parameters, and evidence.
- [EXPERIMENT_LOG.md](EXPERIMENT_LOG.md): append-only index; every entry links to a report in `experiments/`.
- [DECISION_LOG.md](DECISION_LOG.md): dated decisions, rationale, rejected alternatives, and follow-up.
- [DATASET_MANIFEST.md](DATASET_MANIFEST.md): dataset identity, provenance, range, checksum, and unresolved metadata.
- [AUTOMATED_REPORTING_SPEC.md](AUTOMATED_REPORTING_SPEC.md): requirements for future automatic run reports and index updates. Reporting is not implemented by this documentation task.
- [templates/EXPERIMENT_TEMPLATE.md](templates/EXPERIMENT_TEMPLATE.md): copy for each new run report.
- [experiments/README.md](experiments/README.md): report naming, lifecycle, and append-only rules.
- [experiments/EXP-HIST-001.md](experiments/EXP-HIST-001.md): seeded, unverified historical candidate result.

## Working rules

1. Give every actual run a unique experiment ID and its own report. Use `EXP-YYYYMMDD-NNN` for new runs; reserve `EXP-HIST-NNN` for reconstructed historical records whose original run date is unknown.
2. Append to the experiment index; do not silently rewrite or remove prior entries. Correct material errors with a dated correction or superseding experiment, preserving the original record and its audit trail.
3. Keep reports immutable after review except for clearly dated audit/correction appendices. A rerun is a new experiment, even when parameters are identical.
4. Record exact code revision, data identity, test command, assumptions, and results. Link code and artifacts by stable repository-relative paths or immutable URLs where possible.
5. Label evidence `verified`, `reported-unverified`, `pending`, or `not-applicable`. A user-provided fact is not independently verified merely because it is written here.
6. Do not store API keys, tokens, passwords, `.env` values, or other secrets in these records.
7. Keep exploratory, validation, and out-of-sample periods explicit. Do not describe a test configuration as profitable, approved, or production-ready without reproducible evidence and an explicit decision.

## Updating across chats and Codespaces

Start with this README and `MASTER_PROJECT_STATE.md`. Before a run, identify the exact code revision and dataset file. After a run, create the report from the template, append one index row, update the relevant strategy/decision status, and preserve enough commands and artifact references for another person to reproduce or audit it. If the automated reporting workflow is later implemented, it must satisfy `AUTOMATED_REPORTING_SPEC.md` and be verified as implemented before this documentation claims it is live.

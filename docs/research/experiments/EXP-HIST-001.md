# EXP-HIST-001: XAUUSD BUY 09:34 TP 67 / SL 93 historical candidate

- Record type: reconstructed historical research claim; not a newly executed run
- Status: reported-unverified
- Original run date/time: unknown
- Strategy ID/version: `STRAT-XAU-0934-67-93` (registered from known partial parameters)
- Decision status: candidate; pending exact definition, audit and reproducible rerun

## Objective and hypothesis

- Original question/hypothesis: unknown.
- Candidate under record: BUY XAUUSD at 09:34 with TP 67 pips and SL 93 pips.
- Comparison/baseline: unknown.

## Strategy and parameters

- Instrument / timeframe: XAUUSD / M1, association to the reported run not independently verified.
- Direction: BUY.
- Entry time: 09:34; timezone and entry trigger/order timing unknown.
- Take profit: 67 pips; pip-to-price conversion and rounding unknown.
- Stop loss: 93 pips; pip-to-price conversion and rounding unknown.
- Risk and position sizing: unknown.
- Filters, exits beyond TP/SL, daily trade limits, forced close, order behavior, and TP/SL same-bar tie-break: unknown.
- Other test parameters: unknown.

## Dataset

- Dataset ID: unknown; the run's association with `DATA-XAUUSD-M1-FTMO-REPORTED-001` is pending verification.
- Exact file/path, SHA-256, source/export method, schema, timezone and DST convention: unknown.
- Full-period date boundaries, actual included range, and bar count: unknown.
- 2026 subperiod boundaries: unknown; “2026 results” is the extent of the supplied description.
- Data quality checks and transformations: unknown.

## Code and execution

- Repository/path and full code commit: unknown.
- Exact command, working directory, runtime/dependency versions, run date, exit status and raw output: unknown.
- Original report/log/artifact link: none supplied.
- Reproduction status: not reproduced; this record preserves only the reported figures.

## Results

The following values were supplied as previously reported research figures and have not been independently revalidated in this task. All other results are unknown.

| Period label as reported | Trades | Win rate | PF | Net R | Expectancy | Max DD | Max losing streak | Evidence |
|---|---:|---:|---:|---:|---:|---:|---:|---|
| Full period (exact dates unknown) | unknown | unknown | 1.082 | unknown | unknown | unknown | unknown | reported-unverified |
| 2026 (exact boundaries unknown) | unknown | unknown | 1.040 | unknown | unknown | unknown | unknown | reported-unverified |

- Profit-factor definition and whether the figures include spread, slippage, commission or swap: unknown.
- Annual/monthly breakdown beyond the reported 2026 PF: unknown.
- Train/validation/out-of-sample split and tuning history: unknown.

## Costs and execution stress

Spread, slippage, commission, swap, execution/fill assumptions and stress-test results were not supplied. No claim about net-of-cost performance can be made from the reported PF values alone.

## Audit and disposition

- Audit findings: original source artifacts, code commit, exact rule definition, dataset identity, tested date boundaries, sample size and cost conventions are unavailable.
- Decision: retain as a research candidate only; do not treat as validated or production-ready.
- Reasoning: the two PF figures are incomplete secondary claims without enough provenance or context for reproduction, uncertainty assessment, or leakage/cost audit.
- Next actions: recover the original backtest artifacts if possible; verify the exact rules and data; run the identical candidate on identified data; capture full metrics, annual/monthly and train/validation/out-of-sample results, cost stress tests, and an audit.
- Related records: [strategy register](../STRATEGY_REGISTER.md), [dataset manifest](../DATASET_MANIFEST.md), [decision log](../DECISION_LOG.md), [experiment index](../EXPERIMENT_LOG.md).

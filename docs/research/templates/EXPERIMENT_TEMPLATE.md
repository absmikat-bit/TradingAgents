# <EXPERIMENT_ID>: <short descriptive title>

- Record type: actual run / reconstructed historical record
- Status: completed / failed / interrupted / no trades / reported-unverified
- Run date/time (with timezone): <value or unknown>
- Strategy ID/version: <value>
- Decision status: pending review / pass / reject / inconclusive / not assessed

## Objective and hypothesis

- Question: <what is being tested>
- Hypothesis: <falsifiable statement, or unknown for historical reconstruction>
- Comparison/baseline: <strategy and parameters, or none>

## Strategy and parameters

- Instrument / broker symbol / timeframe: <...>
- Entry rules (mechanical): <...>
- Exit rules (mechanical): <...>
- Direction: <...>
- Entry time and timezone: <...>
- TP / SL and units/conversion: <...>
- Filters and exclusions: <...>
- Risk/sizing/compounding: <...>
- Order, gap, intrabar TP/SL tie-break and forced-close behavior: <...>
- Other test parameters: <...>

## Dataset

- Dataset ID: <...>
- Exact input file/path: <...>
- SHA-256: <...>
- Source and export/provenance: <...>
- Schema and timezone/DST convention: <...>
- Requested date range: <...>
- Actual included date range: <...>
- Bar count before / after filtering: <...>
- Cleaning, resampling, filtering or other transformations: <...>
- Data quality audit (gaps, duplicates, invalid rows): <...>
- Evidence status: verified / reported-unverified / pending

## Code and execution

- Repository and branch (if relevant): <...>
- Full code commit hash: <...>
- Dirty/uncommitted changes: <...>
- Exact command and working directory: <...>
- Runtime and relevant dependency versions: <...>
- Start/end, exit status, run status: <...>
- Raw output/log/artifact links: <...>
- Reproduction notes: <...>

## Results

Define metric conventions if the backtester does not define them unambiguously. Use `unknown` when unavailable; never infer a value.

| Metric | Result | Definition / notes |
|---|---:|---|
| Trades | unknown | Include completed/open/filtered-trade convention |
| Wins / losses / breakeven | unknown | |
| Win rate | unknown | State denominator |
| Profit factor | unknown | State gross profit/loss convention |
| Net R | unknown | State risk unit and aggregation |
| Expectancy per trade | unknown | State units and sample |
| Maximum drawdown | unknown | State currency/percent/R and equity basis |
| Maximum losing streak | unknown | State treatment of breakeven trades |

### Annual and monthly breakdown

| Period | Trades | Win rate | PF | Net R | Expectancy | Max DD | Max losing streak | Notes |
|---|---:|---:|---:|---:|---:|---:|---:|---|
| unknown | unknown | unknown | unknown | unknown | unknown | unknown | unknown | Replace with explicit periods; include zero-trade periods |

## Costs and execution stress

- Spread model/value and source: <...>
- Slippage model/value: <...>
- Commission, swap and other transaction costs: <...>
- Base-case result after costs: <...>
- Stress tests (e.g. widened spread, adverse slippage, delayed entry): <scenario, exact settings, result>
- Fill/gap/intrabar assumptions and limitations: <...>

## Train, validation and out-of-sample

| Split | Exact date/time boundaries | Trades | PF | Net R | Other key results | Was it used for tuning? |
|---|---|---:|---:|---:|---|---|
| Train | unknown | unknown | unknown | unknown | unknown | unknown |
| Validation | unknown | unknown | unknown | unknown | unknown | unknown |
| Out-of-sample | unknown | unknown | unknown | unknown | unknown | unknown |

Document leakage controls, selection procedure, boundary rationale and any repeated testing against the out-of-sample period: <...>

## Audit and disposition

- Audit findings: <...>
- Known limitations / unresolved fields: <...>
- Reproducibility status: reproduced / partial / not reproduced / not assessable
- Decision: pass / reject / inconclusive / pending review / not assessed
- Criteria and result against each criterion: <...>
- Reasoning and rejected alternatives: <...>
- Next experiment/action: <...>
- Related strategy, dataset, decision and experiment links: <...>

## Historical claim caveat (remove for ordinary new runs)

If this is reconstructed from a secondary report, state exactly which values are reported, who/source supplied them if known, and that original artifacts were unavailable. Do not present these as independently reproduced. Leave unknown run date, code revision, dataset, commands and parameters explicit.

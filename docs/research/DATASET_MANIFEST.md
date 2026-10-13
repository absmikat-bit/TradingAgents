# Dataset Manifest

Maintain one entry per immutable data file/version. A changed file, timezone interpretation, cleaning operation, or export creates a distinct dataset identity. Never identify a dataset only as “the XAUUSD data.”

## DATA-XAUUSD-M1-FTMO-REPORTED-001

| Field | Value | Evidence status |
|---|---|---|
| Instrument | FTMO XAUUSD | User-provided; broker symbol/contract metadata pending |
| Timeframe | M1 | User-provided |
| Bar count | 1,435,623 | User-provided; not independently counted |
| First timestamp | `2022-08-29 01:05` | User-provided; timezone not specified |
| Last timestamp | `2026-09-30 23:49` | User-provided; timezone not specified |
| Exact filename and path | Unknown | Pending inspection of QuantDinger checkout |
| File format and schema | Unknown | Pending |
| Data source and export method | Described as FTMO dataset | Exact source/export provenance pending |
| Timestamp timezone / DST convention | Unknown | Pending; essential for 09:34 entry interpretation |
| SHA-256 checksum | Unknown | Pending; calculate from the exact immutable input file |
| Duplicate, missing-bar and malformed-row audit | Unknown | Pending |
| Price precision, pip size and contract specs | Unknown | Pending verification against dataset/backtester/broker rules |
| Associated experiments | Historical candidate association not verified | Do not assume the historical PF figures used this exact file until confirmed |

### Use and verification notes

The date range and count above are supplied project facts, not an independently counted or checksummed dataset. The exact underlying file was not found in the current `D:\Ai\TradingAgents` workspace; the stated backtester is in the separate QuantDinger repository. Until path, checksum, timezone and schema are captured, this manifest entry is a provisional identity and cannot by itself establish reproducibility.

For each run, the experiment report must reference the exact dataset ID and also record the resolved path, checksum, date bounds actually used, row/bar count after filtering, and any transformations. Do not overwrite a dataset file in place and keep the same identity after data changes.

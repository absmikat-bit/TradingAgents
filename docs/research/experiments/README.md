# Experiment Reports

Store one Markdown report per unique experiment ID in this directory. Reports are the durable evidence record behind rows in `../EXPERIMENT_LOG.md`.

## Naming and lifecycle

- New run: `EXP-YYYYMMDD-NNN.md`, with run date and next unused sequence for that date.
- Reconstructed history with unknown date: `EXP-HIST-NNN.md`.
- The ID in filename, report heading and index row must match exactly.
- Copy `../templates/EXPERIMENT_TEMPLATE.md` for each new record.
- Record actual runs even when they fail, are interrupted or produce zero trades.
- Never overwrite a report with a rerun. Create a new ID and cross-link it to the prior run.
- Keep changes append-only after review. Corrections or additional audits should be dated and appended, preserving the original claims.
- Distinguish `verified`, `reported-unverified`, `pending`, and `not-applicable`; unknown values stay unknown.

## Existing reports

- [EXP-HIST-001.md](EXP-HIST-001.md): reconstructed candidate metrics supplied as historical research claims; original run artifacts are unavailable and the figures have not been independently validated.

Do not add credentials, `.env` values, or other secrets to experiment reports or linked artifacts.

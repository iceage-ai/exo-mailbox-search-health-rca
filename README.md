# exo-mailbox-search-health-rca

Mailbox search/index health triage with action-focused troubleshooting steps.

## Engine Logic
1. Ingest diagnostic results.
2. Classify dominant root-cause bucket.
3. Return **next step** actions (not raw data only).

## Usage
```powershell
./powershell/rca-engine.ps1 -InputPath ./sample-signals.json -AsJson
```

## Output Contract
- Category
- Confidence
- Reason
- Diagnostics
- NextSteps
- AffectedUser / AffectedUserEmail (example placeholders)

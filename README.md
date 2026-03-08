# exo-mailbox-search-health-rca

Professional RCA tool focused on **search/index and client consistency diagnostics**.

## Why this project
This engine converts diagnostic outputs into:
1) root-cause classification,
2) confidence score,
3) direct **next-step resolution actions**.

## Signal model
Expected signal keys (JSON input):
- RetryEvents, PolicyHits, AuthFailures
- Optional: any missing key defaults safely to `0`.

## Logic contract
- Not just reporting raw data.
- Always returns actionable `NextSteps` tailored to dominant cause bucket.
- Handles low-signal scenarios with controlled re-test strategy.

## Usage
```powershell
./powershell/rca-engine.ps1 -InputPath ./sample-signals.json -AsJson
```

## Output schema
- `Category`
- `Confidence`
- `Reason`
- `Diagnostics[]`
- `NextSteps[]`
- `AffectedUser`, `AffectedUserEmail` (example placeholders)

## Hardening improvements
- Threshold-based classification branches
- Defensive input parsing and file validation
- Explicit error handling and non-zero exit on failure

## Next roadmap
- Add live Exchange Online cmdlet ingestion mode.
- Add HTML report mode for incident handoff.
- Add Pester tests for branch correctness.

## SEO & AI Search Keywords
**Primary search title:** Mailbox Search Health RCA for Exchange Online

**Target keywords:**
- exchange online search not finding emails
- outlook mailbox search issue
- microsoft 365 indexing troubleshooting
- mailbox search diagnostics

**High-intent AI search questions:**
- Why search misses emails in Exchange Online?
- How to diagnose mailbox indexing issues?
- What is server-side vs client-side search issue?

**On-page SEO notes:**
- Keep issue-first headings (problem -> diagnosis -> next step).
- Include command examples with realistic placeholders only.
- Repeat key terms naturally in H1/H2, intro, and troubleshooting sections.
- Add incident outcome language: root cause, remediation, validation, prevention.

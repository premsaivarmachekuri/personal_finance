---
description: "Phase 7: Documentation — launch the tech-writer-agent to produce README, API reference, user guide, and data dictionary"
allowed-tools: Read, Bash, Agent
---

# Phase 7: Documentation

## Pre-flight Checks

1. Verify `specs/09-review-report.md` exists — if not: "Run /phase-6-review first."
2. Read `specs/09-review-report.md` and check the Verdict line:
   - If `BLOCK`: STOP — "The review report has blocking issues. Fix them and re-run /phase-6-review before starting documentation."
   - If `CONDITIONAL APPROVAL`: Ask user: "The review has conditional approval. Have all listed required actions been resolved? Confirm to proceed."
   - If `APPROVED`: proceed.

---

## Launch

Invoke the **tech-writer-agent** with the following context:

> You are running Phase 7 of the personal finance app SDLC.
>
> Start by reading ALL of:
> - CLAUDE.md
> - specs/00-project-brief.md through specs/09-review-report.md (all 10 spec files)
> - All files in src/
>
> Check specs/09-review-report.md Verdict before proceeding. Do not write docs if verdict is BLOCK.
>
> Produce:
> - README.md (update the existing file — setup, features, architecture overview, contributing)
> - docs/api-reference.md (developer API reference with curl examples for every endpoint)
> - docs/user-guide.md (end-user feature walkthroughs for all P0 stories)
> - docs/data-dictionary.md (all entities from specs/05 in plain-language table format)
>
> Follow all instructions in tech-writer-agent. Present a summary and wait for user approval.

---

## After Phase 7 Completes

```bash
git add README.md docs/
git commit -m "phase 7: documentation — README, API reference, user guide, and data dictionary complete"
```

**The pipeline is complete.** Your application is built, tested, reviewed, and documented from spec.

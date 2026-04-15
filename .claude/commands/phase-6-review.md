---
description: "Phase 6: Code Review — launch the reviewer-agent to audit the implementation against all specs and produce a review report"
allowed-tools: Read, Bash, Agent
---

# Phase 6: Code Review

## Pre-flight Checks

1. Verify `specs/08-test-plan.md` exists — if not: "Run /phase-5-qa first."
2. Verify `src/` contains implementation files.
3. Check if `specs/09-review-report.md` already exists — warn if re-running.

---

## Launch

Invoke the **reviewer-agent** with the following context:

> You are running Phase 6 of the personal finance app SDLC.
>
> Start by reading ALL of:
> - CLAUDE.md
> - specs/00-project-brief.md through specs/08-test-plan.md (all 9 spec files)
> - All files in src/
> - All test files
>
> Review the implementation on two axes:
> 1. Spec adherence — does the code match specs/05 (data model), specs/06 (API), specs/07 (interfaces), and specs/08 (test plan)?
> 2. Code quality — correctness, security, maintainability
>
> Produce specs/09-review-report.md with:
> - Verdict: BLOCK | CONDITIONAL APPROVAL | APPROVED
> - All spec deviations (BLOCKING)
> - All security concerns (BLOCKING)
> - Code quality issues (non-blocking unless CRITICAL)
> - Missing P0 coverage
> - Passed checks
>
> Do not approve if any spec deviations or security concerns exist.
> Follow all instructions in reviewer-agent.

---

## After Phase 6 Completes

```bash
git add specs/09-review-report.md
git commit -m "phase 6: code review — review report complete"
```

**If verdict is BLOCK:** Fix all blocking issues, then re-run `/phase-6-review`.

**If verdict is APPROVED or CONDITIONAL APPROVAL (with fixes done):**
**Next step:** Run `/phase-7-docs`

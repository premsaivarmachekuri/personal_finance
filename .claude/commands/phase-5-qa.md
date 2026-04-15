---
description: "Phase 5: QA — launch the qa-agent to write the test plan and test code against all specs"
allowed-tools: Read, Bash, Agent
---

# Phase 5: QA

## Pre-flight Checks

1. Verify `src/` is not empty — if empty: "Run /phase-4-implement first."
2. Verify `specs/06-api-spec.md` and `specs/07-interface-spec.md` exist.
3. Check if `specs/08-test-plan.md` already exists — warn user if re-running.

---

## Launch

Invoke the **qa-agent** with the following context:

> You are running Phase 5 of the personal finance app SDLC.
>
> Start by reading ALL of:
> - CLAUDE.md
> - specs/00-project-brief.md through specs/07-interface-spec.md (all 8 spec files)
> - All files in src/
>
> Then produce:
> - specs/08-test-plan.md (Test strategy, coverage targets, and all test cases with traceability)
> - Test code files (using the test framework from specs/04, placed in the project's test directories)
>
> Required coverage:
> - Every P0 user story → at least one integration test
> - Every API endpoint from specs/06 → happy path + at least 2 error cases
> - Every business rule in specs/06 → a dedicated test case
>
> Run the tests after writing them. All tests must pass before reporting completion.
> Follow all instructions in qa-agent. Present a summary and wait for user approval.

---

## After Phase 5 Completes

```bash
git add specs/08-test-plan.md tests/
git commit -m "phase 5: QA — test plan and test suite complete, all tests passing"
```

**Next step:** Run `/phase-6-review`

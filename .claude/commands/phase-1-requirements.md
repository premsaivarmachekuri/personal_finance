---
description: "Phase 1: Requirements — launch the pm-agent to produce the PRD and user stories from the project brief"
allowed-tools: Read, Bash, Agent
---

# Phase 1: Requirements

## Pre-flight Checks

Before launching, I will verify:

1. **`specs/00-project-brief.md` exists**
   - Read the file. If missing: STOP — "Create and fill in specs/00-project-brief.md first, then re-run /phase-1-requirements."

2. **The brief is filled in**
   - If the file still contains `[FILL IN]` placeholder text: STOP — "specs/00-project-brief.md has unfilled sections. Please complete it before running Phase 1."

3. **Phase 1 has not already run**
   - Check if `specs/01-PRD.md` already exists. If it does, warn the user: "specs/01-PRD.md already exists. Running again will overwrite it. Confirm to proceed."

---

## Launch

Invoke the **pm-agent** with the following context:

> You are running Phase 1 of the personal finance app SDLC.
>
> Start by reading:
> - CLAUDE.md
> - specs/00-project-brief.md
>
> Then produce:
> - specs/01-PRD.md (Product Requirements Document)
> - specs/02-user-stories.md (Prioritized user stories with acceptance criteria)
>
> Follow all instructions in your agent definition (pm-agent). After writing both files, present a summary to the user and wait for their approval before marking this phase complete.

---

## After Phase 1 Completes

Once the pm-agent finishes and the user approves:

```bash
git add specs/01-PRD.md specs/02-user-stories.md
git commit -m "phase 1: requirements — PRD and user stories complete"
```

**Next step:** Run `/phase-2-architecture`

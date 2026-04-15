---
description: "Phase 2: Architecture — launch the architect-agent to produce the architecture document, tech stack, and data model"
allowed-tools: Read, Bash, Agent
---

# Phase 2: Architecture

## Pre-flight Checks

1. Verify `specs/01-PRD.md` exists — if not: "Run /phase-1-requirements first."
2. Verify `specs/02-user-stories.md` exists — if not: "Run /phase-1-requirements first."
3. Check if specs/03-05 already exist — warn user if re-running.

---

## Launch

Invoke the **architect-agent** with the following context:

> You are running Phase 2 of the personal finance app SDLC.
>
> Start by reading ALL of:
> - CLAUDE.md
> - specs/00-project-brief.md
> - specs/01-PRD.md
> - specs/02-user-stories.md
>
> Then produce:
> - specs/03-architecture.md (Architecture style, system diagram, ADRs, security, infra)
> - specs/04-tech-stack.md (All technology choices with pinned versions and rationale)
> - specs/05-data-model.md (ERD + complete entity definitions)
>
> Also update CLAUDE.md to fill in the "Code Conventions" and "Commands" sections based on your tech stack choices.
>
> Follow all instructions in your agent definition (architect-agent). Present a summary and wait for user approval.

---

## After Phase 2 Completes

```bash
git add specs/03-architecture.md specs/04-tech-stack.md specs/05-data-model.md CLAUDE.md
git commit -m "phase 2: architecture — arch decisions, tech stack, and data model complete"
```

**Next step:** Run `/phase-3-api-design`

---
description: "Phase 3: API Design — launch the api-designer-agent to produce API contracts and module interface specs"
allowed-tools: Read, Bash, Agent
---

# Phase 3: API Design

## Pre-flight Checks

1. Verify `specs/03-architecture.md` exists — if not: "Run /phase-2-architecture first."
2. Verify `specs/04-tech-stack.md` exists — if not: "Run /phase-2-architecture first."
3. Verify `specs/05-data-model.md` exists — if not: "Run /phase-2-architecture first."
4. Check if specs/06-07 already exist — warn user if re-running.

---

## Launch

Invoke the **api-designer-agent** with the following context:

> You are running Phase 3 of the personal finance app SDLC.
>
> Start by reading ALL of:
> - CLAUDE.md
> - specs/00-project-brief.md through specs/05-data-model.md (all 6 files)
>
> Then produce:
> - specs/06-api-spec.md (All API endpoint contracts with request/response shapes, business rules, and traceability)
> - specs/07-interface-spec.md (Module interface signatures for every layer)
>
> Follow all instructions in your agent definition (api-designer-agent). Present a summary and wait for user approval.

---

## After Phase 3 Completes

```bash
git add specs/06-api-spec.md specs/07-interface-spec.md
git commit -m "phase 3: api design — API contracts and interface specs complete"
```

**Next step:** Run `/phase-4-implement`

---
description: "Phase 4: Implementation — launch backend-dev-agent and frontend-dev-agent to build the application from approved specs"
allowed-tools: Read, Bash, Agent
---

# Phase 4: Implementation

## Pre-flight Checks

1. Verify `specs/06-api-spec.md` exists — if not: "Run /phase-3-api-design first."
2. Verify `specs/07-interface-spec.md` exists — if not: "Run /phase-3-api-design first."
3. Confirm with user: "Phase 4 will write code to src/. This is the first phase that modifies the codebase. Ready to proceed?"

---

## Launch

Phase 4 runs two agents. You may run them sequentially (backend first, then frontend) or in parallel if your setup supports it.

### Backend Agent

Invoke the **backend-dev-agent** with the following context:

> You are running Phase 4 (Backend) of the personal finance app SDLC.
>
> Start by reading ALL of:
> - CLAUDE.md (especially Code Conventions and Commands sections)
> - specs/00-project-brief.md through specs/07-interface-spec.md (all 8 spec files)
>
> Then implement the backend in src/backend/:
> 1. Project scaffold and dependencies (from specs/04)
> 2. Database schema and migrations (from specs/05)
> 3. Repository layer (from specs/07 interfaces)
> 4. Service layer (from specs/07 interfaces)
> 5. Auth middleware (from specs/03 security section)
> 6. API route handlers (from specs/06 — all endpoints)
> 7. Input validation and error handling
> 8. Seed script
>
> Run lint and type-check after each step. Do not proceed if they fail.
> Follow all instructions in backend-dev-agent. Report completion when all P0 endpoints pass lint and type-check.

### Frontend Agent

Invoke the **frontend-dev-agent** with the following context:

> You are running Phase 4 (Frontend) of the personal finance app SDLC.
>
> Start by reading ALL of:
> - CLAUDE.md (especially Code Conventions and Commands sections)
> - specs/00-project-brief.md through specs/07-interface-spec.md (all 8 spec files)
>
> Then implement the frontend in src/frontend/:
> 1. Project scaffold and dependencies (from specs/04)
> 2. Typed API client (from specs/06 — all endpoints)
> 3. Auth screens
> 4. App shell and routing
> 5. All feature screens for P0 user stories (from specs/02)
> 6. Settings screen
>
> Run lint and type-check after each screen group. Do not proceed if they fail.
> Follow all instructions in frontend-dev-agent. Report completion when all P0 screens pass lint and type-check.

---

## After Phase 4 Completes

```bash
git add src/
git commit -m "phase 4: implementation — backend and frontend complete"
```

**Next step:** Run `/phase-5-qa`

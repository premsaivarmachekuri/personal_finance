# Personal Finance App — CLAUDE.md

## Project Context
Personal finance application covering budgeting, expense tracking, income
management, and analytics. Uses a **spec-driven SDLC** where each phase
produces structured documents in `specs/` before any code is written.

---

## Workflow Law

- NEVER write code before `specs/06-api-spec.md` exists and is approved.
- NEVER modify a spec file from a previous phase without explicit user approval.
- ALL agents MUST read every prior spec file before starting their phase work.
- Commit spec files after each phase: `git add specs/ && git commit -m "phase N: <name>"`
- Spec files are the source of truth. Code must match specs — not the other way around.
- Each agent MUST begin by confirming: "I have read: CLAUDE.md, specs/00 through specs/0N"

---

## Phase Pipeline

| Phase | Slash Command | Agent | Reads | Produces |
|-------|---------------|-------|-------|---------|
| 0 | *(manual)* | Human | — | `specs/00-project-brief.md` |
| 1 | `/phase-1-requirements` | pm-agent | 00 | `specs/01-PRD.md`, `specs/02-user-stories.md` |
| 2 | `/phase-2-architecture` | architect-agent | 00-02 | `specs/03-architecture.md`, `specs/04-tech-stack.md`, `specs/05-data-model.md` |
| 3 | `/phase-3-api-design` | api-designer-agent | 00-05 | `specs/06-api-spec.md`, `specs/07-interface-spec.md` |
| 4 | `/phase-4-implement` | backend-dev-agent + frontend-dev-agent | 00-07 | `src/` |
| 5 | `/phase-5-qa` | qa-agent | 00-07 + src/ | `specs/08-test-plan.md` + test files |
| 6 | `/phase-6-review` | reviewer-agent | 00-08 + src/ | `specs/09-review-report.md` |
| 7 | `/phase-7-docs` | tech-writer-agent | 00-09 + src/ | `docs/` + updated `README.md` |

---

## Spec Directory

`specs/` — all spec files live here, tracked in git.

- Files are prefixed `00-` through `09-` so directory listings always show pipeline order.
- Never delete a spec file. Amend by appending a dated `## REVISION YYYY-MM-DD` section.
- Never overwrite `specs/00-project-brief.md` — it is human-authored and immutable.

---

## Domain Vocabulary

Use these terms consistently across all specs and code:

| Term | Definition |
|------|-----------|
| **User** | The authenticated person using the application |
| **Account** | A financial account (bank, credit card, cash wallet) belonging to a User |
| **Transaction** | A single debit or credit event on an Account |
| **Category** | A user-defined or system-defined label for Transactions (e.g., "Groceries") |
| **Budget** | A spending limit set for a Category over a BudgetPeriod |
| **BudgetPeriod** | The time window for a Budget (monthly, quarterly, annual) |
| **Report** | An aggregated view of Transactions, Budgets, or trends over time |

---

## Code Conventions

> **Status: To be filled in by architect-agent during Phase 2.**

Once the tech stack is chosen in `specs/04-tech-stack.md`, the architect-agent will populate:
- File naming conventions
- Folder structure inside `src/`
- Import style (absolute vs relative paths)
- Error handling pattern
- Env variable naming

---

## Commands

> **Status: To be filled in by architect-agent during Phase 2.**

Once the tech stack is decided, this section will contain the exact terminal commands for:
- Install dependencies
- Run development server
- Run tests
- Lint and type-check
- Build for production
- Run database migrations

---

## Gotchas

- `specs/00-project-brief.md` is human-authored and immutable — never overwrite it.
- Phase agents must not proceed if their required input specs are missing.
- Phase 4 (implementation) may run backend and frontend agents in parallel — both read the same spec files independently.
- Any deviation between code and specs found in Phase 6 is a BLOCKING issue — must be fixed before Phase 7.

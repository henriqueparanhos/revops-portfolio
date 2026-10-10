# ADR-0001: Hub repository plus one repository per project

- **Status:** Accepted
- **Date:** 2026-10-10
- **Deciders:** Portfolio author

## Context

The portfolio contains ten connected projects that mix SQL, Python, Power BI files, automation workflows, and documentation. A recruiter should be able to understand the whole program in one place and open any single project without noise.

## Decision

Use one **hub repository** (`revops-portfolio`) for the narrative, the company profile, the roadmap, decision records, and templates. Build each project in **its own repository**, following the standard structure in [`docs/templates/PROJECT_README_TEMPLATE.md`](../templates/PROJECT_README_TEMPLATE.md). The hub README links to every project.

## Consequences

**Positive**
- Each project can be pinned, starred, and read on its own.
- Cleaner commit history and release tags per project.
- The hub gives a coherent story without forcing readers into a large monorepo.

**Negative**
- Cross-project references must use links and versioned releases instead of relative paths.
- Shared assets (the NovaFlow company profile) live only in the hub and must be linked.

## Alternatives Considered

- **Monorepo with one folder per project.** Simpler linking, but harder to pin and present individual projects and mixes unrelated tooling.
- **Independent repositories with no hub.** Loses the shared NovaFlow narrative.

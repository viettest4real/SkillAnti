---
name: vibe-architect
description: >-
  Token-optimized architecture, security, cost-guardrail, and structural diff
  workflow for vibe-coding projects. Activate whenever creating a new software
  project, modifying existing project code/architecture, or auditing project
  security, API costs, and UI/UX polish.
---

# Vibe Architect — Router (Token-Optimized)

## Global Rules
- `OUTPUT_LANG`: Vietnamese (Keep technical terms, file paths, and code identifiers in English).
- `TOKEN_POLICY`: Progressive disclosure. Read **ONLY** the reference file matching current `MODE`. **NEVER** preload unmatched reference files.
- `COST_SAFETY`: Always flag paid APIs, infinite-loop billing risks, and exposed secrets.

## Mode Routing (Read ONLY matched file)
1. **IF** user asks to create/scaffold a new project, feature module, or architecture (`MODE == CREATE`):
   -> Read `[01-create-project.md](./references/01-create-project.md)`
2. **IF** user asks to edit, fix, refactor, or update an existing project (`MODE == MODIFY`):
   -> Read `[02-modify-project.md](./references/02-modify-project.md)`
3. **IF** user asks to review security, estimate API/cloud costs, or untangle messy code (`MODE == AUDIT`):
   -> Read `[03-audit-rescue.md](./references/03-audit-rescue.md)`

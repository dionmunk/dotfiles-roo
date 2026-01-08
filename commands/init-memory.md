---
description: "Create a project memory bank (.memory/) with imports + index, and enforce project memory rules."
---

You are running in a VS Code workspace.

Goal:
Create a persistent project memory bank under `.memory/` (kebab-case filenames), including an imports area for reference material, plus a project-specific rules file under `.roo/rules/` to enforce consultation of project memory before acting.

Rules:
- Do NOT overwrite existing files.
- Do NOT delete or rename any existing files.
- If a directory or file already exists, leave it unchanged.
- If a required file is missing, create it using the templates below.
- After completion, print a short summary listing what was created vs what already existed.

Steps:
1) Ensure the `.memory/` directory exists at the workspace root.
2) Ensure the `.memory/imports/` directory exists at the workspace root.
3) Ensure the following `.memory/imports/` subdirectories exist:
   - `.memory/imports/api/`
   - `.memory/imports/schemas/`
   - `.memory/imports/diagrams/`
   - `.memory/imports/references/`
4) Ensure the `.roo/rules/` directory exists at the workspace root.
5) Ensure the following `.memory/` files exist:
   - `.memory/README.md`
   - `.memory/index.md`
   - `.memory/project-brief.md`
   - `.memory/product-context.md`
   - `.memory/active-context.md`
   - `.memory/system-patterns.md`
   - `.memory/tech-context.md`
   - `.memory/progress.md`
   - `.memory/conventions.md`
   - `.memory/decisions.md`
   - `.memory/glossary.md`
6) Ensure the following imports README exists:
   - `.memory/imports/README.md`
7) Ensure the following rules file exists:
   - `.roo/rules/rules.md`

Templates (use these exactly for newly created files):

========================
.memory/README.md
========================
# Project Memory (`.memory/`)

This directory contains **persistent project context** shared by humans and automated tools.
It is the **source of truth** for understanding *why* this project exists, *how* it is built,
and *what* is currently happening.

If you are new to this repository, **start here**.

---

## Why This Exists

Projects accumulate context faster than code:
- architectural decisions
- constraints and tradeoffs
- ongoing work
- “gotchas” that aren’t obvious from reading files

The `.memory/` directory captures that context in a **structured, version-controlled way** so it:
- doesn’t live only in people’s heads
- doesn’t get lost across sessions
- stays close to the code

---

## How to Use This Folder

### If you are a developer:
- Read these files before making significant changes
- Update them when your work changes project direction or status
- Treat them like living documentation, not static specs

### If you are reviewing a PR:
- Check whether relevant `.memory/` files were updated
- Especially:
  - `active-context.md`
  - `progress.md`
  - `decisions.md`

### If you are onboarding:
1. Read `project-brief.md`
2. Read `system-patterns.md`
3. Skim `tech-context.md`
4. Check `active-context.md` to see what’s happening now

---

## File Overview

| File                 | Purpose                                                        |
| -------------------- | -------------------------------------------------------------- |
| `index.md`           | Quick links into the memory bank                               |
| `project-brief.md`   | High-level overview, goals, non-goals, success criteria        |
| `product-context.md` | Why the project exists, users, requirements                    |
| `active-context.md`  | Current focus, recent changes, next steps, risks               |
| `system-patterns.md` | Architecture, components, data flow, patterns                  |
| `tech-context.md`    | Stack, tooling, environments, constraints                      |
| `progress.md`        | Status, milestones, known issues                               |
| `conventions.md`     | Coding conventions and safety rules                            |
| `decisions.md`       | Architectural / product decision log                           |
| `glossary.md`        | Project-specific terminology                                   |
| `imports/`           | Reference material (API specs, schemas, diagrams, vendor docs) |

---

## Imported References

Additional reference material belongs in:

- `.memory/imports/`

See `.memory/imports/README.md` for organization and an import log.

---

## Writing Guidelines

- Prefer clear bullets over long prose
- Be factual; avoid speculation
- Label uncertainty clearly
- Keep entries short and scannable
- Dates are helpful for context

This is **working memory**, not a spec.

---

## Contribution Expectations

If your change:
- affects architecture
- introduces new constraints
- changes current focus
- creates long-term implications

…then it probably requires updating at least one file in `.memory/`.

Treat missing updates as a documentation bug.

========================
.memory/index.md
========================
# Project Memory Index

Use this index as a quick jump list.

## Start Here
- `.memory/README.md`

## Core Memory
- `.memory/project-brief.md`
- `.memory/product-context.md`
- `.memory/active-context.md`
- `.memory/system-patterns.md`
- `.memory/tech-context.md`
- `.memory/progress.md`
- `.memory/conventions.md`
- `.memory/decisions.md`
- `.memory/glossary.md`

## Imported References
- `.memory/imports/README.md`
- `.memory/imports/api/`
- `.memory/imports/schemas/`
- `.memory/imports/diagrams/`
- `.memory/imports/references/`

========================
.memory/imports/README.md
========================
# Imported References (`.memory/imports/`)

This folder contains **supporting reference material** that helps developers and automated tools understand
the project, but is not part of the core memory files.

Examples:
- API specifications (OpenAPI/Swagger, Postman collections)
- Database schemas or ERDs
- Architecture diagrams
- External vendor docs or integration notes
- Request/response examples
- “Golden” JSON payloads used for tests

## Where to Put Things

- `api/` — OpenAPI specs, Postman collections, API examples
- `schemas/` — DB schemas, ERDs, migrations notes
- `diagrams/` — PNG/SVG/PDF diagrams, sequence charts
- `references/` — vendor docs, RFC notes, external references

## Guidelines

- Keep imported files as small as practical
- Avoid secrets (no API keys, tokens, passwords)
- Prefer versioned/dated files when helpful
- Add a log entry below when you add or update a reference

## Import Log

- (YYYY-MM-DD) <short name> — <what it is> — <source/location> — <notes>

## Notes for Automated Tools

- Treat files in `.memory/imports/` as reference-only unless explicitly instructed otherwise.
- Prefer core memory files for “source of truth” decisions, and use imports to validate details (e.g., API shapes).

========================
.memory/project-brief.md
========================
# Project Brief

## Overview
- What is this project?
- One-paragraph summary.

## Goals
- Primary goals

## Non-Goals
- Explicitly out of scope

## Success Criteria
- How success is measured

## Scope Notes
- Constraints, boundaries, assumptions

========================
.memory/product-context.md
========================
# Product Context

## Why This Exists
- Problem statement
- Intended users

## Users & Use Cases
- Personas
- Primary workflows

## Requirements
- Functional requirements
- Non-functional requirements (performance, security, reliability)

## UX / Behavior Notes
- Interaction expectations
- Edge cases

========================
.memory/active-context.md
========================
# Active Context

## Current Focus
- What is being worked on right now

## Recent Changes
- High-level summary of recent updates

## Next Steps
- Immediate upcoming tasks

## Open Questions / Risks
- Unknowns, blockers, pending decisions

========================
.memory/system-patterns.md
========================
# System Patterns

## System Overview
- Architecture and boundaries

## Key Components
- Modules/services and responsibilities

## Data Flow
- How data moves through the system

## Patterns & Conventions
- Architectural patterns
- Error handling and retries
- Background/async processing

## Integrations
- External services, APIs, webhooks

## Security Notes
- Auth, permissions, secrets handling

========================
.memory/tech-context.md
========================
# Tech Context

## Stack
- Languages, frameworks, libraries

## Tooling
- Package managers, build tools, linters
- Test frameworks

## Environments
- Local, staging, production

## Constraints
- Platform, performance, compatibility limits

## Common Commands
- Run, test, lint, build

========================
.memory/progress.md
========================
# Progress

## Status
- Current phase or maturity

## Completed
- Finished milestones

## In Progress
- Active work

## Planned
- Upcoming milestones

## Known Issues / Tech Debt
- Bugs, gaps, refactors needed

========================
.memory/conventions.md
========================
# Conventions

## Code Style
- Formatting and naming rules

## Repo Structure
- Where things belong

## Testing Strategy
- Types of tests and expectations

## Change Management
- Prefer minimal diffs
- Avoid large rewrites unless requested
- Ask before deleting or renaming shared interfaces

## Safety Rules
- Always ask before:
  - Deleting files
  - Running destructive commands
  - Changing schemas or migrations
  - Modifying authentication or security behavior

========================
.memory/decisions.md
========================
# Decisions

> Record significant technical or product decisions here.

## Decision Template
- Date: YYYY-MM-DD
- Decision
- Context
- Options considered
- Rationale
- Consequences / follow-ups

========================
.memory/glossary.md
========================
# Glossary

> Project-specific terms and domain language.

- Term: Definition
- Term: Definition

========================
.roo/rules/rules.md
========================
## Project Memory Requirement (Strict)

Before answering, planning, or modifying code, you **must** consult all relevant files under the `.memory/` directory.

If required information is missing, outdated, or contradictory, **stop and ask for clarification** before proceeding.

If your proposed action conflicts with guidance in `.memory/`, **explicitly call out the conflict and do not proceed** until it is resolved.

If `.memory/` files cannot be accessed or do not exist, **pause and request confirmation** before continuing.

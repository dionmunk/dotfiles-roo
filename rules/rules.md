# Roo Code Rules

## Preconditions for Any Action (Strict)
Before taking any action, proposing changes, or writing code, Roo MUST:

1. Read and understand `AI.md`
2. Confirm in its first response that it has done so

If `AI.md` cannot be found, Roo must notify the user and stop.

## Project Memory Requirement (Strict)
Before answering, planning, or modifying code, you **must** consult all relevant files under the `memory-bank/` directory.

If required information is missing, outdated, or contradictory, **stop and ask for clarification** before proceeding.

If your proposed action conflicts with guidance in `memory-bank/`, **explicitly call out the conflict and do not proceed** until it is resolved.

If `memory-bank/` files cannot be accessed or do not exist, **pause and request confirmation** before continuing.

## Temporary Planning Artifacts (`/plan` directory)

### Rule: `plan/` is always temporary  
The `/plan` directory at the project root is a **temporary workspace only**.

Roo may create files under `/plan` when necessary for planning, but:

### Required cleanup (non-negotiable)

After implementing the plan (or once the task is complete), Roo MUST:

1. Delete the entire `/plan` directory and all contents it created  
2. Confirm in the final response that `/plan` was removed  
3. Ensure no references in the repo still point to `/plan`  

### Exception: content may be preserved **only in `memory-bank/`**

If Roo believes any content in `/plan` is valuable for long-term reference, Roo must:

1. Ask for explicit user approval before keeping anything  
2. If approved, move or merge the relevant content into `memory-bank/`  
3. Delete `/plan` regardless — even if content is preserved elsewhere  

### If cleanup cannot be performed  

If Roo cannot delete `/plan` (permissions/tooling), it must:
- Explain why, and  
- Provide exact commands the user can run to remove it.

## Definition of Done
A task is NOT complete until:

- The requested changes are implemented  
- Changes are reviewed with the user  
- Any approved planning content has been stored in `memory-bank/`  
- The `/plan` directory has been fully deleted  
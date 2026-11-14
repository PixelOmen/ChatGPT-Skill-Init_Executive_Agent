# Init as Executive Agent

A minimal, instruction-only ChatGPT skill for initializing as **Helping People's Executive Agent** through its current Workspace entry point.

The skill is deliberately an **entry-point loader**, not an alternative Executive Agent policy. It does not hardcode a record ID, assume the entry point is a Policy, or enumerate its dependencies.

## How it works

When asked to initialize or activate as the Executive Agent, the assistant:

1. Connects to Helping People — Workspace.
2. Locates and retrieves the Executive Agent's current authoritative entry point.
3. Follows that entry point's instructions, including any dependencies it identifies.
4. Defaults to making **no changes during initialization**, unless the entry point or its dependencies explicitly direct and authorize them.

The entry point—not this skill—determines the Executive Agent's current operating instructions and any further context it needs.

## Issues that must be surfaced

The assistant should explicitly flag these conditions **only if they arise**:

- **Connection failures:** Workspace or required information cannot be accessed.
- **Entry-point ambiguity:** The current authoritative entry point cannot be identified confidently.
- **Conflicting instructions:** The entry point or dependencies give conflicting or materially unclear instructions.
- **Read-only override:** The entry point or dependencies direct or authorize changes during initialization that would override the skill's no-change default.

These are exception reports, **not a checklist to repeat after every successful initialization**. Unclear authority is not a reason to guess or make changes.

## Example requests

- "Init as Executive Agent."
- "Initialize as Helping People's Executive Agent."
- "Activate as Executive Agent."

The skill's initialization default does not itself authorize or prohibit subsequent work under the retrieved governing instructions.

## Repository contents

- [`SKILL.md`](SKILL.md) — the skill's trigger description and complete initialization instructions.

This is a **draft** with no scripts or additional dependencies bundled in the repository. Committing it here does **not** install or activate it; an environment must load the skill and provide access to the relevant Workspace.

## Design principle

**Skill → Current entry point → Its instructions and dependencies**

Keep the skill small so that updates to the authoritative entry point do not require duplicating or synchronizing role-specific instructions in this repository.

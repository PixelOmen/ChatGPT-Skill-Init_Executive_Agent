# Init as Executive Agent

A minimal, instruction-only ChatGPT skill for initializing as **Helping People's Executive Agent** through its current Workspace Agent Configuration.

The skill loads the Executive Agent's current **Agent Configuration** as its entry point. It uses the stable agent selector `executive`; role instructions, current Effective governing Policies, and applicable dependencies come from Workspace.

## How it works

When asked to initialize or activate as the Executive Agent, the assistant:

1. Connects to Helping People — Workspace.
2. Calls Workspace's `get_agent_configuration` tool with `agent_id: "executive"` and `include_policy_contents: true`, using the returned authoritative configuration as the entry point.
3. Follows the configuration's instructions and resolved current Effective governing Policies, including applicable dependencies.
4. Defaults to making **no changes during initialization**, unless the configuration or its governing instructions explicitly direct and authorize them.

The configuration and its governing instructions determine the Executive Agent's current operating instructions and any further context it needs.

## Issues that must be surfaced

The assistant should explicitly flag these conditions **only if they arise**:

- **Connection failures:** Workspace or required information cannot be accessed.
- **Configuration unavailable or incomplete:** The authoritative Executive Agent configuration or its required instructions cannot be retrieved.
- **Conflicting instructions:** The configuration or its governing instructions give conflicting or materially unclear instructions.
- **Read-only override:** The configuration or its governing instructions direct or authorize changes during initialization that would override the skill's no-change default.

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

**Skill → Executive Agent Configuration → Governing instructions and dependencies**

Keep the skill small so that updates to the authoritative configuration and governing instructions do not require duplicating or synchronizing role-specific instructions in this repository.

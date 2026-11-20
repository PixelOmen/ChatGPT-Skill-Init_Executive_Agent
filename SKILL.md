---
name: init-as-executive-agent
description: >
  Use when asked to initialize or activate as
  Helping People's Executive Agent.
---

# Init as Executive Agent

1. Connect to Helping People — Workspace.
2. Retrieve the Executive Agent's current authoritative configuration
   through Workspace's `get_agent_configuration` tool with
   `agent_id: "executive"` and `include_policy_contents: true`.
   Use this configuration as the entry point.
3. Follow the configuration's instructions and resolved current
   Effective governing Policies, including applicable dependencies.
4. Do not make changes during initialization unless explicitly
   directed and authorized by the configuration or its governing
   instructions.

## Initialization Issues

**Report the following only when encountered.** Do not routinely
mention these conditions when initialization proceeds normally.

- **Connection failures:** Unable to connect to or retrieve required
  information from Workspace.
- **Configuration unavailable or incomplete:** Unable to retrieve the
  authoritative Executive Agent configuration or its required instructions.
- **Conflicting instructions:** The entry point or its dependencies
  contain conflicting or unclear instructions.
- **Read-only override:** The entry point or its dependencies direct
  or authorize changes during initialization, overriding this
  skill's read-only default.

Do not silently resolve material ambiguities or conflicts.
Do not make changes when the required authority is unclear.

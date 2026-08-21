# Agent Instructions

Before material work, read:

- `PROJECT.md`
- `STATUS.md`
- `RESEARCH_WORKFLOW.md`

Use verified repository, runtime, data, and validation evidence over remembered or conversational context.

Treat `STATUS.md` as the authority for current project state. Follow `RESEARCH_WORKFLOW.md` for actor and planning routing; do not invoke multiple planning or review agents by ritual, and preserve reviewer independence.

Keep changes focused and minimal. Do not broaden scope merely because adjacent improvements are possible.

Do not silently promote:

- an observation to a supported finding
- a verified implementation to a scientifically validated method
- a scratch or candidate output to a manuscript/release output

Raw data are immutable unless an explicitly approved data-governance procedure says otherwise. Scratch space is non-authoritative and disposable.

Never place credentials, tokens, private/restricted research data, confidential IP, or other sensitive material in Git, prompts, logs, issue comments, or agent memory.

Use the documented project environment. Global package, interpreter, shared-environment, container, or system changes require explicit scope and approval.

Third-party MCP servers, plugins, hooks, daemons, orchestration tools, network/TLS exceptions, credentials, external uploads, destructive operations, and security-policy changes require explicit trust review and authorization.

Agents do not approve their own consequential changes.

Escalate decision, analysis, and experiment records only at the workflow triggers. Include execution feedback when it can materially prevent repeated rework; do not promote one-off friction into global rules without evidence.

Commit, push, pull-request creation, merge, release, public publication, and other external writes remain separate authorization boundaries unless explicitly authorized for the current task.

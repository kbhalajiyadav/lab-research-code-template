# Research Workflow

This document defines the project operating standard. It is intentionally compact: rigor should increase with consequence rather than burdening early exploration with release-grade process.

## Truth hierarchy

When sources disagree, prefer evidence in this order:

1. verified current runtime or instrument evidence
2. Git state, manifests, configuration, and versioned data definitions
3. deterministic tests and reproducible validation evidence
4. `PROJECT.md`, `STATUS.md`, and project documentation
5. documented decisions and issue/PR history
6. agent memory
7. chat recollection

Conversation and agent memory are useful context, not authoritative project truth.

## Progressive rigor

Use the lowest rigor level that is sufficient for the current consequence.

### E — Exploratory

Use while determining whether an idea, hypothesis, or workflow is promising.

Minimum expectations:

- project question and hypothesis are understandable
- code or notebook can be rerun by its author
- assumptions and important observations are recorded
- confidential, restricted, or sensitive material remains in approved locations

### R — Reproducible

Promote when work is repeated, shared, used for decisions, or becoming a stable workflow.

Add:

- one documented authoritative environment
- stable input and output expectations
- tests for stable/reusable logic
- a small representative or synthetic fixture when practical
- enough documentation for another person to rerun the workflow

### V — Validated

Promote when a method or result supports a consequential scientific claim.

Add as applicable:

- explicit distinction between implementation verification and scientific validation
- reference or conventional comparator when one exists
- replication
- robustness or sensitivity checks
- material provenance records
- documented limitations and validity scope
- durable records for decisions that materially affect interpretation

### P — Publication / Release

Promote before external dissemination, archival release, or manuscript-critical freezing.

Require as applicable:

- exact Git commit or release tag
- authoritative environment/version record
- exact input dataset identifiers and integrity references
- promoted figures/tables/results with traceable lineage
- final validation evidence
- archive/release information
- independent review where consequence warrants it

A project may move backward to exploration after new evidence. A scientific pivot is not a process failure.

## Verification and validation

Keep these concepts separate.

**Verification** asks: did the implementation perform the intended calculation or workflow correctly?

Examples include unit tests, schema checks, known fixtures, formula checks, and deterministic reproduction.

**Scientific validation** asks: is the method appropriate for the claimed scientific purpose and scope?

Examples include reference-method comparison, independent datasets, replication, physical benchmarks, bias assessment, and robustness analysis.

A passing software test suite does not by itself validate a scientific method.

## Canonical WSL placement

Use this mapping unless a project documents an approved alternative:

```text
~/src/<project>       canonical Git working tree
~/data/<project>      durable project data
~/scratch/<project>   temporary/disposable working data
```

Hard requirements:

- nothing indispensable may exist only in `~/scratch`
- anything outside Git required to reproduce accepted work must be identifiable from the repository
- raw data should remain immutable; corrections create processed or derived representations
- large, private, restricted, or collaborator-controlled data should stay in approved storage rather than being copied into Git

## Environment authority

A project should converge on one authoritative environment mechanism before reproducible or validated work is accepted.

The repository may retain compatibility examples, but project documentation must make clear which environment definition is authoritative.

Do not perform global package, interpreter, shared-environment, container, or system changes merely to satisfy one project unless that change is explicitly in scope.

## Session continuity

### Start a material session

Read in this order:

1. `PROJECT.md`
2. `STATUS.md`
3. the latest relevant GitHub issue, decision, or review checkpoint
4. task-specific data, output, evidence, or method documentation
5. current runtime/repository state when execution depends on it

Continue from durable state rather than reconstructing the project from old chat transcripts.

The repository and its documented external resources must remain sufficient for human-only or degraded-tool operation; no required continuation state may exist only in a chat, agent memory, or tool-specific service.

### End a material session

Record only what changed materially:

- what was established
- what changed
- what was validated
- what remains uncertain
- what decision was made
- the next action
- the next authorization boundary

Update `STATUS.md`, a GitHub issue, or a decision record only when that location owns the fact. Avoid duplicate status systems.

## Browser and desktop continuation

Browser or desktop ChatGPT may continue high-value non-executing work such as:

- research and literature synthesis
- architecture and experiment planning
- requirements refinement
- scientific interpretation
- validation planning
- data-schema design
- comparison matrices
- documentation and implementation specification

When local execution is required, produce an implementation-ready packet containing the objective, allowed scope, non-goals, acceptance criteria, relevant tests, risks, and authorization boundaries.

Do not require the local coding agent to reread an entire exploratory chat.

## Task routing and agent capacity

Use the least expensive and least privileged mechanism capable of completing the task correctly.

- ChatGPT or the reasoning director: scientific reasoning; research and literature synthesis; objective and hypothesis refinement; experiment or analysis design; task specification; and cross-project or system reasoning where applicable
- Codex: exact local repository, runtime, code, or schema inspection when needed; bounded implementation; and authorized local execution; it does not approve its own consequential candidate
- deterministic mechanisms: Git state, tests, hashes, schemas, manifests, numerical reproduction, and other mechanical pass/fail evidence
- Claude Code or another independent reviewer: independent semantic, scientific, architectural, or security challenge when useful; while serving as reviewer it is read-only by default and does not modify the candidate unless explicitly reassigned in a later implementation cycle
- human or project lead: scientific judgment, ambiguity resolution where evidence cannot decide, consequential authorization, candidate acceptance or rejection, and external-write, publication, and release boundaries

For planning, ChatGPT reasoning is normally sufficient for scientific framing and analysis or task design. Add Codex read-only inspection when exact repository, runtime, code, or schema state materially affects the plan. Add a read-only independent plan critique only when that challenge materially improves confidence. Do not invoke ChatGPT, Codex, and Claude mechanically as planning or review ceremony.

Do not consume strong-agent capacity merely because it is available. Preserve capacity for revisions, pivots, hard debugging, deadlines, and consequential review.

## Triggered project records and lineage

Keep base project state lean. At trivial E-rigor exploration, do not require decision, analysis, or experiment records merely because templates exist. Escalate only when a workflow trigger appears:

- when material durable rationale appears, use a decision record such as `DECISIONS.md` or an existing project-owned record
- when scientific, inferential, or comparative analysis becomes material, use `ANALYSIS_EXPERIMENT_TEMPLATE.md` as a starting contract and instantiate `ANALYSIS_PLAN.md` or an equivalent project-owned record only when useful
- when multiple experiments or trials become ambiguous, use lightweight experiment records or an `experiments/` directory with stable IDs when identity helps

Maintain enough lineage for consequential work to connect the question to the analysis or experiment plan, code/configuration/data identity, run, output or manifest, result, decision, and supported claim or next experiment. Prefer a generated run manifest as the owner of mechanical identifiers rather than manually duplicating hashes. Neither an experiment ID nor a separate Git branch is required for trivial work or for every experiment.

## External branch reconciliation

If a branch or commit was created or updated externally and local execution will continue:

1. verify that local state is clean or otherwise interpretable
2. fetch the authoritative remote
3. switch to or track the intended branch
4. verify the expected commit SHA
5. only then continue local execution

## Change and output discipline

Keep exploratory work fast, but do not silently promote state:

- observation -> supported finding
- verified implementation -> scientifically validated method
- scratch/candidate output -> manuscript or release output

Promotion requires evidence appropriate to the rigor level.

For consequential outputs, prefer generated provenance such as Git commit, input identifiers, configuration, environment, timestamps, hashes, and run manifests rather than manually maintained mechanical bookkeeping.

## Authorization boundaries

The following require explicit review/authorization appropriate to project risk and must not be inferred from a general implementation request:

- dependency or environment changes with broader impact
- MCP servers, plugins, hooks, daemons, or orchestration integrations
- credential or secret handling
- external uploads or publication
- network/TLS/security-policy exceptions
- destructive filesystem or data operations
- privileged host changes
- commit, push, pull-request creation, merge, release, or archive publication when those actions have not been separately authorized

Agents do not approve their own consequential changes.

## Governed learning

When a recurring problem appears, prefer the strongest low-overhead prevention mechanism:

1. deterministic test, schema, lint, or gate
2. tool or configuration rule
3. reusable Skill for a stable procedure
4. `AGENTS.md` only for durable project invariants
5. agent memory only as convenience context

Do not turn every historical mistake into a permanent prompt rule.

For material work, record execution feedback when it would help prevent repeated rework. A normal task return, issue, or existing project record may capture, as useful: `avoidable_rework`, `observed_friction`, `root_cause`, `candidate_prevention`, `estimated_benefit`, `complexity_cost`, `scope` (`project | template | RSE | WSL | none`), `repeat_evidence`, and `recommendation` (`ignore | observe | project-local | promote`). Do not create a mandatory feedback file.

Prefer prevention in this order: deterministic check, schema, or gate; tool or configuration fix; reusable procedure or template; durable instruction; memory or conversation convenience. One incident does not automatically justify a permanent global rule.

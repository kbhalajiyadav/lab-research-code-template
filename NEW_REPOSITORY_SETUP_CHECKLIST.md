# New Repository Setup Checklist

Use this checklist when creating a new lab repository from this template.

Start lean. Add stronger reproducibility, validation, governance, citation, and release controls as project consequence and maturity increase.

## 1. Establish the project contract

- [ ] Create the new repository using `Use this template`.
- [ ] Replace `Project Title` and placeholder repository URLs in `README.md`.
- [ ] Complete `PROJECT.md` with the North Star, research question, scope/non-goals, expected deliverables, success criteria, canonical locations, confidentiality, collaborators/constraints, and intended environment authority.
- [ ] Complete `STATUS.md` with the current phase, status, rigor level, blocker, open questions, next action, next deliverable, deadline, and next authorization boundary.
- [ ] Confirm repository visibility and data/IP handling with the PI or project lead.

## 2. Choose the initial rigor level

Select the lowest level sufficient for the current consequence:

- [ ] **E — Exploratory:** fast hypothesis/workflow exploration
- [ ] **R — Reproducible:** stable environment, inputs/outputs, tests, and representative reruns
- [ ] **V — Validated:** scientific validation, comparison, replication/robustness, and provenance
- [ ] **P — Publication/Release:** exact lineage, promoted outputs, archive/release evidence, and independent review where warranted

See `RESEARCH_WORKFLOW.md` for promotion triggers. Do not impose publication-grade process on early exploration.

## 3. Define canonical locations

- [ ] Code repository location is defined, normally `~/src/<project>` for the WSL workflow.
- [ ] Durable project data location is defined, normally `~/data/<project>` or approved institutional/archive storage.
- [ ] Scratch location is defined, normally `~/scratch/<project>`.
- [ ] Working manuscript/meeting/collaboration location is linked when relevant.
- [ ] Nothing indispensable exists only in scratch.
- [ ] Anything outside Git required for reproducibility can be identified from repository documentation or metadata.

## 4. Establish one authoritative environment mechanism

The default Python authority in this template is `pyproject.toml` + committed `uv.lock`, with `.python-version` selecting the default interpreter.

- [ ] Confirm that the default uv workflow is appropriate for this project, or document a justified alternative in `PROJECT.md`.
- [ ] Replace placeholder project metadata and remove dependencies the project does not need.
- [ ] Add or remove dependencies with `uv add`, `uv add --dev`, or `uv remove` rather than hand-editing a second dependency source.
- [ ] Run `uv lock` after changing project metadata, Python support, dependency declarations, or dependency groups.
- [ ] Run `uv lock --check` to verify that the committed lockfile matches `pyproject.toml`.
- [ ] At R rigor or above, run `uv sync --locked` from a clean project environment and verify the representative workflow.
- [ ] Commit `uv.lock`; do not treat a generated `requirements.txt` export as the project authority.

If Conda, a container, an HPC module stack, or another mechanism is required, replace the default authority deliberately and update `PROJECT.md` and user-facing setup instructions in the same reviewed change. Do not maintain competing hand-edited dependency definitions.

Do not perform global/shared environment changes solely for one project unless explicitly approved.

## 5. Configure agent guidance only when used

- [ ] Keep `AGENTS.md` if coding/research agents will operate in the repository; otherwise remove it if unnecessary.
- [ ] Keep `CLAUDE.md` only when Claude Code is part of the project workflow.
- [ ] Keep agent instructions concise; put repeatable procedures in workflow documents or reviewed Skills rather than expanding the root instruction file.
- [ ] Do not add MCP servers, plugins, hooks, daemons, or orchestration integrations without explicit trust review and authorization.

## 6. Add project content

- [ ] Add notebooks to `notebooks/` when interactive analysis is useful.
- [ ] Add reusable scripts to `scripts/` when workflow steps should run outside notebooks.
- [ ] Add reusable modules to `src/` when stable logic emerges.
- [ ] Add tests for stable/reproducibility-sensitive logic.
- [ ] Add small example, synthetic, or representative inputs when appropriate.
- [ ] Document data organization in `data/README.md`.
- [ ] Document generated results in `results/README.md`.
- [ ] Expand `docs/output_dictionary.md` when outputs/metrics become consequential.

## 7. Repository settings

Check these settings for important project repositories:

- [ ] Default branch is `main`.
- [ ] Squash merging is enabled.
- [ ] Merge commits are disabled.
- [ ] Rebase merging is disabled unless intentionally needed.
- [ ] Automatically delete head branches is enabled.
- [ ] GitHub Pages is disabled unless documentation hosting is needed.
- [ ] Deploy keys are empty unless intentionally needed.
- [ ] Secrets and variables are empty unless intentionally needed.

## 8. Branch and tag protection

For manuscript-linked, public, validated, or otherwise consequential repositories:

- [ ] Protect the default branch.
- [ ] Require pull requests before merging.
- [ ] Require at least one approval, if a reviewer is available.
- [ ] Dismiss stale pull request approvals when new commits are pushed.
- [ ] Require conversation resolution before merging.
- [ ] Block force pushes.
- [ ] Restrict branch deletion.
- [ ] Keep required status checks off until a real CI workflow exists.
- [ ] Enable required status checks only after a working workflow is added.

For private repositories in a free organization account:

- [ ] Confirm whether rulesets are enforced.
- [ ] If rulesets are not enforced, create a classic branch protection rule for `main`.
- [ ] If Code Owners review is unavailable, require at least one normal approval instead.

For released software, manuscript-linked workflows, or DOI-archived repositories:

- [ ] Protect release tags matching `v*`.
- [ ] Restrict tag updates.
- [ ] Restrict tag deletion.

## 9. Security and automation

- [ ] Dependency graph is enabled.
- [ ] Dependabot alerts are enabled.
- [ ] Dependabot security updates are enabled, if appropriate.
- [ ] Dependabot version updates are reviewed before enabling.
- [ ] Secret scanning and push protection are enabled if available.
- [ ] Workflow permissions are read-only by default.
- [ ] External contributor workflow approval is required.

## 10. Add maturity-specific records only when needed

Base project state should remain lean:

- [ ] Maintain `README.md`, `PROJECT.md`, and `STATUS.md`; retain `AGENTS.md` only when agents operate in the repository.
- [ ] Establish the environment, durable-data, and disposable-scratch boundaries described above.

Add records when their workflow trigger appears, not automatically at repository creation:

- [ ] `docs/output_dictionary.md` for defined outputs, columns, metrics, and units.
- [ ] Durable material rationale: use a decision record or an existing project-owned record.
- [ ] Material scientific, inferential, or comparative analysis: start from `ANALYSIS_EXPERIMENT_TEMPLATE.md` and create an `ANALYSIS_PLAN.md` or equivalent only when useful.
- [ ] Multiple trials whose identity becomes ambiguous: use lightweight experiment records with stable IDs.
- [ ] A reproducible accepted run: preserve stable run/output identity and manifest linkage.
- [ ] A validated or consequential claim: preserve appropriate validation, robustness, comparison, or replication evidence.
- [ ] Publication or release: freeze traceable code, data, environment, and output lineage.
- [ ] representative/synthetic test data and expected outputs.
- [ ] `ROADMAP.md` for medium/long-term direction or explicitly deferred work.

- [ ] Before continuing local execution on a branch or commit created or updated externally, complete the reconciliation sequence in `RESEARCH_WORKFLOW.md` and verify the expected SHA.

Do not create empty records solely because the template offers them.

## 11. Before public release

- [ ] Complete `RELEASE_CHECKLIST.md`.
- [ ] Update `CITATION.cff`.
- [ ] Confirm `MAINTAINERS.md`.
- [ ] Confirm data availability statement.
- [ ] Confirm DOI/archive plan.
- [ ] Confirm license.
- [ ] Confirm PI/project-lead approval.
- [ ] Confirm exact code, data, environment, validation, and promoted-output lineage.
- [ ] Create a versioned GitHub Release if needed.
- [ ] Archive release in Zenodo or another approved repository if needed.

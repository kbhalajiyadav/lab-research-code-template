# Project Title

Short description of the research code, analysis workflow, or computational tool.

Replace this title and description before public release, manuscript submission, or DOI archiving.

## Start here

Use these files in order when orienting to a project:

1. `PROJECT.md` — what the project is, why it exists, and its durable constraints
2. `STATUS.md` — where the project is now and what should happen next
3. `RESEARCH_WORKFLOW.md` — how rigor, continuity, storage, validation, and agent-assisted work are handled
4. this README and `docs/user_guide.md` — how to run the project workflow

A fresh human or agent session should resume from durable project state rather than replaying old chat transcripts.

## Purpose

This repository contains reproducible research code and documentation for lab research projects, including:

- data processing
- analysis workflows
- figure and table generation
- notebook-based methods
- reusable scripts or Python modules
- validation or quality-control checks

Replace this section with a project-specific description before public release or manuscript submission.

## Progressive rigor

Use the lowest rigor level appropriate to the consequence of the work:

- **E — Exploratory:** fast hypothesis and workflow exploration
- **R — Reproducible:** stable environment, inputs/outputs, tests, and representative reruns
- **V — Validated:** scientific validation, comparison, replication/robustness, and provenance
- **P — Publication/Release:** exact code/data/environment lineage, promoted outputs, archive/release evidence, and independent review where warranted

See `RESEARCH_WORKFLOW.md` for promotion triggers and the distinction between software verification and scientific validation.

## Repository structure

```text
.
├── .github/
│   ├── CODEOWNERS
│   ├── dependabot.yml
│   ├── pull_request_template.md
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.yml
│   │   ├── config.yml
│   │   └── documentation_update.yml
│   └── workflows/
│       └── README.md
├── data/
│   └── README.md
├── docs/
│   ├── README.md
│   ├── user_guide.md
│   └── output_dictionary.md
├── examples/
│   └── README.md
├── notebooks/
│   └── README.md
├── results/
│   └── README.md
├── scripts/
│   └── README.md
├── src/
│   └── README.md
├── tests/
│   └── README.md
├── AGENTS.md
├── ANALYSIS_EXPERIMENT_TEMPLATE.md
├── CLAUDE.md
├── PROJECT.md
├── STATUS.md
├── RESEARCH_WORKFLOW.md
├── README.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── CITATION.cff
├── CODE_OF_CONDUCT.md
├── DATA_AVAILABILITY_TEMPLATE.md
├── GOVERNANCE.md
├── LICENSE_NOTICE.md
├── MAINTAINERS.md
├── NEW_REPOSITORY_SETUP_CHECKLIST.md
├── RELEASE_CHECKLIST.md
├── ROADMAP.md
├── SECURITY.md
├── .python-version
├── pyproject.toml
└── uv.lock
```

Not every generated project must retain every optional template artifact forever. Use `NEW_REPOSITORY_SETUP_CHECKLIST.md` to select what is justified by project maturity and release needs.

`ANALYSIS_EXPERIMENT_TEMPLATE.md` is an optional, triggered starting contract for material scientific, inferential, comparative, or consequential analysis. Projects need not fill or retain it for trivial exploration.

## Getting started

Clone the repository:

```bash
git clone https://github.com/VCU-Soft-Functional-Materials-Lab/REPOSITORY-NAME.git
cd REPOSITORY-NAME
```

For ordinary Python research projects, the template default is:

- `pyproject.toml` — direct project dependencies and development tooling
- `uv.lock` — exact resolved dependency set; commit it to Git
- `.python-version` — default Python interpreter for the project

Create or synchronize the project environment from the committed lockfile:

```bash
uv sync --locked
```

Run project commands through the managed environment:

```bash
uv run --locked python scripts/run_analysis.py
uv run --locked jupyter lab
uv run --locked pytest
```

Use `uv add`, `uv add --dev`, and the corresponding `uv remove` command to change dependencies so `pyproject.toml` and `uv.lock` remain aligned.

If a project genuinely requires Conda, a container, an HPC module stack, or another environment mechanism, document that alternative as the authority in `PROJECT.md` and replace the default authority deliberately. Do not maintain `requirements.txt`, `environment.yml`, or another hand-edited dependency file as a parallel source of truth.

If an external tool requires `requirements.txt`, generate it from the authoritative uv project rather than maintaining it independently.

For notebook-based projects, place notebooks in `notebooks/`.

For reusable scripts, place command-line or helper scripts in `scripts/`.

For reusable Python modules, place package code in `src/`.

For tests or verification checks, use `tests/`.

## Development and data placement

For the standard WSL workflow, use:

```text
~/src/<project>       canonical Git working tree
~/data/<project>      durable project data
~/scratch/<project>   temporary/disposable working data
```

Nothing indispensable should exist only in scratch. Anything outside Git required to reproduce accepted work should be identifiable from the repository.

See `RESEARCH_WORKFLOW.md` for the full placement and continuity rules.

## Reproducibility

Before using this repository for a manuscript, poster, thesis, report, public release, or DOI archive, document as applicable:

- input data sources and identifiers
- exact software commit or release
- the authoritative environment/dependency definition
- analysis settings or configuration
- expected and promoted outputs
- validation evidence and scope
- release tag
- DOI/archive link, if applicable

For the default uv workflow, verify that `uv.lock` is current with:

```bash
uv lock --check
```

Use `RELEASE_CHECKLIST.md` before creating a public release or archive.

Use `NEW_REPOSITORY_SETUP_CHECKLIST.md` when creating a new project repository from this template.

## Data availability

Large raw data files should generally not be stored directly in this repository.

Use an approved archive such as Zenodo, OSF, institutional storage, or another PI-approved repository.

Add project-specific data availability information here before public release or manuscript submission.

## Citation

If this repository supports a publication, cite the associated paper and archived software release.

Update `CITATION.cff` before public release or DOI archiving.

## License

Add a formal license only after confirming the lab/project policy with the PI or project lead.

Until a formal license is selected, see `LICENSE_NOTICE.md`.

## Governance and contribution

Project governance expectations are described in `GOVERNANCE.md`.

Maintainer information should be updated in `MAINTAINERS.md`.

Contribution expectations are described in `CONTRIBUTING.md`.

Security reporting expectations are described in `SECURITY.md`.

## Contact

Maintained by the VCU Soft Functional Materials Lab.

Update this section with project-specific contact information before public release.

# User Guide

This guide should be updated for each project that uses this template.

## Overview

Briefly describe what the workflow does, what inputs it requires, and what outputs it produces.

## Prerequisites

Before running the workflow, confirm that you have:

- access to the repository
- the required input data
- `uv` available for the default Python workflow, or the explicitly documented project environment tool
- the committed authoritative environment files
- permission to use any project-specific data

## Installation

Clone the repository:

```bash
git clone https://github.com/VCU-Soft-Functional-Materials-Lab/REPOSITORY-NAME.git
cd REPOSITORY-NAME
```

For the default environment authority, create or synchronize the environment from `pyproject.toml` and `uv.lock`:

```bash
uv sync --locked
```

Run commands through the project environment:

```bash
uv run --locked python scripts/run_analysis.py --input data/raw/example.csv --output results/
uv run --locked jupyter lab
uv run --locked pytest
```

The default Python version is recorded in `.python-version`. `pyproject.toml` declares direct and development dependencies, while `uv.lock` records the exact resolved environment and should remain under version control.

If the project documents Conda, a container, an HPC module stack, or another mechanism as its environment authority, replace this installation section with that project-specific procedure. Do not maintain multiple hand-edited dependency definitions as competing sources of truth.

## Input data

Describe the expected input files here.

Include:

- file names
- file formats
- required columns or sheets
- units
- expected folder locations
- any preprocessing assumptions

Example:

```text
data/
├── raw/
├── processed/
└── metadata/
```

## Running the workflow

Add project-specific instructions here.

Example:

```bash
uv run --locked python scripts/run_analysis.py --input data/raw/example.csv --output results/
```

For notebook-based workflows, describe the notebook order and any required user inputs.

Example:

```text
1. Open notebooks/01_setup.ipynb
2. Confirm input paths
3. Run all cells
4. Review quality-control outputs
5. Run notebooks/02_analysis.ipynb
```

## Outputs

Describe the expected outputs.

Include:

- processed data files
- figures
- tables
- logs
- quality-control reports
- manuscript-ready exports, if applicable

## Quality-control checks

Before using outputs for a report, poster, thesis, or manuscript, verify:

- input files were loaded correctly
- units are correct
- analysis settings match the intended method
- output files were generated successfully
- plots and tables are visually inspected
- warnings or excluded data are documented

## Reproducibility notes

Before public release, document:

- software version and exact Git commit or release tag
- authoritative environment mechanism
- Python version
- committed dependency lock or equivalent environment record
- input data source
- DOI/archive link, if available
- analysis settings used for reported results

For the default uv workflow, confirm the lockfile is current:

```bash
uv lock --check
```

## Troubleshooting

Add project-specific troubleshooting notes here.

Common items to document:

- missing dependency errors
- incorrect file paths
- unexpected column names
- notebook kernel issues
- environment installation or lockfile problems

## Contact

For project-specific questions, contact the repository maintainer or project lead.

# Notebooks

This folder is reserved for Jupyter notebooks used in project setup, analysis, visualization, quality control, or demonstration workflows.

## Notebook policy

Use notebooks for exploratory analysis, interactive review, tutorials, and reproducible workflow demonstrations.

For manuscript-linked repositories, notebooks should be clear enough that another lab member can understand:

- required inputs
- analysis settings
- processing steps
- generated outputs
- quality-control checks
- known limitations

## Recommended naming

Use numbered notebook names when execution order matters.

Examples:

```text
notebooks/
├── README.md
├── 01_setup_and_inputs.ipynb
├── 02_analysis.ipynb
├── 03_figures_and_tables.ipynb
└── 04_quality_control.ipynb
```

## Reproducibility checklist

Before public release, check that notebooks:

- run from a clean kernel
- use relative paths where possible
- do not contain personal file paths
- do not expose credentials, tokens, or private information
- document required user inputs
- save outputs to documented folders
- match the project README and user guide

## Large outputs

Avoid committing large generated notebook outputs unless they are necessary for review. When appropriate, clear unnecessary outputs before committing.

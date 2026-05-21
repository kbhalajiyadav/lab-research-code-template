# Scripts

This folder is reserved for command-line or reusable Python scripts used by the project.

## Purpose

Use scripts for analysis steps that should be reusable, testable, and easier to run outside a notebook.

Examples:

```text
scripts/
├── README.md
├── run_analysis.py
├── generate_figures.py
└── export_tables.py
```

## Recommended practice

Scripts should:

- use clear input and output paths
- avoid hard-coded personal file paths
- include helpful comments
- fail with clear error messages
- write outputs to documented folders
- be referenced in the user guide

## Example command

```bash
python scripts/run_analysis.py --input data/raw/example.csv --output results/
```

## Reproducibility checklist

Before public release, confirm that scripts:

- run from the repository root
- use relative paths where possible
- match dependency files
- generate documented outputs
- do not require private credentials
- are consistent with notebooks and documentation

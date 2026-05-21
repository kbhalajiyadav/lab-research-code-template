# Tests

This folder is reserved for lightweight tests that verify project code, data-loading logic, analysis functions, or workflow behavior.

## Purpose

Tests help confirm that important project functions continue to work after changes.

For research-code repositories, tests can be simple. They should focus on the parts most likely to affect reproducibility.

## Recommended structure

```text
tests/
├── README.md
├── test_io.py
├── test_preprocessing.py
└── test_analysis.py
```

## What to test

Consider adding tests for:

- file loading
- required column checks
- unit conversions
- metric calculations
- data filtering logic
- output file creation
- small example workflows

## Running tests

If the project uses `pytest`, tests can usually be run from the repository root:

```bash
pytest
```

## Reproducibility checklist

Before public release, confirm that tests or manual checks cover the workflow components most relevant to reported results.

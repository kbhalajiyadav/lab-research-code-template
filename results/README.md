# Results

This folder is reserved for generated outputs from project workflows.

## Results policy

Generated outputs should be committed only when they are necessary for review, documentation, manuscript preparation, or reproducibility.

Avoid committing large, temporary, or easily regenerated files unless the project lead has approved it.

## Recommended structure

```text
results/
├── README.md
├── processed_data/
├── figures/
├── tables/
├── logs/
└── quality_control/
```

## Recommended practice

Document which script or notebook generated each result.

For manuscript-linked repositories, record:

- input data source
- analysis settings
- software version
- dependency versions
- output generation date
- release tag
- DOI/archive link, if applicable

## What may be included

Depending on the project, this folder may include:

- processed data tables
- summary statistics
- manuscript-ready figures
- exported tables
- quality-control plots
- analysis logs
- small expected-output examples

## What should usually be excluded

Avoid committing:

- very large generated files
- temporary scratch outputs
- personal working copies
- duplicate exports
- outputs generated from private data without approval
- files that can be regenerated and are not needed for review

## Reproducibility checklist

Before public release, verify that:

- results can be regenerated from documented inputs
- file names match documentation
- units and metrics are defined
- figures and tables are traceable to scripts/notebooks
- excluded files are documented if relevant
- outputs used in manuscripts or reports match the archived release

# Data

This folder is reserved for project-specific data organization notes.

## Data policy

Do not commit sensitive, restricted, proprietary, human-subject, unpublished, or very large raw data unless the PI or project lead has explicitly approved it.

For manuscript-linked repositories, primary datasets should usually be archived separately using Zenodo, OSF, institutional storage, or another approved data repository.

## Recommended structure

```text
data/
├── README.md
├── raw/
├── processed/
└── metadata/
```

## What may be included

Small example or synthetic datasets may be included when they are useful for demonstrating the workflow.

Examples:

- toy datasets
- synthetic input files
- public-domain demonstration files
- small metadata tables

## What should usually be excluded

Avoid committing:

- large raw instrument files
- private or restricted datasets
- unpublished collaborator data without permission
- credentials, tokens, or identifying information
- generated outputs that can be recreated from scripts

## Documentation checklist

For each dataset used by the project, document:

- file name
- source
- date collected or downloaded
- owner or responsible person
- format
- units
- required columns or sheets
- preprocessing steps
- access restrictions
- archive DOI or storage location, if applicable

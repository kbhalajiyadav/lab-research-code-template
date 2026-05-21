# Contributing

This document provides a simple contribution workflow for lab research-code repositories.

## General workflow

Use branches and pull requests for project changes whenever the repository is active, public, manuscript-linked, or shared with collaborators.

Recommended workflow:

1. Create a new branch from `main`.
2. Make one focused change.
3. Test or inspect the output.
4. Open a pull request.
5. Request review from a maintainer.
6. Squash merge after review.

## Branch naming

Use short, descriptive branch names.

Examples:

```text
fix-readme-links
add-example-data-loader
update-analysis-settings
docs-output-dictionary
```

Avoid vague names such as:

```text
changes
update
final
new-version
```

## Commit messages

Use clear commit messages that describe the change.

Examples:

```text
Add output dictionary template
Update environment file
Fix Binder setup instructions
Add example notebook placeholder
```

## Pull requests

Each pull request should include:

- a short summary of the change
- why the change was needed
- whether outputs, figures, or results changed
- any files or settings that require special attention

For manuscript-linked repositories, state explicitly whether the change affects:

- analysis settings
- input data
- processed outputs
- figure or table generation
- dependency versions
- release or DOI documentation

## Data handling

Do not commit sensitive, restricted, unpublished, or very large raw data unless the PI or project lead has approved it.

Large data files should usually be stored in an approved archive or storage location, such as Zenodo, OSF, institutional storage, or another PI-approved repository.

## Reproducibility checks

Before merging a change, check that:

- the repository still runs as documented
- dependency files are updated if needed
- output folders or generated files are not accidentally committed
- project-specific instructions are clear
- README and changelog entries are updated when appropriate

## Review expectations

Maintainers should check whether the change is scientifically and computationally consistent with the project goals.

For manuscript-linked repositories, maintainers should also verify that the change does not silently alter published or submitted analysis results.

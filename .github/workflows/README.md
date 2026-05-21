# GitHub Actions Workflows

This folder is reserved for GitHub Actions workflow files.

## Purpose

Use workflows for lightweight automated checks such as:

- confirming that Python dependencies install
- running tests
- checking notebook execution
- validating documentation links
- building documentation
- preparing release checks

## Recommended practice

For manuscript-linked repositories, workflows should support reproducibility without silently changing files or outputs.

Recommended defaults:

- use read-only workflow permissions unless write access is necessary
- avoid storing credentials unless absolutely required
- do not expose secrets in logs
- require maintainer approval for workflows from external contributors
- keep workflow files simple and documented

## Example workflow names

```text
.github/workflows/
├── README.md
├── python-smoke-test.yml
├── run-tests.yml
└── docs-check.yml
```

## Notes

This template does not include an active workflow by default. Add project-specific workflows only when they are needed and tested.

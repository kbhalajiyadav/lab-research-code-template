---
project_id: replace-me
project_profile: computational-research
confidentiality: internal
---

# Project Contract

Use this file for stable or slowly changing project identity. Keep current execution state in `STATUS.md`.

## North Star

State the durable scientific, engineering, or computational objective.

## Research question

State the specific question this project is intended to answer.

## Current hypothesis

State the present testable hypothesis. The hypothesis may change without changing the North Star.

## Why this matters

Summarize the scientific, engineering, translational, or operational significance.

## Scope

### In scope

- Replace with project-specific scope.

### Explicit non-goals

- Replace with work that is intentionally outside this project.

## Expected deliverables

List the intended outputs, such as:

- manuscript or thesis material
- analysis workflow
- reusable software
- dataset or archive
- figures or tables
- poster, report, or proposal

## Success criteria

State the evidence or result that would constitute meaningful success.

## Canonical locations

| Resource | Canonical location | Notes |
| --- | --- | --- |
| Code | GitHub and `~/src/<project>` | Version-controlled source authority |
| Durable data | `~/data/<project>` or approved archive/storage | Do not duplicate large or restricted raw data into Git |
| Scratch | `~/scratch/<project>` | Temporary and non-authoritative |
| Working documents | Drive / Obsidian / approved collaboration space | Manuscripts, meeting notes, and working material |
| Work items and material decisions | GitHub issues / project records | Link rather than duplicate current state |

Nothing indispensable may exist only in scratch. Anything outside Git required to reproduce accepted work must be identifiable from the repository.

## People and responsibilities

| Person or group | Role | Responsibility |
| --- | --- | --- |
| Replace me | Project lead | Replace with project-specific responsibility |

## Major constraints

Document material constraints such as:

- deadlines
- instrument or facility availability
- collaborator dependencies
- compute requirements
- restricted or confidential data
- intellectual-property limits
- regulatory or institutional requirements

## Environment authority

Choose and document one authoritative environment mechanism for this project.

Examples include a project-local `pyproject.toml` plus lock file, an explicitly managed shared environment, a container, or a documented HPC environment.

Do not leave multiple environment definitions competing as the project authority.

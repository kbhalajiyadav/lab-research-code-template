# Source Code

This folder is reserved for reusable project code, functions, modules, or package-style utilities.

## Purpose

Use this folder when a project grows beyond notebooks or standalone scripts and needs reusable functions.

Examples:

```text
src/
├── README.md
└── project_package/
    ├── __init__.py
    ├── io.py
    ├── preprocessing.py
    ├── analysis.py
    ├── plotting.py
    └── export.py
```

## Recommended practice

Code in this folder should:

- use clear function names
- avoid hard-coded personal file paths
- separate input/output from analysis logic
- include comments where the logic is not obvious
- be reusable from notebooks and scripts
- be documented in the user guide when used in the workflow

## Import pattern

If the project becomes package-like, document how users should import functions.

Example:

```python
from project_package.analysis import run_analysis
```

## Reproducibility checklist

Before public release, confirm that source code:

- matches the documented workflow
- produces the expected outputs
- uses version-controlled settings
- does not depend on local-only files
- does not expose private credentials or restricted data

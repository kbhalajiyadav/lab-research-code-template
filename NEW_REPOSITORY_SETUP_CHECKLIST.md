# New Repository Setup Checklist

Use this checklist when creating a new lab repository from this template.

## 1. Create the repository

- [ ] Create the new repository using `Use this template`.
- [ ] Replace `Project Title` in `README.md`.
- [ ] Replace placeholder repository URLs.
- [ ] Update project description.
- [ ] Confirm repository visibility with the PI or project lead.

## 2. Update project metadata

- [ ] Update `CITATION.cff`.
- [ ] Update `MAINTAINERS.md`.
- [ ] Update `ROADMAP.md`.
- [ ] Decide whether to add a formal `LICENSE`.
- [ ] Remove `LICENSE_NOTICE.md` if a formal license is added.

## 3. Update environment files

- [ ] Rename the Conda environment in `environment.yml`.
- [ ] Add project-specific packages to `requirements.txt`.
- [ ] Add project-specific packages to `environment.yml`.
- [ ] Remove unused placeholder dependencies if needed.
- [ ] Test environment creation from a clean setup.

## 4. Add project content

- [ ] Add notebooks to `notebooks/`.
- [ ] Add reusable scripts to `scripts/`.
- [ ] Add reusable modules to `src/`, if needed.
- [ ] Add small example inputs to `examples/`, if appropriate.
- [ ] Document data organization in `data/README.md`.
- [ ] Document outputs in `docs/output_dictionary.md`.

## 5. Repository settings

Check these settings for important project repositories:

- [ ] Default branch is `main`.
- [ ] Squash merging is enabled.
- [ ] Merge commits are disabled.
- [ ] Rebase merging is disabled unless intentionally needed.
- [ ] Automatically delete head branches is enabled.
- [ ] GitHub Pages is disabled unless documentation hosting is needed.
- [ ] Deploy keys are empty unless intentionally needed.
- [ ] Secrets and variables are empty unless intentionally needed.

## 6. Branch and tag protection

For manuscript-linked, public, or important project repositories:

- [ ] Protect the default branch.
- [ ] Require pull requests before merging.
- [ ] Require at least one approval, if a reviewer is available.
- [ ] Dismiss stale pull request approvals when new commits are pushed.
- [ ] Require conversation resolution before merging.
- [ ] Block force pushes.
- [ ] Restrict branch deletion.
- [ ] Keep required status checks off until a real CI workflow exists.
- [ ] Enable required status checks only after a working workflow is added.

For private repositories in a free organization account:

- [ ] Confirm whether rulesets are enforced.
- [ ] If rulesets are not enforced, create a classic branch protection rule for `main`.
- [ ] If Code Owners review is unavailable, require at least one normal approval instead.

For released software, manuscript-linked workflows, or DOI-archived repositories:

- [ ] Protect release tags matching `v*`.
- [ ] Restrict tag updates.
- [ ] Restrict tag deletion.

## 7. Security and automation

- [ ] Dependency graph is enabled.
- [ ] Dependabot alerts are enabled.
- [ ] Dependabot security updates are enabled, if appropriate.
- [ ] Dependabot version updates are reviewed before enabling.
- [ ] Secret scanning and push protection are enabled if available.
- [ ] Workflow permissions are read-only by default.
- [ ] External contributor workflow approval is required.

## 8. Before public release

- [ ] Complete `RELEASE_CHECKLIST.md`.
- [ ] Confirm data availability statement.
- [ ] Confirm DOI/archive plan.
- [ ] Confirm license.
- [ ] Confirm PI/project-lead approval.
- [ ] Create a versioned GitHub Release if needed.
- [ ] Archive release in Zenodo or another approved repository if needed.

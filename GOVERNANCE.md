# Governance

## Roles

| Role | Who | Can |
|---|---|---|
| Maintainer | Org owners (`@engineering-mathematics/maintainers`) | Admin on org-level repos; final say on cross-team design; release approval |
| Team member | A team (Foundations, System Modelling, Infrastructure, Domain Frameworks, Reference Systems) | Write access to **its own** repos only |
| Contributor | Anyone | Fork, open issues and PRs |

Team repos have exclusive write access for their team. Everyone else contributes through forks and pull requests.

## Decisions

- Day-to-day changes: pull request, one CODEOWNER approval, green CI.
- Changes to a public API, dependency set or cross-package behaviour: PR plus approval from each affected team.
- Changes to architecture, naming, licensing, or the release process: an
  [RFC](https://github.com/engineering-mathematics/roadmap/tree/main/RFCs), accepted by the maintainers.
- While the project has a single maintainer, that maintainer's approval stands in for all of the above, but the
  written trail (issue/RFC/PR) is still required. It is what makes the project transferable.

## Mandatory repository settings

Applied to every repo (via org rulesets) before its first release:

- `main` is protected: no direct pushes, no force-push, no deletion; linear history; signed commits.
- Pull request required; CODEOWNER review required; stale approvals dismissed on new commits.
- Required status checks: every job of the reusable `python-ci` workflow, plus `security`.
- Secret scanning and push protection on; Dependabot alerts and security updates on; private vulnerability reporting on.
- Actions: workflows pinned by commit SHA; default `GITHUB_TOKEN` permissions read-only.
- A `pypi` environment with required reviewers; PyPI publishing only through Trusted Publishing (no long-lived tokens).

## Releases

SemVer. Tag `vX.Y.Z` → CI → build with SBOM and provenance → approval on the `pypi` environment → publish.
A release can be yanked but never silently replaced.

## Becoming a maintainer

Sustained, high-quality contributions across repos and demonstrated care for correctness. Nominated by an existing
maintainer, confirmed by the others.

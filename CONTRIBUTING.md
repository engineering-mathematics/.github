# Contributing

Thank you for helping build a mathematical foundation engineers can trust. This applies to every repository in the
organisation unless that repo says otherwise.

## Before you start

1. Read the [Vision](https://github.com/engineering-mathematics/roadmap/blob/main/Vision.md),
   [Architecture](https://github.com/engineering-mathematics/roadmap/blob/main/Architecture.md) and
   [Style Guide](https://github.com/engineering-mathematics/roadmap/blob/main/Style%20Guide.md).
2. For anything that changes a public API, a dependency, or cross-package behaviour, open an issue or an
   [RFC](https://github.com/engineering-mathematics/roadmap/tree/main/RFCs) first.
3. Check the repo's `CODEOWNERS`: those reviewers must approve your PR.

## Set up (any package repo)

```bash
git clone https://github.com/engineering-mathematics/<repo>.git && cd <repo>
uv sync                   # reproducible env from uv.lock
uvx pre-commit install    # same gates as CI, before every commit
```

## The gates your change must pass

```bash
uv run ruff check . && uv run ruff format --check .
uv run mypy
uv run lint-imports
uv run pytest             # warnings are errors; branch coverage >= 90%
```

CI additionally runs Python 3.11–3.13 on Linux, macOS and Windows, a lowest-supported-dependency run, a dependency
audit, CodeQL and a packaging check. A PR merges only when all of them are green.

## Expectations for a change

- **Tests with the change.** Bug fix → a test that failed before. New behaviour → unit tests, and a property-based or
  reference-solution test if there is an invariant or a known answer.
- **Numerics.** No explicit inversion or determinants (CI bans them). State tolerances. Keep column-major layout.
- **Units.** Physical quantities carry units; document them in docstrings.
- **No new runtime dependency without justification** in the PR description.
- **Docs and changelog.** Public changes update the docstring and `CHANGELOG.md` under *Unreleased*.
- **Small PRs.** One logical change; squash-merged; Conventional Commit title (`feat(solvers): ...`).

## Commits and signing

Conventional Commits. Commits must be signed (`git config commit.gpgsign true`); unsigned commits cannot merge.

## Reporting problems

- Bugs and features: use the issue templates.
- Security issues: **do not open a public issue.** See [SECURITY.md](SECURITY.md).

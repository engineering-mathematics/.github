<div align="center">

# ⚙️ Engineering Mathematics

**A rigorous, modular mathematical foundation for engineering software**

</div>

Small, independently versioned Python packages for the mathematics behind engineering systems: fast
(BLAS/LAPACK underneath, column-major), unit-aware, strictly typed, and verifiable, with a rich terminal experience.

> [!IMPORTANT]
> Pre-release. APIs may change until `1.0`. Nothing here is certified for safety-critical use.

## Packages

| Tier | What | Examples |
|---|---|---|
| 0 · Infrastructure | Shared runtime foundations | `core`, `units`, `viz` |
| 1 · Foundations | Core mathematics | `linear-systems`, `continuous-analysis`, `dynamical-systems`, `discrete-structures`, `stochastic-systems` |
| 2 · System Modelling | Models built on Foundations | `state-space`, `transfer-functions` |
| 3 · Domain Frameworks | Engineering domains | `control`, `robotics`, `cfd`, `fem` |
| 4 · Reference Systems | Worked applications | `ref-autopilot`, `ref-smart-grid` |

Install what you need, nothing more: `pip install engg-math-linear-systems` or `uv add engg-math-linear-systems`.
Import under one namespace: `from engg_math.linear_systems import ...`.
The optional `engg-math` CLI manages multi-package workspaces.

## Principles

Correctness · Reproducibility · Decoupling · Native speed · Unit safety · No silent failure.

Read the [Vision](https://github.com/engineering-mathematics/roadmap/blob/main/Vision.md),
[Architecture](https://github.com/engineering-mathematics/roadmap/blob/main/Architecture.md) and
[CONTRIBUTING](https://github.com/engineering-mathematics/.github/blob/main/CONTRIBUTING.md).

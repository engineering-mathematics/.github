# Security Policy

These libraries are meant to sit under safety- and mission-relevant software, so we treat numerical and supply-chain
defects as security-relevant.

## Reporting a vulnerability

**Do not open a public issue.** Use GitHub's private reporting on the affected repository:
*Security → Report a vulnerability*. If the repository does not show that option, open a private report on the
`.github` repository instead.

Please include the package and version, a minimal reproduction, and the impact you expect.

## What counts

- Memory-safety, injection, deserialisation or path-traversal issues (for example in file loaders).
- Supply-chain problems: compromised dependencies, build or release tampering.
- **Silent numerical failures** that return plausible but wrong results where we claim to detect them
  (missed singularity/ill-conditioning, unit mismatch not raised).

## Supported versions

While below `1.0`, only the latest minor release of each package receives fixes.

## Our commitments

- Acknowledge a report within 5 working days and give an assessment within 14.
- Fix, release and publish a GitHub Security Advisory; credit reporters who want it.

## Supply-chain posture

Locked dependencies; `pip-audit` and CodeQL in CI; GitHub Actions pinned by SHA; PyPI Trusted Publishing; every release
carries a CycloneDX SBOM and a signed build-provenance attestation.

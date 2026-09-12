# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- Added GitHub issue and pull request templates.
- Documented the Apache-2.0 license and copyright attribution in the README.

### Changed

- Restructured the root README to the family outline (purpose, why / what
  this is not, install, use, modules, related, contributing, license).
  The README documents marketplace-only consumer install (`okf@atlas`).
- Documented marketplace-first public GitHub consumer install (`okf@atlas`)
  and removed private-package `GITHUB_APM_PAT` / Contents: read requirements
  for public github.com sources.
- Pull request CI now reports **Release readiness decision**. When metadata,
  package integrity, and both consumer jobs succeed, that check records
  `release_readiness_decision=pr-validated` and does not require exact-main.

## [0.2.1] - 2026-09-04

### Added

- Added the root APM skill package for the Open Knowledge Format v0.2 standard,
  including authority, import, and export guidance.
- Added Apache-2.0 licensing and private APM installation documentation.

### Changed

- Separated the pure OKF format authority from operational process memory and
  directed live knowledge-store workflows to Atlas.
- Aligned package metadata and skill metadata on version 0.2.1.

### Fixed

- Removed obsolete wiki naming from the OKF export workflow.

[Unreleased]: https://github.com/sergio-sisternes-epam/okf/compare/v0.2.1...HEAD
[0.2.1]: https://github.com/sergio-sisternes-epam/okf/releases/tag/v0.2.1

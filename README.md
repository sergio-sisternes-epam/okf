# OKF

OKF provides the format rules and validator for portable Open Knowledge Format (OKF) v0.2 bundles.

## Why / what this is not

Use OKF to create, exchange, or validate Markdown bundles with YAML frontmatter against a shared format contract. It is the format authority, not a live knowledge store: ingestion, querying, and process memory belong to Atlas.

## Modules

| Module | What you get |
| --- | --- |
| `okf-authority` | Normative rules for frontmatter, reserved files, and conformance. |
| `okf-export` | Procedures for producing a portable OKF bundle. |
| `okf-import` | Procedures for materialising an external OKF bundle. |

Detailed procedures are in `references/modules/`; the runtime contract is in [`SKILL.md`](SKILL.md).

## Install

Requires APM CLI 0.29.0 or newer.

```bash
apm marketplace add sergio-sisternes-epam/atlas-marketplace --name atlas
apm install okf@atlas
```

## Use

Ask an agent to apply the OKF skill to the bundle or content at hand:

- `Validate this directory as an OKF v0.2 bundle.`
- `Export these Markdown pages as a portable OKF v0.2 bundle.`
- `Import this external OKF bundle into the target directory.`

## Prerequisites

Install the APM CLI (version 0.29.0 or newer). Atlas is not required for format and validation work.

## Related

- [Atlas marketplace](https://github.com/sergio-sisternes-epam/atlas-marketplace) — publishes `okf`.
- [okf-atlas](https://github.com/sergio-sisternes-epam/okf-atlas) — companion store for live knowledge operations.
- [`SKILL.md`](SKILL.md) — runtime contract and routing rules.

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md) for validation, issue, and release guidance. Report vulnerabilities through a [private GitHub security advisory](https://github.com/sergio-sisternes-epam/okf/security/advisories/new), not a public issue.

## License

Copyright 2026 Sergio Sisternes. Licensed under the [Apache License 2.0](LICENSE); see [`NOTICE`](NOTICE) for attribution.

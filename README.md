# OKF

Open Knowledge Format — An APM package to distribute the OKF format foundations for anyone to consume.

## Why / what this is not

OKF is the format authority and hard validator for portable Open Knowledge
Format **v0.2** bundles: Markdown files with YAML frontmatter.

It is not a live knowledge store. It does not ingest, query, expand, or lint
process memory.

## Install

Requires APM CLI 0.29.0 or newer.

```bash
apm marketplace add sergio-sisternes-epam/atlas-marketplace --name atlas
apm install okf@atlas
```

## Use

After install, ask your agent to apply the OKF skill. One example:

```text
Validate this directory as an OKF v0.2 bundle.
```

See `SKILL.md` for the runtime contract.

## Modules

| Module | Purpose |
| --- | --- |
| **okf-authority** | Normative rules, frontmatter, reserved files, and conformance |
| **okf-export** | Produce a portable OKF bundle |
| **okf-import** | Materialise an external OKF bundle |

Procedures live in `references/modules/`. Extra depth stays in `SKILL.md`.

## Related

- [atlas-marketplace](https://github.com/sergio-sisternes-epam/atlas-marketplace) — APM marketplace that publishes `okf`
- [okf-atlas](https://github.com/sergio-sisternes-epam/okf-atlas) — companion store for live knowledge-store operations

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for validation, issues, and release
handoff.

Do not file public issues for vulnerabilities. Report them through a
[private GitHub security advisory](https://github.com/sergio-sisternes-epam/okf/security/advisories/new).

## License

Copyright 2026 Sergio Sisternes. Licensed under the
[Apache License 2.0](LICENSE); see [NOTICE](NOTICE) for attribution.

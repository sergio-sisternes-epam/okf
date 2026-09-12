# okf

Open Knowledge Format — pure format standard and validator.

APM package: `okf` from the `atlas` marketplace (`sergio-sisternes-epam/atlas-marketplace`).

Grok-native layout: `SKILL.md` and `apm.yml` at the repository root.

## Prerequisites

- APM CLI 0.29.0 or newer.

## Install

Add the Atlas marketplace, then install OKF from it:

```bash
apm marketplace add sergio-sisternes-epam/atlas-marketplace --name atlas
apm install okf@atlas
```

Consumers of public github.com sources do not need `GITHUB_APM_PAT` or
Contents: read.

Direct git remains optional for the immutable release tag:

```bash
apm install sergio-sisternes-epam/okf#v0.2.1
```

Declare the same marketplace source when consuming OKF from another APM
project:

```yaml
dependencies:
  apm:
    - name: okf
      marketplace: atlas
```

Or pin the git tag:

```yaml
dependencies:
  apm:
    - sergio-sisternes-epam/okf#v0.2.1
```

See `SKILL.md` for the runtime contract and `apm.yml` for package metadata.

## Process memory (not this repo)

Live knowledge-store operations live in Atlas, not here. That store is a
separately licensed All Rights Reserved Atlas store, not a GitHub secret:

```text
atlas mount github.com/sergio-sisternes-epam/okf-atlas
```

Compile/query root: `.../okf-atlas/atlas` (OKF root is `atlas/SCHEMA.json`, not the git root).

Do not use `okf-wiki` for new process memory. Do not add `references/atlas`, `references/wiki`, or any knowledge store to this package.

## Support

Source, issues, changelog, and release history:
https://github.com/sergio-sisternes-epam/okf

See `CONTRIBUTING.md` for validation and release handoff.

## License

Copyright 2026 Sergio Sisternes. Licensed under the
[Apache License 2.0](LICENSE); see [NOTICE](NOTICE) for attribution.

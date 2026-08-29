---
name: okf-import
description: Bring an external Open Knowledge Format v0.2 bundle into the live session wiki. Trigger on import OKF, load knowledge bundle, ingest OKF bundle.
---

# OKF Import

Bring an external Open Knowledge Format v0.2 bundle into the live session wiki.

## Process

1. Locate the source bundle (directory path, zip, or tarball supplied by the user).
2. If archived, unpack it to a temporary location.
3. Validate basic OKF conformance:
   - Every non-reserved `.md` has YAML frontmatter
   - Every frontmatter contains a non-empty `type`
4. For each concept file:
   - Map it into the session wiki under `pages/` (preserve relative structure where sensible)
   - Keep all original frontmatter (never strip unknown keys)
   - Resolve or rewrite links so they work inside the session wiki
5. Update the session `index.md` and append a clear entry to `log.md` recording the import.
6. Optionally run a lightweight pass to surface any immediate contradictions or useful links.
7. Report what was imported (count of concepts, top-level types, any warnings).

## Rules

- Always load the `okf-authority` module (or the parent `okf` skill) for format rules, using the substrate contract below.
- Use the skill named `okf-wiki` for all writes into the session wiki (using the same contract).
- Prefer update-over-create.
- Never strip unknown frontmatter keys.

## Substrate contract (mandatory for every skill or module load)

When this body must invoke / load / execute another skill (or one of its progressive modules):

1. Locate the target skill **by name** from the harness’s available skills list (do not hard-code absolute paths).
2. Load the **full body** of that skill’s entrypoint (`SKILL.md`) using the harness’s on-demand skill-loader tool. Never rely on the short frontmatter description alone.
3. Follow the loaded body instructions **exactly**.
4. Re-execute any live tool calls the body requires.

For internal progressive-disclosure modules under `references/modules/`, locate the parent skill first, then `read_file` the module path relative to that skill root (or follow the loaded parent body’s own progressive-disclosure instructions).

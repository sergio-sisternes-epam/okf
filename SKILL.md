---
name: okf
description: Use this skill for Open Knowledge Format (OKF) rules, compliance, frontmatter requirements, and validation of any OKF bundle. Triggers on okf, Open Knowledge Format, OKF compliance, OKF frontmatter, validate OKF, OKF rules, and pure format questions. This is the pure format standard and validator. For live knowledge-store operations (ingest, query, expand, etc.) use okf-wiki instead.
version: 0.2.1
activation_card: on
---

# OKF — Open Knowledge Format (Pure Standard)

Format authority and hard validator for portable Open Knowledge Format (OKF) **v0.2** bundles.  
This skill knows **nothing** about live wiki operations, ingestion, or knowledge processes. Those belong to `okf-wiki`.

**Activation card (on):** Before any substantial path work, emit the standard Enter card (skill, skill_path, mode, subject, path, path_module, intent) and a matching path receipt at Exit. See autogenesis workflow-discipline for the canonical schema.

## Contained modules

| Module | Purpose |
|--------|---------|
| **okf-authority** | Normative rules, frontmatter, reserved files, conformance |
| **okf-export** | Produce a portable OKF bundle (called by okf-wiki or directly) |
| **okf-import** | Materialise an external OKF bundle (called by okf-wiki or directly) |

## Core normative rules (always apply)

1. Every non-reserved `.md` file must contain parseable YAML frontmatter.
2. Frontmatter must contain a non-empty `type` field.
3. Reserved filenames at any level: `index.md`, `log.md` (must not be used as concept files).
4. Directory structure is free; producers organise concepts as they see fit.
5. Consumers must tolerate unknown `type` values and unknown frontmatter keys.
6. Prefer update-over-create; never strip unknown frontmatter keys on import.
7. Links should be resolvable inside the target environment after import/export.

## How to route

- Pure format / compliance / validation questions → load the `okf-authority` module (see substrate contract below).
- Explicit request to export or import a portable bundle → load the matching module (still apply authority rules via the same contract).
- Any request about live ingest, query, expand, lint of the session store → hand off to the skill named `okf-wiki` (see substrate contract below).

## Substrate contract (mandatory for every skill or module load)

When this body must invoke / load / execute another skill (or one of its progressive modules):

1. Locate the target skill **by name** from the harness’s available skills list (do not hard-code absolute paths).
2. Load the **full body** of that skill’s entrypoint (`SKILL.md`) using the harness’s on-demand skill-loader tool. Never rely on the short frontmatter description alone.
3. Follow the loaded body instructions **exactly**.
4. Re-execute any live tool calls the body requires.

For internal progressive-disclosure modules under `references/modules/`, locate the parent skill first, then `read_file` the module path relative to that skill root (or follow the loaded parent body’s own progressive-disclosure instructions).

## Relationship to okf-wiki

- `okf` is the pure standard and validator.
- `okf-wiki` is the operational long-term knowledge / persistence layer.
- `okf-wiki` depends on this skill for all format rules and hard validation.
- This skill does not depend on `okf-wiki`.

## Progressive disclosure

Detailed procedures live in `references/modules/`. Load only what the current request needs.

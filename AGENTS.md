# AGENTS.md

Guidance for agents working at the root of this knowledge-base repository.

## Root Purpose

This repository is being organized as a multi-source knowledge base for OWD Figma Copilot. Keep each major source or dataset in its own top-level directory so API snapshots, product notes, design guidance, examples, and future corpora can evolve independently.

Current top-level content:

- `OWD-figma-api-snapshot-master/`: Figma developer docs snapshot generator and generated API/widget dataset.
- `.github/workflows/daily-crawl.yml`: root GitHub Actions workflow that runs the nested snapshot crawler.

Project-specific guidance for the snapshot crawler lives in `OWD-figma-api-snapshot-master/AGENTS.md`.

## Root Rules

- Keep `.git` at the repository root.
- Keep GitHub workflows under root `.github/workflows/`; GitHub will not run workflows nested inside dataset folders.
- Add new knowledge sources as separate top-level directories.
- Do not mix generated corpora from different sources in the same folder.
- Prefer scoped searches so generated corpora do not swamp results.
- When working on `OWD-figma-api-snapshot-master/`, follow that directory's own `AGENTS.md`.

## Validation

For root-only structure or workflow changes:

```bash
git status --short
git diff --check
```

For snapshot crawler changes, run validation from `OWD-figma-api-snapshot-master/`.

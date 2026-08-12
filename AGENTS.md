# ToeMath - local instructions

Before working here, read `~/codex-workspace/AGENTS.md`.

## Project context

- Docusaurus documentation site written in TypeScript.
- Keep documentation content in `docs/`, posts in `blog/`, and reusable UI in `src/`.
- Preserve sidebar IDs, document routes, links, and localization metadata when moving content.
- This checkout uses `package-lock.json`; prefer `npm ci` over introducing another package manager.
- Validate with `npm run typecheck` and `npm run build`; use `npm start` for local preview.
- Do not edit generated `.docusaurus/`, `build/`, or dependency directories manually.

Load only task-relevant AI Dev Team guidance; do not preload all rules, SPEC files, or `LEARNING_LOG.md`.

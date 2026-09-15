# Совместимость контекста ToeMath

Read-only baseline: GitHub `main` `18b8a0c`, чистый isolated checkout;
`reconcile_project_framework.py` классифицировал brownfield. Старые
`prompts/STAGES.md`, `docs/AI_PLAN.md`, `docs/AI_STATUS.md` — `MERGE`;
product `docusaurus.config.ts`, content/blog/src, `package.json`,
`pnpm-lock.yaml`, `docs/project-context.md` и `docs/LEARNING_LOG.md`
не перезаписываются framework-автоматикой. Docs-plugin exclude
защищает корневые governance files и `notes/**` от публичной сборки.

| Поверхность | Legacy conflict | Code/evidence resolution | Итог |
| --- | --- | --- | --- |
| Stage/current | Старый STAGES — каталог без selector; AI pair описывает завершённую infrastructure migration | `docusaurus.config.ts` содержит example identity; `docs/ROADMAP.md` и ADR-003 требуют отдельного выбора | `ADAPT`: Stage 1 `TOEMATH-PRODUCT-IDENTITY`, `blocked` |
| NEXT/blockers | Исторический AI_PLAN указывает product decision, но не stable selector | Не угадывать title/audience/locales/domain/repository/edit policy; сохранить scaffold content до классификации | `ADAPT`: `TOEMATH-PRODUCT-IDENTITY-DECISION` |
| Evidence | AI_STATUS содержит прошлые typecheck/build и dependency-audit факты | Сохранить past facts/hashes в `docs/notes`, не делать current production claim | `MERGE` разрешён |
| Docs site | `docs/` одновременно project context и продуктовый контент | Docs-plugin exclude корневые governance files и `notes/**`; `intro.md`/tutorial routes сохраняются | `PRESERVE` + config delta |

Формальный structured DEV bridge не добавлялся. Расположение STAGES задано
прямым указанием пользователя. Product identity и deployment по-прежнему
заблокированы; их status не определяется успешной docs migration.

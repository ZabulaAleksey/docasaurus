# Исторический source snapshot AI state

Уникальные факты старых `docs/AI_PLAN.md` и `docs/AI_STATUS.md` из GitHub
`main` `18b8a0c` сохранены до вывода этих live owners. SHA-256 исходных
файлов: AI_PLAN
`d3cfd3fbaf0255d4e9d25e2b1e9b8550662674f466aea94cb3c3405388cee570`,
AI_STATUS
`1ce7c44e14b4ccebb4144594943e8870958e86d9928aa4aeccba46a0cf4927bc`.
Предыдущий Git commit позволяет восстановить bytes. Этот файл не является
current plan/status/NEXT; выбранный state находится в `docs/STAGES.md`.

## Из старого AI_PLAN

- Governance/dependency manager migration 2026-08-24 описана как DONE:
  npm/yarn заменены `pnpm@11.23.0`, clean restore использует один
  `pnpm-lock.yaml`, shared store и project-local virtual-store fallback.
  Scaffold content/product requirements не менялись.
- Следующее осмысленное действие — получить product identity decision,
  потом заменить scaffold metadata, только потом inventory/reorganization.
  Нельзя угадывать domain, brand, GitHub owner, locales или удалять
  tutorial pages без классификации.
- Исторический governance DoD: overlay validator, typecheck, честный build,
  no stale global path, product uncertainties, локально интегрированная
  dependency migration; push на момент записи не выполнялся.
- Duplicate `/` routes/default export требуют отдельной продуктовой задачи.

## Из старого AI_STATUS

- Baseline на 2026-08-24: Docusaurus 3.9.2, React 19, TypeScript,
  `pnpm@11.23.0`, lockfile; product identity/deployment `UNVERIFIED`,
  backend/API и automated unit/integration/E2E runner отсутствовали.
- После clean restore `pnpm typecheck` и `pnpm build` прошли тогда.
  Global virtual store оказался несовместим с Docusaurus/TypeScript type
  resolution; сохранён проверенный fallback `node_modules/.pnpm`.
- Для компиляции явно объявлены прежде скрытые dependencies
  `@docusaurus/theme-classic`, `@types/node`, `@types/react`; build scripts
  разрешены только для `core-js` и `core-js-pure`.
- На момент записи Docusaurus сообщал о 3.10.2 и старой Browserslist базе;
  версии не обновлялись. `pnpm audit` тогда дал 64 транзитивных advisory
  (2 critical, 35 high, 23 moderate, 4 low); автоматического breaking fix
  не было, dependency-upgrade этап оставался отдельным.
- Dependency migration локально вошла в `main`, checkout тогда был чистым;
  push/deploy на момент записи не выполнялись. Текущий GitHub `main` уже
  содержит PR merge `18b8a0c`; historical claim не является live Git status.

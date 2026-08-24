# Состояние ToeMath

Дата: 2026-08-24.

- Текущий baseline: Docusaurus 3.9.2 / React 19 / TypeScript, `pnpm@11.23.0` и `pnpm-lock.yaml`.
- Product identity и deployment target: `UNVERIFIED`; конфигурация содержит scaffold metadata.
- Backend/API: отсутствует.
- Automated unit/integration/E2E runner: отсутствует. После clean restore `pnpm typecheck` и `pnpm build` — PASS.
- Общий pnpm content store используется; экспериментальный global virtual store несовместим с type-resolution Docusaurus/TypeScript, поэтому применён проверенный fallback на `node_modules/.pnpm`.
- Для компиляции явно объявлены ранее скрытые npm-hoisting зависимости `@docusaurus/theme-classic`, `@types/node` и `@types/react`; build scripts разрешены только для `core-js` и `core-js-pure`.
- Docusaurus сообщает о доступном обновлении 3.10.2 и устаревшей Browserslist-базе; версии намеренно не обновлялись в инфраструктурной миграции.
- `pnpm audit` фиксирует 64 транзитивных advisory (2 critical, 35 high, 23 moderate, 4 low) в Docusaurus/build-tooling цепочках; автоматический breaking fix не выполнялся, требуется отдельный dependency-upgrade этап.
- Основной checkout: 13 пользовательских staged изменений сохранены; governance находится в отдельном worktree.
- Push/merge/deploy: не выполнялись.

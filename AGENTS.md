# ToeMath — локальные инструкции

Перед работой прочитай `~/.codex/AGENTS.md`; этот файл содержит только project-specific delta. Этапы находятся в `prompts/STAGES.md`, состояние — в `docs/AI_STATUS.md`.

## Контекст

- Проект — статический documentation site на Docusaurus 3.9.2, React 19 и TypeScript.
- Документация находится в `docs/`, публикации — в `blog/`, переиспользуемый UI — в `src/`.
- Сохраняй route/sidebar ids, ссылки, front matter и локализацию при переносе материалов.
- Канонический package manager — `pnpm@11.23.0` с `pnpm-lock.yaml`; используй `pnpm install --frozen-lockfile`.
- Общий pnpm content store разрешён; project-local `node_modules` остаётся генерируемой disposable projection. При блокировке `pnpm.ps1` используй `pnpm.cmd`.
- Не редактируй генерируемые `.docusaurus/`, `build/` и dependency directories.

## Проверки

- `pnpm typecheck`
- `pnpm build`
- локальный просмотр при необходимости: `pnpm start`

Обязательный unit/integration runner пока отсутствует. Принятые tests/fixtures, когда они появятся, меняются только отдельным contract decision. Browser/E2E до появления стабильного продукта помечается `BLOCKED_BY_PRODUCT_BASELINE_TOEMATH`.

## Ограничения

- Текущий `docusaurus.config.ts` сохраняет scaffold metadata (`My Site`, facebook/docusaurus links); не заявляй production readiness до отдельного этапа идентификации продукта.
- Не выполняй deploy, push или merge без явного разрешения пользователя.

# Журнал проверенных наблюдений

- `package.json` требует Node.js 20+ и предоставляет `typecheck`/`build`, но не test script.
- README исторически предлагал yarn, хотя repository содержит `package-lock.json`; локальный контракт нормализован на npm.
- `docusaurus.config.ts` содержит upstream example identity и links, поэтому успешный build сам по себе не означает готовность сайта к публикации.
- Основной checkout имел пользовательские staged изменения контента; governance выполнен в отдельном linked worktree и их не перезаписывает.
- TypeScript gate проходит после `npm ci`, но Docusaurus build выявляет два существующих `/` route и homepage module без доступного default export.
- Lockfile dependency tree содержит 55 advisories (2 critical, 32 high); автоматический `npm audit fix` не запускался из-за риска breaking changes.

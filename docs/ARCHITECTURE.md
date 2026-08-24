# Архитектура

```text
docs/ + blog/ + static assets
             ↓
Docusaurus content/plugins + sidebars
             ↓
React theme/components in src/
             ↓
static build/
```

Content routes и sidebar ids являются публичным контрактом. `docusaurus.config.ts` задаёт site identity, base URL, i18n, edit links и theme; сейчас часть значений остаётся upstream scaffold. Генерируемые `.docusaurus/` и `build/` не являются source of truth. Backend и runtime persistence отсутствуют.

## Контракт зависимостей

- Источник истины (Source of truth): `package.json`, `pnpm-lock.yaml` и `pnpm-workspace.yaml`; канонический менеджер — `pnpm@11.23.0`.
- Чистое восстановление (Clean restore): удалить только disposable `node_modules`, затем выполнить `pnpm install --frozen-lockfile`.
- Общий pnpm content store разрешён, но virtual store остаётся project-local: global virtual store несовместим с текущим TypeScript/Docusaurus resolution baseline.
- `allowBuilds` ограничен `core-js` и `core-js-pure`; npm/Yarn/Bun lock-файлы не допускаются.
- `node_modules`, `.docusaurus`, `build` и tool caches пересоздаваемы; docs/content и site configuration dependency cleanup не затрагивает.
- Locked gates: pnpm typecheck и production build согласно `package.json`; возврат к global virtual store требует отдельного compatibility proof.

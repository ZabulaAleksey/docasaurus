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

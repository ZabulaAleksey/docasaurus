---
sidebar_position: 2
---

# Перевод сайта

Переведём `docs/intro.md` на французский язык.

## Настройка i18n

Измени `docusaurus.config.js`, чтобы добавить поддержку локали `fr`:

```js title="docusaurus.config.js"
export default {
  i18n: {
    defaultLocale: 'en',
    locales: ['en', 'fr'],
  },
};
```

## Перевод документа

Скопируй файл `docs/intro.md` в каталог `i18n/fr`:

```bash
mkdir -p i18n/fr/docusaurus-plugin-content-docs/current/

cp docs/intro.md i18n/fr/docusaurus-plugin-content-docs/current/intro.md
```

Переведи `i18n/fr/docusaurus-plugin-content-docs/current/intro.md` на французский язык.

## Запуск локализованного сайта

Запусти сайт с французской локалью:

```bash
npm run start -- --locale fr
```

Локализованный сайт будет доступен по адресу [http://localhost:3000/fr/](http://localhost:3000/fr/), а страница «Начало работы» будет переведена.

:::caution

В режиме разработки одновременно можно использовать только одну локаль.

:::

## Добавление списка локалей

Чтобы удобно переключаться между языками, добавь раскрывающийся список локалей.

Измени файл `docusaurus.config.js`:

```js title="docusaurus.config.js"
export default {
  themeConfig: {
    navbar: {
      items: [
        // highlight-start
        {
          type: 'localeDropdown',
        },
        // highlight-end
      ],
    },
  },
};
```

В панели навигации появится раскрывающийся список локалей:

![Раскрывающийся список локалей](./img/localeDropdown.png)

## Сборка локализованного сайта

Собери сайт для определённой локали:

```bash
npm run build -- --locale fr
```

Или собери сайт сразу со всеми локалями:

```bash
npm run build
```

---
sidebar_position: 2
---

# Создание документа

Документы — это **группы страниц**, связанные через:

- **боковую панель**;
- навигацию **назад/вперёд**;
- **версионирование**.

## Создание первого документа

Создай Markdown-файл `docs/hello.md`:

```md title="docs/hello.md"
# Привет

Это мой **первый документ Docusaurus**!
```

Новый документ доступен по адресу [http://localhost:3000/docs/hello](http://localhost:3000/docs/hello).

## Настройка боковой панели

Docusaurus автоматически **создаёт боковую панель** по содержимому каталога `docs`.

Добавь метаданные, чтобы настроить подпись и позицию в боковой панели:

```md title="docs/hello.md" {1-4}
---
sidebar_label: 'Привет!'
sidebar_position: 3
---

# Привет

Это мой **первый документ Docusaurus**!
```

Боковую панель также можно описать явно в `sidebars.js`:

```js title="sidebars.js"
export default {
  tutorialSidebar: [
    'intro',
    // highlight-next-line
    'hello',
    {
      type: 'category',
      label: 'Руководство',
      items: ['tutorial-basics/create-a-document'],
    },
  ],
};
```

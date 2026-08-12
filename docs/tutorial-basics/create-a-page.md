---
sidebar_position: 1
---

# Создание страницы

Добавляй файлы **Markdown или React** в `src/pages`, чтобы создавать **самостоятельные страницы**:

- `src/pages/index.js` → `localhost:3000/`
- `src/pages/foo.md` → `localhost:3000/foo`
- `src/pages/foo/bar.js` → `localhost:3000/foo/bar`

## Создание первой страницы React

Создай файл `src/pages/my-react-page.js`:

```jsx title="src/pages/my-react-page.js"
import React from 'react';
import Layout from '@theme/Layout';

export default function MyReactPage() {
  return (
    <Layout>
      <h1>Моя страница React</h1>
      <p>Это страница React</p>
    </Layout>
  );
}
```

Новая страница доступна по адресу [http://localhost:3000/my-react-page](http://localhost:3000/my-react-page).

## Создание первой страницы Markdown

Создай файл `src/pages/my-markdown-page.md`:

```mdx title="src/pages/my-markdown-page.md"
# Моя страница Markdown

Это страница Markdown
```

Новая страница доступна по адресу [http://localhost:3000/my-markdown-page](http://localhost:3000/my-markdown-page).

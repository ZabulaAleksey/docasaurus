---
slug: welcome
title: Добро пожаловать
authors: [slorber, yangshun]
tags: [facebook, hello, docusaurus]
---

[Возможности блога Docusaurus](https://docusaurus.io/docs/blog) предоставляются [плагином блога](https://docusaurus.io/docs/api/plugins/@docusaurus/plugin-content-blog).

Ниже приведено несколько полезных советов.

<!-- truncate -->

Просто добавляй Markdown-файлы или каталоги в `blog`.

Постоянных авторов блога можно добавить в `authors.yml`.

Дата публикации может извлекаться из имени файла, например:

- `2019-05-30-welcome.md`
- `2019-05-30-welcome/index.md`

Каталог публикации удобен для хранения её изображений рядом с текстом:

![Плюшевая игрушка Docusaurus](./docusaurus-plushie-banner.jpeg)

Блог также поддерживает теги.

**Если блог не нужен**, удали этот каталог и укажи `blog: false` в конфигурации Docusaurus.

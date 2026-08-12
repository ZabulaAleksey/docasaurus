---
sidebar_position: 3
---

# Создание публикации в блоге

Docusaurus создаёт **страницу для каждой публикации**, а также **страницу-оглавление блога**, **систему тегов** и ленту **RSS**.

## Создание первой публикации

Создай файл `blog/2021-02-28-greetings.md`:

```md title="blog/2021-02-28-greetings.md"
---
slug: greetings
title: Приветствие!
authors:
  - name: Joel Marcey
    title: Соавтор Docusaurus 1
    url: https://github.com/JoelMarcey
    image_url: https://github.com/JoelMarcey.png
  - name: Sébastien Lorber
    title: Сопровождающий Docusaurus
    url: https://sebastienlorber.com
    image_url: https://github.com/slorber.png
tags: [приветствие]
---

Поздравляем, ты создал свою первую публикацию!

Можешь свободно экспериментировать и редактировать эту публикацию.
```

Новая публикация доступна по адресу [http://localhost:3000/blog/greetings](http://localhost:3000/blog/greetings).

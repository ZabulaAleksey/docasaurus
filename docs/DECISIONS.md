# Архитектурные решения

## ADR-001 — Docusaurus остаётся текущей платформой

Статус: принято для существующего baseline. Миграция не меняет стек без продуктового требования.

## ADR-002 — npm lockfile является каноническим

Статус: принято. Используется `npm ci`; смешивание yarn/npm без отдельной миграции запрещено.

## ADR-003 — Scaffold metadata не считается production contract

Статус: принято. Название, domain/baseUrl, organization/project links, locales и edit links утверждаются отдельным этапом до deploy.

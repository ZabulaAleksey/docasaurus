# Архитектурные решения

## ADR-001 — Docusaurus остаётся текущей платформой

Статус: принято для существующего baseline. Миграция не меняет стек без продуктового требования.

## ADR-002 — pnpm lockfile является каноническим

Статус: заменено миграцией 2026-08-24. Используется `pnpm@11.23.0` и `pnpm install --frozen-lockfile`; единственный lock-файл — `pnpm-lock.yaml`. Общий content store и global virtual store уменьшают дублирование, а возврат к npm/yarn требует отдельного решения и полного regression-прогона.

## ADR-003 — Scaffold metadata не считается production contract

Статус: принято. Название, domain/baseUrl, organization/project links, locales и edit links утверждаются отдельным этапом до deploy.

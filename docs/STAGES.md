# Этапы ToeMath

- Stage ID: TOEMATH-PRODUCT-IDENTITY

Этот файл — единственный владелец current stage/status/blockers/evidence/NEXT.
Прошлые сведения AI pair сохранены в `docs/notes/legacy-ai-state-evidence.md`
как historical source, а не второй текущий план или статус.

## Общий контракт

Выполняй один этап за раз. Перед изменениями прочитай `AGENTS.md`,
`docs/project-context.md` и только выбранный record здесь. Не угадывай
product identity и не удаляй scaffold/content без подтверждённой
классификации. Минимальные gates каждого этапа: `pnpm typecheck` и
`pnpm build`. Внутренний STAGES исключён из публичного docs plugin.

## TOEMATH-PRODUCT-IDENTITY — Этап 1: Утвердить product identity

- Status: blocked
- NEXT: TOEMATH-PRODUCT-IDENTITY-DECISION
- Blockers: название, audience, primary language/locales, production
  URL/baseUrl, repository organization/project и edit-link policy не
  утверждены; `docusaurus.config.ts` ещё содержит `My Site`, example URL,
  `facebook/docusaurus` links.
- Evidence: `docusaurus.config.ts`, `docs/project-context.md`,
  `docs/DECISIONS.md` и legacy AI pair сверены с GitHub `main` `18b8a0c`.
  Governance/dependency migration была интегрирована, а typecheck/build
  PASS в исходном AI_STATUS относится к 2026-08-24; это не подтверждение
  product identity и не текущая production readiness. Для этой docs/config
  migration pinned `pnpm@11.23.0` frozen restore, `pnpm typecheck` и
  `pnpm build` — PASS; built output содержит `intro`/tutorial routes и не
  содержит internal STAGES/notes/governance routes или action IDs.

Цель: получить проверенные название, audience, primary language/locales, production URL/baseUrl, GitHub organization/project и edit-link policy.

Scope: SPEC/ADR и конфигурационные значения. Non-goals: редизайн, массовая правка content, deploy. DoD: ни одного example `My Site`/facebook/docusaurus значения в active contract, все решения отражены в ADR, build PASS.

### Действия пользователя

- `USER-TOEMATH-PRODUCT-IDENTITY` — `PENDING`, condition: до реализации
  Stage 1 требуется продуктовый выбор. Безопасное действие: утвердить
  проверенные название/audience, primary locales, production URL/baseUrl,
  GitHub owner/project и edit-link policy. Ожидаемое evidence: SPEC/ADR с
  этими решениями, согласованная Docusaurus config и build PASS. Это
  разблокирует Stage 1 и последующий content inventory; scaffold pages
  до этого не удаляются.
- `USER-TOEMATH-STAGES-INTEGRATION` — `DONE`: пользователь разрешил merge
  `feature/docs-stages-canonical`; `main` fast-forward до `8ee1d60` и
  опубликован. GitHub read-back подтвердил только `docs/STAGES.md` из четырёх
  state paths. Selector `TOEMATH-PRODUCT-IDENTITY`, `blocked` и NEXT проходят
  canonical adapter; `pnpm typecheck` и `pnpm build` прошли. Product decision
  остаётся отдельным blocker.

## TOEMATH-CONTENT-INVENTORY — Этап 2: Content inventory и классификация

- Status: planned
- Depends on: TOEMATH-PRODUCT-IDENTITY completed

Цель: классифицировать каждый документ/blog page как предметный ToeMath content, полезный tutorial, кандидат на переписывание или scaffold.

Требования: сохранить route ids и входящие links до утверждённой redirect/delete policy; предметные math assets не терять. DoD: versioned inventory, решение по каждой странице, no broken links. Массовое удаление вне этого этапа запрещено.

## TOEMATH-INFORMATION-ARCH — Этап 3: Information architecture

- Status: planned
- Depends on: TOEMATH-CONTENT-INVENTORY completed

Цель: утвердить sidebar, landing/navigation и content taxonomy на основе inventory.

Scope: routes, sidebars, front matter, navigation; accessibility и responsive states. DoD: typecheck/build PASS, link validation, documented redirects для изменённых routes.

## TOEMATH-QUALITY-GATES — Этап 4: Quality automation

- Status: planned
- Depends on: TOEMATH-INFORMATION-ARCH completed

Цель: добавить воспроизводимые content gates.

Scope: markdown/MDX lint, internal links, build warnings policy, минимальный browser smoke критических routes. DoD: команды зафиксированы в package scripts/CI, negative fixture доказывает работу gate, принятые checks не ослаблены.

## TOEMATH-DEPLOYMENT-CONTRACT — Этап 5: Deployment contract

- Status: blocked
- Depends on: TOEMATH-QUALITY-GATES completed
- Blockers: product identity/content/quality prerequisites и отдельное
  разрешение на внешнюю публикацию отсутствуют.

Цель: подготовить hosting, environment, observability и rollback после завершения этапов 1–4.

Non-goals: фактическая внешняя публикация без разрешения. DoD: production build evidence, baseUrl/404/assets smoke, rollback steps и owner decision.

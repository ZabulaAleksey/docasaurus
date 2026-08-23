# Этапы ToeMath

## Общий контракт

Выполняй один этап за раз. Перед изменениями прочитай `AGENTS.md`, `docs/project-context.md`, `docs/AI_PLAN.md` и `docs/AI_STATUS.md`. Не угадывай product identity и не удаляй scaffold/content без подтверждённой классификации. Минимальные gates каждого этапа: `npm run typecheck` и `npm run build`.

## Этап 1 — Утвердить product identity

Цель: получить проверенные название, audience, primary language/locales, production URL/baseUrl, GitHub organization/project и edit-link policy.

Scope: SPEC/ADR и конфигурационные значения. Non-goals: редизайн, массовая правка content, deploy. DoD: ни одного example `My Site`/facebook/docusaurus значения в active contract, все решения отражены в ADR, build PASS. Статус: `BLOCKED_BY_PRODUCT_DECISION`.

## Этап 2 — Content inventory и классификация

Цель: классифицировать каждый документ/blog page как предметный ToeMath content, полезный tutorial, кандидат на переписывание или scaffold.

Требования: сохранить route ids и входящие links до утверждённой redirect/delete policy; предметные math assets не терять. DoD: versioned inventory, решение по каждой странице, no broken links. Массовое удаление вне этого этапа запрещено.

## Этап 3 — Information architecture

Цель: утвердить sidebar, landing/navigation и content taxonomy на основе inventory.

Scope: routes, sidebars, front matter, navigation; accessibility и responsive states. DoD: typecheck/build PASS, link validation, documented redirects для изменённых routes.

## Этап 4 — Quality automation

Цель: добавить воспроизводимые content gates.

Scope: markdown/MDX lint, internal links, build warnings policy, минимальный browser smoke критических routes. DoD: команды зафиксированы в package scripts/CI, negative fixture доказывает работу gate, принятые checks не ослаблены.

## Этап 5 — Deployment contract

Цель: подготовить hosting, environment, observability и rollback после завершения этапов 1–4.

Non-goals: фактическая внешняя публикация без разрешения. DoD: production build evidence, baseUrl/404/assets smoke, rollback steps и owner decision. Статус до выполнения prerequisites: `BLOCKED_BY_PRODUCT_BASELINE_TOEMATH`.

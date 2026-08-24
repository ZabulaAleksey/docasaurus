# Текущий план

Инфраструктурный срез 2026-08-24: миграция npm/yarn-команд на `pnpm@11.23.0`, clean restore из единственного `pnpm-lock.yaml`, shared content store и проверенный project-local virtual-store fallback — `DONE`. Продуктовые требования и scaffold content не изменялись.

Статус: governance migration подготовлена отдельно от dirty основного checkout.

Следующее осмысленное действие — получить product identity decision, затем заменить scaffold metadata и только после этого реорганизовывать content. До решения нельзя угадывать домен, бренд, GitHub organization, locales или удалять tutorial pages.

Definition of Done текущего governance-этапа: overlay validator PASS, `typecheck` проверен, результат `build` записан честно, stale global path отсутствует, product uncertainties обозначены явно, push/merge не выполнены. Исправление duplicate `/` routes/default export требует отдельной продуктовой задачи.

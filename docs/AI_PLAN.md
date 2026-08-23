# Текущий план

Статус: governance migration подготовлена отдельно от dirty основного checkout.

Следующее осмысленное действие — получить product identity decision, затем заменить scaffold metadata и только после этого реорганизовывать content. До решения нельзя угадывать домен, бренд, GitHub organization, locales или удалять tutorial pages.

Definition of Done текущего governance-этапа: overlay validator PASS, `typecheck` проверен, результат `build` записан честно, stale global path отсутствует, product uncertainties обозначены явно, push/merge не выполнены. Исправление duplicate `/` routes/default export требует отдельной продуктовой задачи.

# Integrations · Интеграции

Templates that put VeriFirst into your team's everyday tools. Copy them into **your own** repository or tracker.

Шаблоны, которые встраивают VeriFirst в повседневные инструменты команды. Копируйте их в **свой** репозиторий или трекер.

---

## GitHub

| File · Файл | Copy to · Куда скопировать | What it does · Что делает |
|---|---|---|
| [`github/ISSUE_TEMPLATE/ai-task.yml`](github/ISSUE_TEMPLATE/ai-task.yml) | `.github/ISSUE_TEMPLATE/ai-task.yml` | Issue form with the Intent Contract fields (English) |
| [`github/ISSUE_TEMPLATE/ai-task-ru.yml`](github/ISSUE_TEMPLATE/ai-task-ru.yml) | `.github/ISSUE_TEMPLATE/ai-task-ru.yml` | Форма задачи с полями Контракта намерения (русский) |
| [`github/pull_request_template.md`](github/pull_request_template.md) | `.github/pull_request_template.md` | PR template with the Break checklist and reversibility level · Шаблон PR с чек-листом «Сломай» и уровнем обратимости |

The forms add the label `ai-task`; create it in your repository so it is applied.
Формы ставят метку `ai-task`; создайте её в своём репозитории, чтобы она применялась.

---

## Jira (and similar trackers · и похожие трекеры)

Jira has no single file to drop in, so set it up once by hand. Exact menu names depend on your Jira edition and version.
В Jira нет одного файла, который можно просто положить, поэтому настройка делается один раз вручную. Названия меню зависят от редакции и версии Jira.

1. **Custom field "Trust quadrant" · Поле «Квадрант доверия»** — a single-select list with 🟢 Delegate, 🟡 Delegate + Review, 🔵 Explore, 🔴 Advise. Add it to the issue screen of the task types that involve AI.
   Выпадающий список с четырьмя квадрантами; добавить на экран задач, где участвует ИИ.
2. **Description template · Шаблон описания** — paste the Intent Contract ([EN](../templates/en/intent-contract.md) · [RU](../templates/ru/intent-contract.md)) as the default description, or add it with an automation rule on issue creation.
   Вставить Контракт намерения как описание по умолчанию или добавлять его правилом автоматизации при создании задачи.
3. **Workflow status "Verification" · Статус «Проверка»** — between *In Progress* and *Done*. For 🟡 and 🔴 issues, the transition to *Done* requires the Break checklist ([EN](../templates/en/break-review.md) · [RU](../templates/ru/break-review.md)) and a verifier different from the assignee.
   Между «В работе» и «Готово». Для 🟡 и 🔴 переход в «Готово» — только после чек-листа «Сломай» и проверяющим, отличным от исполнителя.
4. **Label `verification-debt` · Метка `verification-debt`** — for results accepted without a required Break pass. Review the count at every planning session.
   Для результатов, принятых без обязательного прохода «Сломай». Смотреть их число на каждом планировании.
5. **Dashboard · Дашборд** — issues reopened after *Done* because of an AI error (escaped errors) and the count of `verification-debt` issues.
   Задачи, переоткрытые после «Готово» из-за ошибки ИИ (ускользнувшие ошибки), и число задач с меткой `verification-debt`.

# AI instructions · Инструкции для ИИ

Ready-to-use files that make an AI assistant follow VeriFirst on its own: it names the Trust Map quadrant, asks for done criteria, never invents facts, lists its assumptions and stops before irreversible actions.

Готовые файлы, которые заставляют ИИ-ассистента работать по VeriFirst самостоятельно: он называет квадрант Карты доверия, спрашивает критерий готовности, не выдумывает факты, перечисляет допущения и останавливается перед необратимыми действиями.

| Tool · Инструмент | File · Файл | Where to put it · Куда положить |
|---|---|---|
| Claude (Projects), ChatGPT (Projects, GPTs), any chat with a system prompt | [`en/system-prompt.md`](en/system-prompt.md) · [`ru/system-prompt.md`](ru/system-prompt.md) | Paste into the project / GPT instructions · Вставить в инструкции проекта или GPT |
| Fields with a character limit (e.g. ChatGPT custom instructions) | [`en/short.md`](en/short.md) · [`ru/short.md`](ru/short.md) | Paste into the instructions field · Вставить в поле инструкций |
| GigaChat, YandexGPT / Алиса, DeepSeek and other chat assistants · и другие чат-ассистенты | [`ru/short.md`](ru/short.md) · [`en/short.md`](en/short.md); via API · через API: [`ru/system-prompt.md`](ru/system-prompt.md) | Where the tool has a custom-instructions field, paste it there; otherwise paste it as the first message of the chat. Via API, pass the file as the system message · Если в инструменте есть поле для своих инструкций — вставить туда, если нет — первым сообщением в чате. Через API — передать файл как системное сообщение (system) |
| Claude Code | [`en/CLAUDE.md`](en/CLAUDE.md) · [`ru/CLAUDE.md`](ru/CLAUDE.md) | Repository root as `CLAUDE.md`, or append to an existing one · В корень репозитория как `CLAUDE.md` или дописать в существующий |
| Cursor | [`en/verifirst.mdc`](en/verifirst.mdc) · [`ru/verifirst.mdc`](ru/verifirst.mdc) | `.cursor/rules/verifirst.mdc` |
| GitHub Copilot | [`en/copilot-instructions.md`](en/copilot-instructions.md) · [`ru/copilot-instructions.md`](ru/copilot-instructions.md) | `.github/copilot-instructions.md` |

Tool locations change over time; check your tool's current documentation if a path does not work.
Расположение файлов в инструментах со временем меняется; если путь не сработал, сверьтесь с актуальной документацией инструмента.

**Important · Важно:** these rules make the AI more careful, but self-review is not verification. 🟡 and 🔴 work still needs an independent Break pass ([checklist](../templates/en/break-review.md) · [чек-лист](../templates/ru/break-review.md)).
Эти правила делают ИИ аккуратнее, но самопроверка — не проверка. Для 🟡 и 🔴 задач независимый проход «Сломай» всё равно нужен.

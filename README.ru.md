# UX/UI Психология — навык Hermes Agent

[English](README.md) · **Русский**

> Перевод основного [README.md](README.md). Если расхождения — английская версия считается каноном.

Навык [Hermes Agent](https://hermes-agent.nousresearch.com/) с правилами «триггер → действие» для дизайна интерфейсов. Содержит три взаимодополняющих блока:

1. **Шесть психологических принципов** — каждый с конкретным триггером (когда применять) и действием (что менять).
2. **Три паттерна A/B-тестов** — пейвол, заказ поездки, бронирование — как actionable-правила, а не кейсы.
3. **Триггеры для пейволов** — конкретные правила на уровне экрана, CTA, триала и ценообразования, собранные из исследования 2 995 пейволов.

Объединяющий мета-принцип: **каждый элемент интерфейса задаёт пользователю внутренний вопрос. Чем проще вопрос, тем выше конверсия.**

## Зачем нужен

Загружай этот навык, когда:

- Проектируешь или ревьюишь **онбординг, регистрацию, формы, прайсинг, пейволы, апсейлы**.
- Разбираешься, **почему пользователи отваливаются** на конкретном экране.
- Объясняешь заказчику или команде, почему «просто добавить кнопку» не починит конверсию.
- Пишешь промпты для генерации UI (`claude-design`, `sketch`, `popular-web-designs`).

Навык про **поведенческую психологию**, а не про визуальную эстетику (цвета, типографика, сетка) — для этого есть `popular-web-designs`. Здесь только то, как люди принимают решения.

## Структура

Навык использует **progressive disclosure** — тонкую точку входа (`SKILL.md`, ~6 КБ), которая грузится всегда, и глубокий материал в `references/`, который подгружается по мере необходимости.

```
ux-ui-psychology/
├── SKILL.md                          # Точка входа (~5 КБ, грузится всегда)
├── references/
│   ├── principles.md                 # 6 принципов в формате Триггер → Действие
│   ├── ab-test-patterns.md           # 3 паттерна в формате Триггер → Действие
│   ├── paywall-patterns.md           # Триггеры для пейволов: экран, CTA, триал, цена
│   ├── screen-recipes.md             # Рецепты для 8 типов экранов
│   └── ethics-and-pitfalls.md        # Этическая граница, 10 ошибок, чек-лист
├── guides/                           # Гайды по установке в разные инструменты
├── README.md (EN), README.ru.md (этот файл)
├── LICENSE
└── .gitignore
```

> ⚠️ **Языковое замечание:** `SKILL.md` и `references/` на английском (это канон для совместимости со всеми AI-инструментами). Русский — только в README.

| Файл | Назначение |
|------|-----------|
| `SKILL.md` | Краткие таблицы + ссылки. Грузится на каждую задачу. |
| `references/principles.md` | Каждый принцип как триггер, действие и возможная ошибка. |
| `references/ab-test-patterns.md` | Три паттерна в формате trigger → action. |
| `references/paywall-patterns.md` | Конкретные триггеры: уровень экрана, CTA, триал, ценообразование, фрейминг. |
| `references/screen-recipes.md` | Онбординг, форма, пейвол, бронирование, лендинг, отток, пустое состояние, уведомления. |
| `references/ethics-and-pitfalls.md` | Чего делать нельзя, почему, и чек-лист перед релизом. |

## Установка

Это стандартный навык Hermes Agent. Положи `SKILL.md` (и папку `references/`) в свой каталог навыков:

```bash
# Локально для пользователя (личное использование)
mkdir -p ~/.hermes/skills/creative/ux-ui-psychology
cp SKILL.md ~/.hermes/skills/creative/ux-ui-psychology/SKILL.md
cp -r references ~/.hermes/skills/creative/ux-ui-psychology/

# Или в репозиторий Hermes Agent (для контрибьюторов)
cp SKILL.md /path/to/hermes-agent/skills/creative/ux-ui-psychology/SKILL.md
cp -r references /path/to/hermes-agent/skills/creative/ux-ui-psychology/
```

Перезапусти сессию (или начни новую) — и навык подхватится.

## Использование с другими AI-инструментами

Навык — это универсальный markdown, он работает с Claude Code, Codex CLI, OpenCode, Cursor, Gemini CLI, Cline, Continue.dev, Aider и Windsurf. У каждого инструмента своя конвенция, где лежат файлы контекста.

**Краткий гайд по установке:** см. [`guides/`](guides/README.md) — инструкция для каждого инструмента.

| Инструмент | Конвенция | Гайд |
|------------|-----------|------|
| Hermes Agent | `~/.hermes/skills/<cat>/<name>/SKILL.md` | (этот README) |
| Claude Code | `.claude/skills/<name>.md` | [guides/claude-code.md](guides/claude-code.md) |
| Codex CLI | `AGENTS.md` в корне | [guides/codex.md](guides/codex.md) |
| OpenCode | `AGENTS.md` в корне | [guides/opencode.md](guides/opencode.md) |
| Cursor | `.cursor/rules/<name>.mdc` | [guides/cursor.md](guides/cursor.md) |
| Gemini CLI | `GEMINI.md` в корне | [guides/gemini-cli.md](guides/gemini-cli.md) |
| Cline | директория `.clinerules/` | [guides/cline.md](guides/cline.md) |
| Continue.dev | `.continue/rules/<name>.md` | [guides/continue.md](guides/continue.md) |
| Aider | `CONVENTIONS.md` или `--read` | [guides/aider.md](guides/aider.md) |
| Windsurf | `.windsurfrules` в корне | [guides/windsurf.md](guides/windsurf.md) |

## Источники

Все три исходных видео указаны в `SKILL.md`. Краткая сводка:

- **Шесть принципов** — [youtube.com/watch?v=2TlIg3VokY8](https://www.youtube.com/watch?v=2TlIg3VokY8)
- **Три A/B-теста** — [youtube.com/watch?v=zr37ibqXl1U](https://www.youtube.com/watch?v=zr37ibqXl1U)
- **Исследование 2 995 пейволов** — [youtube.com/watch?v=9ypqs_2fAl8](https://www.youtube.com/watch?v=9ypqs_2fAl8)

Все таймстампы, проценты (70–90%, 2× неприятие потери) и суммы ($50 vs $1900, $13–17, $19/мес, Opal 7→17%, Outsider 5×) — из оригинальных роликов.

## Этичность

Эти приёмы существуют, чтобы **снижать путаницу и строить доверие**, а не манипулировать. Навык явно помечает как запрещённые: фейковые таймеры обратного отсчёта, поддельные отзывы, выдуманные потери, сложные cancellation-флоу. Проверочный тест: *если бы пользователь понял, как это работает, почувствовал бы он себя обманутым?* Если да — не выкладывай.

## Лицензия

MIT — см. [LICENSE](LICENSE).

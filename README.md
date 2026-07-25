# cain_skills

Контент-скиллы для Cain / OpenClaw / Hermes и любых Claude-совместимых агентов.
Чистые prompt-скиллы: один `SKILL.md` на скилл, без скриптов и зависимостей.

## Скиллы

| Скилл | Что делает | Триггеры |
|---|---|---|
| **humanize** | Очеловечивает русский текст, убирает следы нейросети (52 паттерна, HARD BANS, quad-pass аудит; режимы полная правка / аудит / точечно). | `/humanize`, `/оживи`, `/antidetector` |
| **story** | Усиливает готовый текст как историю (12 приёмов + бизнес-модуль для продающих текстов), правки в формате «Было → Предлагаю → Почему». | `/story`, `/сторителлинг`, `/корректор` |

Вместе образуют контент-конвейер: **story** усиливает историю → **humanize** вычищает следы ИИ → публикация.

## Установка

```bash
git clone https://github.com/cain66666/cain_skills.git /tmp/cain_skills
mkdir -p ~/.agents/skills
cp -r /tmp/cain_skills/humanize ~/.agents/skills/humanize
cp -r /tmp/cain_skills/story    ~/.agents/skills/story

# Cain (OpenClaw) и Hermes видят скиллы через симлинки:
for s in humanize story; do
  ln -sfn ../../.agents/skills/$s ~/.claude/skills/$s
  ln -sfn ../../.agents/skills/$s ~/.hermes/skills/$s
done
```

Одна реальная папка в `~/.agents/skills/<skill>/` + симлинки для Cain и Hermes.
Правишь `SKILL.md` один раз — обновляется у обоих.

## Структура

```
cain_skills/
├── humanize/SKILL.md
└── story/SKILL.md
```

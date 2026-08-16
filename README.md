# ie-specs-templates

Схема OpenSpec `epm-analytics-template` — шаблоны для генерации артефактов
постановки: `proposal.md`, `spec.md`, `design.md`, `tasks.md`.

Корень репозитория устроен как каталог схемы OpenSpec:

```
schema.yaml          описание артефактов и инструкций
templates/           шаблоны артефактов
```

## Подключение к store-репозиторию

Схема подключается submodule'ом в каталог схем store-репозитория — имя
каталога должно совпадать со значением `name` в `schema.yaml`:

```bash
git submodule add ssh://git@gitverse.ru:2222/integration_engine/ie-specs-templates.git \
    openspec/schemas/epm-analytics-template
```

и указывается в `openspec/config.yaml` store-репозитория:

```yaml
schema: epm-analytics-template
```

Обновление шаблонов в store:

```bash
git submodule update --remote openspec/schemas/epm-analytics-template
```

Настройка рабочего окружения (OpenSpec, предпросмотр mermaid и OpenAPI) —
см. [SETUP.md](./SETUP.md).

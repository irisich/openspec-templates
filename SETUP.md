# Настройка окружения для написания постановок (EPM)

Этот документ собирает всё, что нужно настроить коллегам, чтобы их окружение
для написания постановок (`change.md`, `proposal.md`, `spec.md`, `tasks.md` и т.п.
в `openspec/schemas/epm-analytics-template/templates`) совпадало с рабочим. Дополняется
по мере того, как всплывают новые нужные настройки/расширения.

## Чек-лист

- [ ] Установлен **OpenSpec**
      (см. раздел ниже)
- [ ] Установлено расширение VS Code **Markdown Preview Mermaid Support**
      (см. раздел ниже)
- [ ] Установлено расширение VS Code **Swagger Viewer**
      (см. раздел ниже)

## 1. Установка OpenSpec

Для работы с постановками в `openspec/schemas/...` (в т.ч. с шаблонами из
`epm-analytics-template/templates`) должен быть установлен OpenSpec.

<!-- TODO: добавить ссылку на инструкцию по установке -->

## 2. Рендеринг mermaid-диаграмм в предпросмотре Markdown

**Зачем:** шаблоны постановок используют mermaid-диаграммы (sequence, flowchart,
erDiagram, stateDiagram-v2) вместо PlantUML/Draw.io/картинок — они хранятся как
текст прямо в `.md` и должны отрисовываться в предпросмотре. Встроенный
Markdown Preview в VS Code (`Ctrl+Shift+V`) **не умеет** рендерить mermaid без
расширения — без него ```mermaid```-блоки показываются как обычный код.

**Расширение:** `bierner.markdown-mermaid` — "Markdown Preview Mermaid Support".
Встраивается в штатный предпросмотр VS Code, ничего не заменяет.

Установка через терминал:
```bash
code --install-extension bierner.markdown-mermaid
```

Либо вручную: `Ctrl+Shift+X` → найти "Markdown Preview Mermaid Support" → Install.

**Проверка:** открыть `openspec/schemas/epm-analytics-template/templates/change.md`,
нажать `Ctrl+Shift+V` — диаграммы в примерах (раздел "Изменение в архитектуре
сервиса" и др.) должны отрисовываться как схемы, а не как текст кода.

## 3. Просмотр OpenAPI/yml спецификаций (Swagger Preview)

**Зачем:** в разделе "Изменения в предоставляемом API" каждой постановки
указывается ссылка на OpenAPI/yml-файл с методами (см. `Ссылка на OpenAPI/yml`
в `change.md`). Чтобы смотреть и проверять такие файлы прямо в VS Code, не
выгружая их на внешний сервис, нужно расширение **Swagger Viewer**.

**Расширение:** `Arjun.swagger-viewer` — "Swagger Viewer".

Установка через терминал:
```bash
code --install-extension arjun.swagger-viewer
```

Либо вручную: `Ctrl+Shift+X` → найти "Swagger Viewer" → Install.

**Проверка:** открыть любой `.yml`/`.yaml`/`.json` файл с OpenAPI/Swagger-спецификацией и нажать `Shift+Alt+P` (или через Command Palette —
`Swagger: Open Preview`) — сбоку должна открыться отрисованная Swagger UI-страница с методами вместо голого текста.

<!-- Следующие пункты добавляем по мере обнаружения новых настроек -->

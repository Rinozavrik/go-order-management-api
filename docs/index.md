
# Учебная панель

## Цель

Научиться самостоятельно проектировать, писать, тестировать, профилировать и разворачивать production-oriented backend-сервисы на Go.

Фокус обучения:

- идиоматичный Go;
- стандартная библиотека;
- package boundaries;
- errors и `context.Context`;
- конкурентность и управление ресурсами;
- HTTP;
- PostgreSQL и MongoDB;
- Redis и брокеры сообщений;
- тестирование;
- profiling;
- observability;
- Docker и Kubernetes.

## Текущий этап

Этап 0 — подготовка репозитория и учебной среды.

## Текущий milestone

[[milestones/00-environment-and-module]]

## Текущая задача

Учебная часть Milestone 00:

- изучить Go module и package;
- разобраться с `package main`;
- создать первый исполняемый package;
- создать первый внутренний package;
- написать первую функцию;
- написать первый table-driven test;
- настроить базовый GitHub Actions workflow.

## Прогресс

- [x] Go установлен
- [x] Репозиторий клонирован
- [x] Go module инициализирован
- [x] Добавлен `AGENTS.md`
- [x] Создана структура учебной документации
- [x] `docs` открыт как Obsidian vault
- [x] Установлены Templater, Spaced Repetition, Dataview и Excalidraw
- [x] Добавлен `learning-process.md`
- [x] Добавлен `codex-prompts.md`
- [x] Репозиторий открыт в Codex
- [x] Codex корректно прочитал инструкции
- [x] Сделан первый инфраструктурный commit
- [x] Изменения отправлены в GitHub
- [ ] Разобрана ментальная модель Go module и package
- [ ] Понятно, как module path формирует import paths
- [ ] Понятна роль `package main`, `func main` и директории `internal`
- [ ] Создан исполняемый package в `cmd/app`
- [ ] Создан небольшой package внутри `internal`
- [ ] Написана первая функция и table-driven test
- [ ] `gofmt`, `go test ./...` и `go vet ./...` проходят
- [ ] Добавлен и успешно проходит базовый GitHub Actions workflow
- [ ] Код проверен Codex, существенные замечания исправлены
- [ ] Я могу своими словами объяснить module, package, import path и `internal`
- [ ] Учебная часть отправлена в GitHub отдельным логическим commit

## Навигация

### Организация обучения

- [[learning-process]]
- [[codex-prompts]]

### Текущий milestone

- [[milestones/00-environment-and-module]]

### Основные разделы

- [[questions]]
- [[concepts/index]]
- [[milestones/index]]
- [[reviews/index]]
- [[decisions/index]]

## Базовые проверки

```bash
gofmt -w .
go test ./...
go vet ./...
```

Для конкурентного кода:

```bash
go test -race ./...
```

## Ближайший следующий шаг

После инфраструктурного commit начать учебную часть Milestone 00:

- Go module;
- package;
- `package main`;
- базовая структура программы;
- первая функция;
- первый table-driven test.

## Правило обновления

Этот файл обновляется только когда:

- начат или завершён milestone;
- изменилась текущая задача;
- появился значимый review;
- изменился общий статус проекта.

Подробный учебный процесс описан в [[learning-process]].
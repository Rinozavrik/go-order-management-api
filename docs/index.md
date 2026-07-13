
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

Завершить подготовку среды и перейти к учебной части Milestone 00:

- проверить Go module;
- подключить Codex к репозиторию;
- проверить, что Codex понимает `AGENTS.md`;
- сделать первый инфраструктурный commit;
- начать изучение Go modules и packages.

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
- [ ] Репозиторий открыт в Codex
- [ ] Codex корректно прочитал инструкции
- [ ] Сделан первый инфраструктурный commit
- [ ] Изменения отправлены в GitHub

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
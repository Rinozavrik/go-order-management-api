# Промпты для Codex

## Назначение

Короткая шпаргалка для основных сценариев работы с Codex.

Перед задачей Codex должен учитывать:

- `AGENTS.md`;
- текущий milestone;
- актуальное состояние репозитория.

## 1. Проверить понимание проекта

```text
Read AGENTS.md, docs/index.md, docs/learning-process.md,
and the current milestone.

Do not modify files.

Summarize:
1. the project purpose;
2. the current milestone;
3. the learner and Codex responsibilities;
4. the current constraints;
5. what must not be implemented yet.
```

## 2. Подготовиться к моей реализации

```text
Read AGENTS.md and the current milestone.

Do not modify files.
Do not provide a complete implementation.

Explain:
1. which Go concepts I need;
2. which existing files are relevant;
3. which files I may need to create;
4. which acceptance criteria will be checked;
5. which premature abstractions must be avoided.
```

## 3. Провести code review

```text
Read AGENTS.md and the current milestone.

Review my uncommitted changes.
Do not modify files.

Run:
- go test ./...
- go vet ./...
- gofmt checks.

If concurrent code is present, also run:
- go test -race ./...

Classify findings as:
- blocking;
- important;
- improvement;
- question.

For each finding explain:
1. what is wrong;
2. why it matters;
3. how an idiomatic Go developer would reason about it.

Pay attention to correctness, errors, context, resources,
goroutine lifecycle, package boundaries, tests,
and unnecessary abstractions.
```

## 4. Исправить конкретные замечания

```text
Read AGENTS.md and the current milestone.

Apply only findings <NUMBERS> from the latest review.

Do not modify unrelated files.
Do not introduce new dependencies or abstractions.

After editing, run:
- gofmt -w .
- go test ./...
- go vet ./...

If concurrent code changed, also run:
- go test -race ./...

Summarize the exact changes and check results.
```

## 5. Добавить карточки в concept note

```text
Read <CONCEPT_NOTE_PATH>.

Append 3–5 flashcards under:

## Карточки для повторения

Use the format:

Question::Answer

Requirements:
- test understanding, trade-offs and failure modes;
- avoid trivial syntax questions;
- avoid duplicates;
- keep answers concise;
- use Russian, preserving Go terms in English;
- do not modify other sections.
```

## 6. Создать review note

```text
Read the latest review and related code changes.

Create:

docs/reviews/<FILE_NAME>.md

Include only:
- what was reviewed;
- real findings;
- why they matter;
- how they were fixed, if fixed;
- non-idiomatic Go patterns;
- lessons learned;
- related concept notes.

Do not copy the full Codex response.
Do not invent conclusions.
Use Russian.
```

## 7. Обновить `index.md`

```text
Read docs/index.md, the current milestone,
and the current repository state.

Update only docs/index.md.

Rules:
- mark only actually completed items;
- do not invent progress;
- do not mark understanding without user confirmation;
- update the current task and milestone only when they changed;
- keep detailed findings out of index.md.
```

## 8. Проверить готовность milestone

```text
Read AGENTS.md, docs/index.md, the current milestone,
relevant reviews, and the repository state.

Do not modify files.

Evaluate:
1. technical criteria;
2. architectural criteria;
3. remaining learning gaps.

Return:
- completed criteria;
- incomplete criteria;
- blockers;
- recommended final actions.

Do not declare the milestone complete automatically.
```

## Правила использования

- Не использовать команду `Fix everything`.
- Просить менять только конкретные findings.
- Не передавать Codex подтверждение понимания темы.
- Использовать самый узкий промпт, достаточный для задачи.
- Не запускать полный review репозитория для мелкой правки.

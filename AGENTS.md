# AGENTS.md

## Project purpose

This repository is a learning project for becoming capable of building production-ready backend services in Go.

The learner is a Senior Node.js/NestJS developer with production experience in TypeScript, PostgreSQL, Redis, RabbitMQ, Docker, Kubernetes, REST APIs, and distributed systems.

The goal is not merely to produce working code. The goal is to learn idiomatic Go, its standard library, runtime model, tooling, testing practices, and production engineering.

## General working rules

- Prefer idiomatic Go over patterns copied from Node.js, NestJS, Java, or C#.
- Prefer the Go standard library when it is sufficient.
- Do not introduce frameworks or third-party dependencies without a concrete reason.
- Do not over-engineer the project before the current milestone requires it.
- Do not create abstractions only because they may become useful later.
- Keep dependencies explicit.
- Prefer composition over inheritance-like abstractions.
- Keep APIs small and readable.
- Format all Go code with `gofmt`.

## Architecture rules

- Do not create a `controllers/services/repositories` structure merely by analogy with NestJS.
- Define package boundaries based on domain responsibilities and dependency direction.
- Do not introduce a generic repository.
- Do not introduce a dependency injection container.
- Do not introduce a service layer without an actual orchestration or business-logic responsibility.
- Do not define an interface when there is only one implementation unless there is a concrete consumer-side reason.
- Prefer consumer-defined, small interfaces.
- Avoid global mutable state.

## Error handling

- Handle errors explicitly.
- Do not use `panic` for ordinary application errors.
- Add useful context with `fmt.Errorf("...: %w", err)`.
- Preserve errors for `errors.Is` and `errors.As` when appropriate.
- Do not log the same error repeatedly at every layer.

## Context and resources

- Pass `context.Context` as the first parameter when cancellation, deadlines, or request scope are relevant.
- Do not store `context.Context` in structs.
- Close resources correctly.
- Check errors returned by resource cleanup when they can affect correctness.
- Do not start a goroutine without a clear owner, termination condition, and error-handling strategy.
- Check for goroutine leaks and blocked channel operations.

## Concurrency

When reviewing concurrent code, inspect:

- race conditions;
- shared mutable state;
- mutex ownership;
- channel ownership;
- channel closure responsibility;
- cancellation;
- goroutine lifecycle;
- deadlocks;
- unbounded concurrency;
- backpressure.

Use the race detector when concurrency is involved:

```bash
go test -race ./...
```

## Testing

- Use table-driven tests when they improve clarity.
- Test observable behavior rather than implementation details.
- Avoid mocks when simple fakes or real lightweight dependencies are clearer.
- Do not introduce interfaces solely to satisfy a mocking framework.
- Run:

```bash
go test ./...
go vet ./...
```

## Review mode

When asked to review code:

1. Check correctness first.
2. Identify compilation and runtime errors.
3. Check idiomatic Go.
4. Check error handling.
5. Check context propagation.
6. Check resource ownership and cleanup.
7. Check concurrency and goroutine lifecycle.
8. Check package boundaries and API clarity.
9. Check testability.
10. Check unnecessary abstractions.
11. Discuss performance only where it materially matters.

Do not approve code merely because it works.

Classify findings as:

- blocking;
- important;
- improvement;
- question.

For every finding, explain:

- what is wrong;
- why it matters;
- how an idiomatic Go developer would reason about it.

## Learning mode

Do not immediately implement complete exercise solutions unless explicitly requested.

For a new exercise:

1. Explain the goal.
2. State constraints.
3. Define acceptance criteria.
4. Let the learner attempt the implementation.
5. Review the submitted solution.
6. Provide a complete reference solution only after the attempt or an explicit request.

When useful, compare the concept with Node.js or TypeScript, but explicitly identify where the analogy breaks down.

## Current technology direction

The project may eventually use:

- Go;
- `net/http` and later possibly `chi`;
- PostgreSQL with `pgx`;
- MongoDB;
- Redis;
- RabbitMQ or NATS;
- Docker Compose;
- `log/slog`;
- OpenTelemetry;
- Prometheus.

Do not add these technologies before the corresponding milestone.

---
description: Generate maintainable API tests (Python-first, async-ready)
model: claude-sonnet-4-5
---

Generate comprehensive API tests for the endpoint below.

## Target

$ARGUMENTS

## Framework Selection Rules

1. If project is Python, default to `pytest`.
2. For async APIs, use `pytest-asyncio` + `httpx.AsyncClient`.
3. Only use JS tooling (Vitest/Jest/Supertest) when explicitly requested.

## Python Test Strategy

### 1) Test layers
- Unit tests for validators/services.
- Integration tests for full route behavior.
- Security tests for auth and permission boundaries.

### 2) Core scenarios
- Happy path (valid request/expected response).
- Validation failures (schema/type/missing fields).
- Authentication and authorization failures.
- Error paths (upstream timeout, DB failure, unexpected exception).
- Concurrency or idempotency edge cases when relevant.

### 3) Test quality requirements
- Arrange-Act-Assert structure.
- Independent tests with clean fixtures.
- Deterministic assertions and explicit status/body checks.

## Output Requirements

Generate:
1. `tests/test_<endpoint>.py` with complete scenarios.
2. Shared fixtures (`conftest.py`) as needed.
3. Mock/stub guidance for external dependencies.
4. Command examples:
   - `uv run pytest -q`
   - `uv run pytest --maxfail=1 --disable-warnings`

Also apply the shared checklist in `.claude/commands/shared/api-python-baseline.md`.

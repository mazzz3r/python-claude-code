---
description: Create a production-ready API endpoint (Python-first, stack-adaptive)
model: claude-sonnet-4-5
---

Create a new API endpoint with modern best practices. Prefer Python-first output by default.

## Requirements

API Endpoint: $ARGUMENTS

## Framework Selection Rules

1. If the user has a Python backend (FastAPI/Starlette/Django Ninja/Flask async), generate Python.
2. If no stack is specified, default to **FastAPI + Pydantic v2**.
3. If user explicitly asks for Next.js/TypeScript, generate that stack instead.

## Python-First Implementation Guidelines

### 1) Endpoint structure
- Use router-based structure (e.g. `app/api/routes/<resource>.py`).
- Keep route handlers thin; call service layer for business logic.

### 2) Validation and typing
- Use Pydantic v2 request/response models.
- Validate early before DB/network calls.
- Use explicit return types and strict typing (mypy-friendly).

### 3) Async and reliability
- Use `async def` for handlers when I/O is involved.
- Use async DB/http clients where applicable.
- Add timeout + retry/backoff for outbound requests.
- Avoid blocking calls in event loop paths.

### 4) Security and error handling
- Include authn/authz hook points.
- Return consistent error envelopes.
- Use safe error messages for clients and detailed server logs.

### 5) Response contract
```json
{ "success": true, "data": {...} }
{ "success": false, "error": {"code": "...", "message": "...", "details": {...}} }
```

## Output Requirements

Generate:
1. Route/handler file.
2. Pydantic models.
3. Service layer stub.
4. Error handling utility or pattern.
5. Minimal usage example (`curl` + Python client).
6. Notes on how to run lint/type checks (`uv run ruff check .`, `uv run mypy .`).

Also apply the shared checklist in `.claude/commands/shared/api-python-baseline.md`.

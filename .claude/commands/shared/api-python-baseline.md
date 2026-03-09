# Shared API Baseline (Python-first)

Use this checklist in `/api-new`, `/api-test`, and `/api-protect` outputs.

## Quality Baseline

- Use Python 3.11+ typing (`typing`, `TypedDict`/Pydantic models, no `Any` unless justified).
- Keep handlers thin; move business logic into service functions.
- Ensure all external I/O has timeout + retry/backoff strategy.
- Avoid blocking calls inside async routes/services.
- Return consistent response envelopes and structured errors.

## Validation Baseline

- Validate request payloads with Pydantic v2 before calling DB/external APIs.
- Validate query/path parameters explicitly.
- Return clear field-level validation errors.

## Security Baseline

- Authentication first; authorization second (least privilege).
- Sanitize user-controlled input and constrain payload size.
- Include rate-limit strategy recommendations.
- Avoid leaking stack traces or sensitive internals in responses.

## Async Reliability Baseline

- Use async clients/drivers where possible.
- Make cancellation-safe await chains.
- Set connection and request timeouts.
- Handle transient failures with bounded retries.

## Testing Baseline

- Include happy-path, validation-path, auth-path, and failure-path tests.
- Prefer `pytest` + `pytest-asyncio` + `httpx` for async API tests.
- Keep tests independent and deterministic.

---
description: Add authentication, authorization, and API hardening (Python-first)
model: claude-sonnet-4-5
---

Secure the specified API endpoint with authentication, authorization, validation, and abuse controls.

## Target API Route

$ARGUMENTS

## Framework Selection Rules

1. Default to Python implementations (FastAPI/Starlette patterns).
2. Use stack-specific alternatives only when explicitly requested.

## Security Layers to Implement

### 1) Authentication (who are you?)
- Validate token/session/API key.
- Handle expired/invalid credentials with 401.

### 2) Authorization (what can you do?)
- Enforce role/scope/resource ownership with 403.
- Apply least privilege and explicit permission checks.

### 3) Input safety
- Validate request payload and parameters with Pydantic v2.
- Constrain payload size and sanitize user-controlled input.

### 4) Abuse protection
- Add rate-limit strategy (user + IP where possible).
- Define retry-after behavior and clear 429 responses.

### 5) Observability
- Log auth failures, permission denials, and suspicious patterns.
- Avoid logging secrets or PII in plaintext.

## Output Requirements

Generate:
1. Protected route implementation.
2. Reusable auth/permission helpers.
3. Standardized auth/error responses.
4. Minimal tests for 401/403/429 and valid-auth success.
5. Deployment notes (env vars, key rotation, clock skew handling).

Also apply the shared checklist in `.claude/commands/shared/api-python-baseline.md`.

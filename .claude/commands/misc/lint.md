---
description: Run linting and fix code quality issues (Python-first with uv, ruff, and mypy)
model: claude-sonnet-4-5
---

Run linting and fix code quality issues in the codebase.

## Target

$ARGUMENTS

## Lint Strategy for Python Developers

### 1. **Run the Core Commands**

```bash
# Lint
uv run ruff check .

# Auto-fix lint issues
uv run ruff check . --fix

# Format
uv run ruff format .

# Type-check (strict)
uv run mypy .

# Full local quality gate
uv run ruff check . --fix && uv run ruff format . && uv run mypy .
```

### 2. **Ruff Focus Areas**

- Unused imports and variables
- Bug-prone patterns (flake8-bugbear rules)
- Import sorting (`I` rules)
- Annotation quality (`ANN` rules)
- Modern Python upgrades (`UP` rules)

### 3. **Mypy Focus Areas**

- Missing type annotations
- Untyped function calls in typed contexts
- Unsafe Optional handling
- `Any` leaks through external APIs
- Invalid Pydantic model usage in typed code

### 4. **Pydantic v2 Guidance**

- Use explicit field types everywhere
- Prefer `BaseModel` + `Field(...)` for constraints
- Keep validators typed and deterministic
- Configure `mypy` with `pydantic.mypy` plugin

### 5. **Fix Priority**

**High Priority**
- Type errors that can hide runtime bugs
- Validation gaps on external input
- Incorrect Optional / None handling

**Medium Priority**
- Annotation coverage gaps
- Lint warnings affecting readability/maintainability

**Low Priority**
- Pure formatting nits already covered by `ruff format`

### 6. **What to Produce**

1. Lint report (what failed and why)
2. Auto-fix summary (what `ruff --fix` changed)
3. Manual fix list (type/logic issues)
4. Suggested config improvements

Always preserve behavior while improving type safety and consistency.

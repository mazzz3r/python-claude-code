# Edmund's Claude Code Setup

My personal Claude Code configuration for productive Python development. This plugin provides **14 slash commands** and **11 specialized AI agents** to supercharge your development workflow, now with a Python-first setup (uv + ruff + mypy + Pydantic v2).

## Quick Install

```bash
# Step 1: Add the marketplace
/plugin marketplace add edmund-io/edmunds-claude-code

# Step 2: Install the plugin
/plugin install edmunds-claude-code
```

## What's Inside

### 📋 Development Commands (7)

- `/new-task` - Analyze code for performance issues
- `/code-explain` - Generate detailed explanations
- `/code-optimize` - Performance optimization
- `/code-cleanup` - Refactoring and cleanup
- `/feature-plan` - Feature implementation planning
- `/lint` - Linting and fixes
- `/docs-generate` - Documentation generation

### 🔌 API Commands (3)

- `/api-new` - Create new API endpoints
- `/api-test` - Test API endpoints
- `/api-protect` - Add protection & validation

### 🎨 UI Commands (2)

- `/component-new` - Create React components
- `/page-new` - Create Next.js pages

### 💾 Supabase Commands (2)

- `/types-gen` - Generate TypeScript types
- `/edge-function-new` - Create Edge Functions

### 🤖 Specialized AI Agents (11)

**Architecture & Planning**
- **tech-stack-researcher** - Technology choice recommendations with trade-offs
- **system-architect** - Scalable system architecture design
- **backend-architect** - Backend systems with data integrity & security
- **frontend-architect** - Performant, accessible UI architecture
- **requirements-analyst** - Transform ideas into concrete specifications

**Code Quality & Performance**
- **refactoring-expert** - Systematic refactoring and clean code
- **performance-engineer** - Measurement-driven optimization
- **security-engineer** - Vulnerability identification and security standards

**Documentation & Research**
- **technical-writer** - Clear, comprehensive documentation
- **learning-guide** - Teaching programming concepts progressively
- **deep-research-agent** - Comprehensive research with adaptive strategies

## Installation

### From GitHub (Recommended)

```bash
# Add marketplace
/plugin marketplace add edmund-io/edmunds-claude-code

# Install plugin
/plugin install edmunds-claude-code
```

### From Local Clone (for development)

```bash
git clone https://github.com/edmund-io/edmunds-claude-code.git
cd edmunds-claude-code

# Add as local marketplace
/plugin marketplace add /path/to/edmunds-claude-code

# Install plugin
/plugin install edmunds-claude-code
```

## Best For

- Python back-end developers
- Projects using `uv` for environment and dependency management
- Teams enforcing `ruff` + `mypy --strict`
- Pydantic v2 codebases with strong typing discipline
- Full-stack engineers who still want the existing web-focused command set

## Usage Examples

### Planning a Feature

```bash
/feature-plan
# Then describe your feature idea
```

### Creating an API

```bash
/api-new
# Claude will scaffold a complete API route with types, validation, and error handling
```

### Research Tech Choices

Just ask Claude questions like:
- "Should I use WebSockets or SSE?"
- "How should I structure this database?"
- "What's the best library for X?"

The tech-stack-researcher agent automatically activates and provides detailed, researched answers.

## Philosophy

This setup emphasizes:
- **Type Safety**: Comprehensive Python typing with strict static checks
- **Python Tooling**: `uv`, `ruff`, and `mypy` as the default quality workflow
- **Validation Quality**: Pydantic v2 patterns for robust input/output models
- **Productivity**: Reduces repetitive scaffolding
- **Research**: AI-powered tech decisions with evidence

## Requirements

- Claude Code 2.0.13+
- Works with any project (optimized for Next.js + Supabase)

## Customization

After installation, you can customize any command by editing files in `.claude/commands/` and `.claude/agents/`.

## Contributing

Feel free to:
- Fork and customize for your needs
- Submit issues or suggestions
- Share your improvements

## License

MIT - Use freely in your projects

## Author

Created by Edmund

---

**Note**: This is my personal setup that I've refined over time. Commands are optimized for Next.js + Supabase workflows but work great with any modern web stack.

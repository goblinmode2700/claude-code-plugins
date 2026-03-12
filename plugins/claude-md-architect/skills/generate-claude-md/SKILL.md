---
description: Analyze a codebase and generate a production-grade CLAUDE.md file. Creates comprehensive AI agent governance configs with architecture constraints, session modes, sprint protocols, and tool permissions based on actual project patterns.
---

You are a CLAUDE.md architect. Your job is to analyze the current codebase and generate a production-grade CLAUDE.md that will govern AI agent behavior for this specific project.

## Analysis Protocol

First, perform deep codebase reconnaissance:

1. **Stack detection**: Read package.json, requirements.txt, Cargo.toml, go.mod, etc. Identify ALL frameworks, languages, and tools.
2. **Architecture mapping**: Scan directory structure. Identify the layering pattern (MVC, hexagonal, feature-based, monorepo, etc.).
3. **Convention extraction**: Read 3-5 representative source files. Extract naming conventions (camelCase vs snake_case), import patterns, error handling patterns, logging patterns.
4. **Test patterns**: Find test files. Identify framework (jest, pytest, vitest, etc.), naming convention (*.test.ts, *_test.go, test_*.py), and coverage expectations.
5. **CI/CD detection**: Read .github/workflows/, Dockerfile, docker-compose.yml, Makefile. Understand the build and deploy pipeline.
6. **Existing governance**: Check for existing CLAUDE.md, .cursorrules, .github/copilot-instructions.md, or similar files.
7. **Git conventions**: Read recent git log messages. Extract commit message format and branching strategy.
8. **Sensitive files**: Identify .env patterns, secret management (Doppler, Vault, etc.), and files that must never be modified.

## CLAUDE.md Generation

Generate a CLAUDE.md with these sections (adapt to what's relevant for this codebase):

### 1. Project Identity Block
```
# [Project Name]
One-line description of what this is and its current state.
```

### 2. Architecture Constraints
- Tech stack with exact versions where it matters
- Directory structure explanation (what goes where)
- Naming conventions (with examples from the actual codebase)
- Import ordering rules
- Error handling patterns (extracted from existing code)

### 3. Development Rules
- How to run the project locally
- How to run tests (exact commands)
- How to build for production
- Database migration patterns (if applicable)
- Environment variable conventions

### 4. Code Style Rules
- Extracted from actual code, not generic guidelines
- Formatting tool and config (prettier, black, rustfmt, etc.)
- Linting rules and how to run them
- Type strictness expectations

### 5. Git Conventions
- Commit message format (extracted from git log)
- Branch naming convention
- PR process if detectable

### 6. Guardrails (Critical)
- Files/directories that should NEVER be modified without asking
- Patterns that should NEVER be introduced
- Security-sensitive areas
- Performance-critical paths
- Breaking change boundaries (public APIs, database schemas)

### 7. Testing Requirements
- Minimum expectations (unit tests for new code, integration tests for APIs, etc.)
- How to run specific test suites
- Test file location and naming convention

## Output Rules

- Be SPECIFIC. Reference actual files, actual patterns, actual conventions from THIS codebase.
- Do NOT include generic advice. Every line should be derived from codebase analysis.
- Use code blocks with real examples from the project.
- If you find conflicting patterns, note the conflict and recommend the dominant pattern.
- Keep it under 200 lines. Dense, not verbose.
- Write the CLAUDE.md content directly — do not explain what you're going to do, just do it.

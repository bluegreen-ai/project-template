# Project Guidelines for Claude Code

## Project Type
[Describe: Web app, CLI tool, library, API, etc.]

## Tech Stack
- **Language**: [e.g., TypeScript, Python, etc.]
- **Framework**: [e.g., Express, FastAPI, etc.]
- **Database**: [e.g., PostgreSQL, MongoDB, etc.]
- **Testing**: [e.g., Jest, pytest, etc.]

## Code Style & Conventions

### Naming
- Files: `kebab-case.ts`
- Classes: `PascalCase`
- Functions: `camelCase`
- Constants: `UPPER_SNAKE_CASE`

### File Organization
```
src/
├── components/    # Reusable components
├── services/      # Business logic
├── utils/         # Helper functions
└── types/         # Type definitions
```

## Development Rules

### Type Safety
- [ ] Use strict TypeScript (no `any` without justification)
- [ ] All functions must have return type annotations
- [ ] All parameters must have type annotations

### Testing
- [ ] Unit tests required for all new features
- [ ] Integration tests for critical flows
- [ ] Minimum 80% coverage

### Documentation
- [ ] Update README when adding features
- [ ] Document complex algorithms
- [ ] Add JSDoc comments for public APIs

### Git Workflow
- [ ] Meaningful commit messages
- [ ] No commits with failing tests
- [ ] No commits with linting errors

## Common Gotchas
[List specific issues Claude should watch for in your project]

Example:
- Don't forget to update the schema when adding database fields
- Always use parameterized queries (never string concatenation)
- Check for null before accessing nested properties

## External Resources
[Links to important documentation]

- Project docs: [URL]
- API reference: [URL]
- Design system: [URL]

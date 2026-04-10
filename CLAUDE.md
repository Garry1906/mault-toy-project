# Claude Code — Project Rules

## Testing Enforcement

### TDD Workflow (Non-Negotiable)
1. Write the test FIRST — see it fail (Red)
2. Write minimal code to pass — see it pass (Green)
3. Refactor — tests still pass (Refactor)

### Testing Pyramid
- **Unit Tests**: No I/O, no framework imports, stub injection only
- **Integration Tests**: Framework mocking allowed, real orchestration
- **Behavioral Tests**: Detector perception — "Does it SEE the files?"
- **Adapter Tests**: Real I/O in temp directories, no mocks

### Mock Tax Rule
If test file LOC > 2x source file LOC:
- DELETE the unit test
- Write an integration test instead
- Never try to "fix" or "reduce" the unit test

### Pre-commit Hooks
- NEVER use `--no-verify` to skip hooks
- Wait for hooks to pass before declaring work complete
- Fix failures, do not bypass them

### Test Locations (this project)
- Unit tests: `tests/unit/` (NO framework imports)
- Integration tests: `tests/integration/`
- Behavioral tests: `tests/behavioral/`

### Test Naming (this project)
- TypeScript: `*.test.ts` / `*.spec.ts`
- Run tests: `npm test`

### Before Every Change
1. Check if tests exist for the file being modified
2. If no tests exist, write them FIRST
3. Run the full test suite before declaring complete

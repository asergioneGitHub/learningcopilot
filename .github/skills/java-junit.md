# Skill: Java JUnit 5 Testing

Source: adapted from `github/awesome-copilot` (`skills/java-junit/SKILL.md`)

## Purpose
Write effective, maintainable JUnit 5 tests for Java code with clear structure, isolation, and coverage.

## References
- `.github/copilot-instructions.md`
- `.github/copilot-context.md`

## Required Inputs
- Target class/module
- Expected behaviors and edge cases
- Whether test type is unit, integration, or mixed
- Dependencies to mock or keep real

## JUnit 5 Checklist

### Setup
- Keep tests in `src/test/java`.
- Ensure JUnit 5 dependencies are available (`junit-jupiter-api`, `junit-jupiter-engine`, `junit-jupiter-params`).
- Use build-tool test command (`mvn test` / `gradle test`).

### Test Structure
- Name classes with `*Test` suffix.
- Use descriptive test names (e.g., `method_shouldExpectedBehavior_whenScenario`).
- Follow Arrange-Act-Assert pattern.
- Use `@BeforeEach` / `@AfterEach` for per-test setup/teardown.
- Keep each test focused on one behavior and independent of order.

### Parameterized Tests
- Use `@ParameterizedTest` for data-driven checks.
- Select source type by need:
  - `@ValueSource` for simple literals.
  - `@CsvSource` / `@CsvFileSource` for tabular data.
  - `@MethodSource` for richer generated arguments.
  - `@EnumSource` for enum variants.

### Assertions
- Use JUnit assertions (`assertEquals`, `assertTrue`, `assertThrows`, etc.).
- Use `assertAll` for grouped related checks.
- Provide clear failure messages where useful.

### Mocking and Isolation
- Use Mockito for dependency isolation (`@Mock`, `@InjectMocks`) in unit tests.
- Prefer interfaces/ports for mock-friendly design.
- Keep integration tests for wiring and persistence behavior.

### Organization
- Use `@Tag` for grouping (`fast`, `integration`, etc.).
- Use `@Nested` for scenario grouping when it improves readability.
- Use `@Disabled` only with explicit reason.

## Done Criteria
- Tests are deterministic, readable, and meaningful.
- Happy path + edge cases + failure behavior covered.
- Test type is appropriate (unit vs integration).
- Test run results are reported.

## Prompt Template
Apply skill java-junit.
Target: `<class/module>`
Test scope: `<unit/integration/mixed>`
Behaviors: `<list>`
Edge cases: `<list>`
Use JUnit 5 best practices, add/adjust tests, run test checks, and report outcomes.

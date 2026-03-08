# Skill: Angular Testing

Source: project conventions from `.github/copilot-instructions.md`

## Purpose
Write effective, maintainable Angular tests with clear structure, isolation, and coverage.

> **Targets Angular 17+ (standalone-first, provider-based testing, signals).** Patterns below reflect Angular 21 conventions. Avoid deprecated `NgModule`-based testing imports (`RouterTestingModule`, `HttpClientTestingModule`).

> **Note:** This skill intentionally overlaps with `.github/copilot-instructions.md` so it remains self-contained and portable across repositories.

## References
- `.github/copilot-instructions.md`
- `.github/copilot-context.md`

## Required Inputs
- Target component/service/module
- Expected behaviors and edge cases
- Whether test type is unit, integration, or e2e
- Dependencies to mock or keep real

## Angular Testing Checklist

### Setup
- Keep tests co-located with source files as `*.spec.ts`.
- Ensure test runner is configured (Karma/Jasmine or Jest).
- Use `ng test` to run tests.

### Component Tests
- Use `TestBed.configureTestingModule` with standalone component imports and `providers` array — no `NgModule` declarations.
- Use `ComponentFixture` and `DebugElement` for DOM interaction.
- Test presentational components with different `@Input()` / input signal combinations.
- Test smart components with mocked services injected via `providers`.
- Verify `@Output()` / output signal event emissions with `spy` or `subscribe`.
- Use `fakeAsync` / `tick` or `waitForAsync` for async rendering.

### Service Tests
- Inject services via `TestBed.inject()`.
- Use `provideHttpClient()` + `provideHttpClientTesting()` (not deprecated `HttpClientTestingModule`).
- Use `HttpTestingController` to verify request method, URL, headers, and body.
- Flush responses and assert transformed results.
- Test error paths by flushing error responses.

### Routing Tests
- Use `provideRouter()` with test route configs (not deprecated `RouterTestingModule`).
- Test route guards by mocking auth/permission services and verifying `canActivate` / `canDeactivate` outcomes.
- Test resolvers by verifying pre-fetched data availability.
- Use `RouterTestingHarness` for navigation-driven component tests.

### State and Reactivity
- **Signals (preferred):** Test signal reads, computed values, and effects directly. Use `TestBed.flushEffects()` when testing effect side-effects.
- **RxJS (when used):** Test observable chains with marble testing or `subscribe` + `done` callback.
- Keep state approach consistent within a feature — do not mix signals and RxJS in the same feature's tests.

### Mocking and Isolation
- Mock external services with `jasmine.createSpyObj` or Jest mocks.
- Use `NO_ERRORS_SCHEMA` or `CUSTOM_ELEMENTS_SCHEMA` sparingly — prefer shallow component stubs.
- Mock `ActivatedRoute` params/queryParams for route-dependent components.
- Use `of()` / `throwError()` for observable mocks.

### Organization
- Group related tests with `describe` blocks.
- Use clear test names: `it('should <expected behavior> when <scenario>')`.
- Keep each test focused on one behavior and independent of execution order.
- Use `beforeEach` for shared setup; avoid shared mutable state between tests.

## Done Criteria
- Tests are deterministic, readable, and meaningful.
- Happy path + edge cases + error behavior covered.
- Test type is appropriate (unit vs integration vs e2e).
- Test run results are reported.

## Prompt Template
Apply skill angular-testing.
Target: `<component/service/module>`
Test scope: `<unit/integration/e2e>`
Behaviors: `<list>`
Edge cases: `<list>`
Use Angular testing best practices, add/adjust tests, run checks, and report outcomes.

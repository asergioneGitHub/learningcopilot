# Skill: Java Spring Boot Best Practices

Source: adapted from `github/awesome-copilot` (`skills/java-springboot/SKILL.md`)

## Purpose
Apply practical Spring Boot best practices while staying aligned with this repository's governance and layered architecture.

> **Note:** This skill intentionally overlaps with `.github/copilot-instructions.md` so it remains self-contained and portable across repositories.

## References
- `.github/copilot-instructions.md`
- `.github/copilot-context.md`

## Core Principles
- Use feature-oriented package organization.
- Keep dependencies explicit with constructor injection and `private final` fields.
- Keep controllers transport-focused, services business-focused, repositories persistence-focused.
- Prefer DTOs at API boundaries; never expose JPA entities directly.

## Checklist

### Project Setup
- Use Maven/Gradle with Spring Boot starters.
- Keep module/package naming clear and domain-oriented.

### Configuration
- Externalize configuration in `application.properties`/`application.yml`.
- Use profiles (`dev`, `test`, `prod`) for environment-specific settings.
- Bind typed config where useful (`@ConfigurationProperties`).
- Never hardcode secrets.

### Web Layer
- Design consistent REST endpoints.
- Validate request DTOs with Bean Validation (`@Valid`, `@NotNull`, `@Size`, etc.).
- Use global exception handling (`@ControllerAdvice`) and standardized error payload.

### Service Layer
- Keep business logic in `@Service` classes.
- Keep services stateless when possible.
- Use `@Transactional` at the most granular level that preserves consistency.

### Data Layer
- Prefer Spring Data repositories (`JpaRepository`/`CrudRepository`).
- Use derived queries first; use `@Query` for complex reads.
- Use projections/DTO queries when only partial data is needed.

### Logging
- Use SLF4J with parameterized messages.
- Keep logs actionable and avoid sensitive data.

### Testing
- Add unit tests for service logic (JUnit + mocks).
- Add integration tests for endpoints/repositories (`@SpringBootTest`, `@WebMvcTest`, `@DataJpaTest` where applicable).
- Prefer regression tests for bug fixes.

### Security
- Enforce authentication/authorization where required.
- Ensure secure credential handling and password hashing where applicable.
- Validate/sanitize inputs and avoid unsafe query patterns.

## Done Criteria
- Architecture boundaries respected.
- Validation, error handling, and logging are consistent.
- Tests updated and passing.
- Docs and API contract updates included where applicable.

## Prompt Template
Apply skill java-springboot.
Task: `<describe task>`
Constraints: `<api compatibility, security, performance>`
Implement using Spring Boot best practices above, update tests/docs, run checks, and provide risk/impact summary.

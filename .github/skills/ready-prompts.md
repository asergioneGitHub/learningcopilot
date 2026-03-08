# Ready Prompts

Use these as copy-paste starters. Replace placeholders in `<...>`.

## 1) New Backend Endpoint (Create)
Apply skill backend-api.
Implement `POST /api/v1/<resource>`.
Request DTO: `<fields + validation rules>`.
Response DTO: `<fields>`.
Business rules: `<rules>`.
Security rules: `<auth/permissions>`.
Keep layered boundaries strict, add unit + integration tests, update OpenAPI docs, run checks, and provide risk/impact summary.

## 2) New Backend Endpoint (Read with Filters)
Apply skill backend-api.
Implement `GET /api/v1/<resource>` with query params `<filters>` and pagination `<page,size,sort>`.
Define validation for query params, service-level filtering rules, repository query strategy, and response DTO.
Add tests for happy path, invalid params, and empty result behavior.

## 3) Backend Bug Fix (Production Defect)
Apply skill backend-bugfix.
Bug summary: `<symptom>`.
Expected behavior: `<expected>`.
Repro steps: `<steps or failing test>`.
Scope limits: `<what not to change>`.
Find root cause, implement minimal cohesive fix, add regression test, run checks, and report residual risk.

## 4) Backend Refactor (Service Cleanup)
Apply skill backend-refactor.
Target: `<service/class list>`.
Goal: reduce duplication and improve readability.
Non-goals: behavior changes, API contract changes.
Refactor in small steps, preserve behavior, update tests, run checks, and summarize impact.

## 5) Backend Validation Hardening
Apply skill backend-api.
Harden validation for `<endpoint>`.
Add Bean Validation constraints to request DTOs, validate at controller entry with `@Valid`, and standardize validation error responses.
Add integration tests for invalid payload cases and verify error structure `{ error, message, details, timestamp }`.

## 6) Frontend Feature (New Screen)
Apply skill frontend-feature.
Feature: `<name>`.
User flow: `<steps>`.
Routes: add/update `<route>` with guard/resolver requirements.
API calls: `<endpoints>`.
Validation/error/loading behavior: `<rules>`.
Implement using smart/presentational split, consistent state approach, tests, and build verification.

## 7) Frontend + Backend Contract Sync
Apply skill contract-sync.
Contract change: `<field added/renamed/removed>`.
Affected endpoints: `<list>`.
Frontend consumers: `<components/services>`.
Compatibility approach: `<additive/deprecation/breaking approved>`.
Update backend, OpenAPI docs, frontend types/services/tests, and list explicit follow-ups if any.

## 8) Safe Schema Migration
Apply skill migration-rollout.
Migration intent: `<schema/data change>`.
Affected tables/entities: `<list>`.
Risk profile: `<low/medium/high + why>`.
Constraints: `<downtime/compatibility window>`.
Provide expand/contract plan, rollback strategy, backup awareness note, test updates, and go/no-go checkpoint before risky steps.

## 9) Security Review on Sensitive Change
Apply skill security-review.
Target: `<endpoint/feature>` touching auth/permissions/data exposure.
Auth model: `<current auth setup>`.
Data sensitivity: `<PII/financial/internal>`.
Known threats: `<scenarios or "none known">`.
Audit using security checklist, implement required fixes, add tests for unauthorized/forbidden and sensitive-data leakage prevention, run checks, and report findings with residual risk.

## 10) Performance Improvement Pass
Apply skill performance-pass.
Target hotspot: `<query/loop/endpoint/path>`.
Current issue: `<latency/cpu/memory/throughput symptom>`.
Measurement method: `<logs/profiler/load test/devtools>`.
Constraints: `<acceptable trade-offs, SLA targets>`.
Identify hotspot, measure baseline, propose 2-3 options with trade-offs, wait for go/no-go, implement, measure after, update tests, and report before/after comparison.

## 11) JUnit 5 Test Coverage Boost
Apply skill java-junit.
Target module/class: `<class/module>`.
Scope: `<unit/integration/mixed>`.
Behaviors to cover: `<list>`.
Edge/error cases: `<list>`.
Use AAA structure, parameterized tests where relevant, Mockito for isolation, and descriptive assertions.
Run tests, report results, and highlight uncovered risk areas.

## 12) Angular Test Coverage Boost
Apply skill angular-testing.
Target: `<component/service/module>`.
Scope: `<unit/integration/e2e>`.
Behaviors to cover: `<list>`.
Edge/error cases: `<list>`.
Use TestBed setup, mock services, test inputs/outputs, async rendering, and HTTP interactions.
Run tests, report results, and highlight uncovered risk areas.

## 13) Backend API Review (Agent)
Use agent backend-api-reviewer for this task.
Endpoint(s): `<METHOD /path>`.
Request/response changes: `<summary>`.
Business constraints: `<rules>`.
Security constraints: `<auth/permissions>`.
Compatibility expectations: `<backward-compatible / breaking approved>`.
Review architecture, contracts, validation, security, tests, and docs. Return findings checklist, required actions, and risk notes.

## Usage Tip
Start each request with one of these prompts, then append exact business constraints.

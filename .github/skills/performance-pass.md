# Skill: Performance Improvement Pass

## Purpose
Identify, measure, and resolve performance hotspots with clear trade-off analysis and before/after evidence.

## References
- `.github/copilot-instructions.md`
- `.github/copilot-context.md`

## Required Inputs
- Target hotspot (query, loop, endpoint, rendering path)
- Current symptom (latency, CPU, memory, throughput)
- Measurement method available (logs, profiler, load test, browser devtools)
- Acceptable trade-offs and constraints

## Execution Checklist
1. **Identify and confirm hotspot:** Pinpoint the specific code path causing the issue.
2. **Measure baseline:** Capture current metrics (response time, query count, memory, etc.) with the available measurement method.
3. **Propose 2–3 solution options** with trade-offs for each (complexity, risk, maintainability, behavior changes).
4. **Get explicit go/no-go** from the developer before implementing.
5. **Implement chosen option:** Code changes may intentionally alter behavior (caching, query rewriting, async processing, pagination strategy, etc.).
6. **Measure after:** Capture the same metrics post-change and compare.
7. **Add/update regression tests** to cover the changed path — both correctness and performance-sensitive behavior.
8. **Document trade-offs applied** (e.g., eventual consistency, cache TTL, pagination limits).
9. Run relevant checks and report outcomes.

## Done Criteria
- Hotspot addressed with measurable improvement evidence.
- Trade-offs explicitly documented.
- Regression tests updated for changed behavior.
- Before/after metrics reported.
- Residual risks stated.

## Prompt Template
Apply skill performance-pass.
Target hotspot: `<query/loop/endpoint/path>`
Current issue: `<latency/cpu/memory/throughput symptom>`
Measurement method: `<logs/profiler/load test/devtools>`
Constraints: `<acceptable trade-offs, SLA targets>`
Identify hotspot, measure baseline, propose 2-3 options with trade-offs, wait for go/no-go, implement, measure after, update tests, and report before/after comparison.

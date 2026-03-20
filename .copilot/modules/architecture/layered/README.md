# Module: Layered Architecture

## Purpose
This module defines governance for a **layered architecture** for Spring Boot + Angular projects, with a clear separation of responsibilities.

## When to use
Use this module when you want:
- Familiar, mainstream structure for Spring Boot services
- Clear boundaries between API transport, business logic, and persistence
- Straightforward testing strategy by layer

## What this module provides
- Layer responsibilities and rules (backend)
- Package layout guidance (package-by-feature + internal layers)
- Testing expectations aligned to the layers
- A lightweight ADR with rationale and trade-offs

## Related modules
- Works with: `api/rest`
- Conflicts with: `architecture/hexagonal`
# Changelog

All notable changes to this repository will be documented in this file.

This project follows a draft-stage specification model.  
Version numbers before 1.0 indicate an evolving standard and may include substantial structural changes.

The format is inspired by Keep a Changelog, adapted for specification repositories.

---

## [v0.2.0] - 2026-05-07

### Added
- New operational draft specification target:
  - `spec/multi-wing-standard-specification-v0.2.md`
- New operational and coordination documents:
  - `docs/kazene-operational-semantics.md`
  - `docs/wing-composition-rules.md`
  - `docs/trace-lifecycle-model.md`
- Strengthened interoperability guidance in:
  - `docs/interoperability-profiles.md`
- New informative scenario examples:
  - `examples/scenarios/minimal-session.sample.json`
  - `examples/scenarios/review-loop.sample.json`
  - `examples/scenarios/trace-integrated.sample.json`

### Changed
- Repository positioning was updated so that:
  - `v0.2.0` is the **current operational draft**
  - `v0.1.0` remains the **baseline structural draft**
- `README.md` was revised to:
  - foreground `v0.2.0` as the recommended primary reading target
  - preserve `v0.1.0` as a historical and structural reference
  - incorporate new operational documents into the reading order
  - distinguish atomic examples from scenario-based examples
- `docs/one-page-overview.md` was updated to reflect the expanded reading order and scenario structure
- `docs/interoperability-profiles.md` was expanded toward a v0.2-oriented profile model, including:
  - stronger operational interpretation of profiles
  - richer profile negotiation guidance
  - new profile directions such as `signed-trace` and `federated`
- Repository structure guidance was updated to include:
  - scenario-based examples
  - a clearer distinction between canonical draft versions
  - a stronger operational interpretation of Multi-Wing

### Clarified
- The role of **Kazene** was clarified from a coordination principle toward an **operational coordination semantics**
- The role of **composition** was clarified from simple role combination toward explicit structural rules governing:
  - recommended pairings
  - risky pairings
  - guarded compositions
  - prohibited silent merges
- The role of **trace** was clarified from static provenance metadata toward a **lifecycle-bound structural continuity model**
- The role of **profiles** was clarified from simple maturity labels toward explicit interoperability boundaries
- The relationship between:
  - structural draft (`v0.1.0`)
  - operational draft (`v0.2.0`)
  
  was made explicit across repository documentation

### Defined
- A more operational interpretation of Multi-Wing across:
  - coordination states
  - rebalance conditions
  - escalation triggers
  - failure containment
  - degraded-mode behavior
- A stronger architectural interpretation of trace across:
  - proposal
  - assignment
  - execution
  - review
  - revision
  - rebalance
  - finalization
  - escalation
  - archive / retention
- A more explicit composition model for Wings across:
  - sequential composition
  - parallel composition
  - nested composition
  - composite Wing structures
- A more explicit profile model across:
  - structure surface
  - protocol surface
  - context surface
  - trace surface
  - execution surface
  - trust and governance surface

### Notes
- `v0.2.0` should be read as the **current operational draft**
- `v0.1.0` remains the **baseline structural draft**
- The purpose of `v0.2.0` is not to replace the conceptual basis of Multi-Wing, but to make more of its coordination law explicit
- Backward compatibility is not guaranteed before 1.0
- Future revisions may further formalize:
  - conformance language
  - profile registries
  - scenario-to-schema relationships
  - reference implementation guidance
  - stronger trace and federation extensions

---

## [v0.1.0] - 2026-05-05

### Added
- Initial repository structure for **Multi-Wing Standard Specification**
- Initial `README.md`
- Canonical specification target:
  - `spec/multi-wing-standard-specification-v0.1.md`
- Supporting documentation targets:
  - `docs/one-page-overview.md`
  - `docs/architecture-overview.md`
  - `docs/wing-type-system.md`
  - `docs/kazene-coordination-principles.md`
  - `docs/interoperability-profiles.md`
  - `docs/relationship-to-mcp-a2a.md`
- Initial repository governance files:
  - `CONTRIBUTING.md`
  - `CHANGELOG.md`
  - `CITATION.cff`
- Initial schema targets:
  - `schemas/wing-type.schema.json`
  - `schemas/message-envelope.schema.json`
  - `schemas/shared-context.schema.json`
  - `schemas/trace-reference.schema.json`
- Initial example targets:
  - `examples/wing-type.sample.json`
  - `examples/message-envelope.sample.json`
  - `examples/shared-context.sample.json`
  - `examples/trace-reference.sample.json`

### Defined
- Project scope as an **open draft specification**
- Three-layer architecture:
  - Structure Layer
  - Protocol Layer
  - Execution Layer
- Core positioning of Multi-Wing as a standardizable abstraction for distributed intelligence
- Early terminology around:
  - Wing
  - Role
  - Capability
  - Shared Context
  - Trace Reference
  - Kazene coordination

### Notes
- `v0.1.0` establishes the initial publication baseline
- Future revisions may refine terminology, schemas, conformance language, and interoperability mappings
- Backward compatibility is not guaranteed before 1.0

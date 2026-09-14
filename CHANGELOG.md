# Changelog

All notable conceptual changes to SDO will be documented here.

Version numbers below refer to methodology drafts, not software releases.

## [0.3] — 2026-09-14

### Changed

- Promoted SDO from **Concept Draft** to **Public Draft**.
- Reframed the repository for external testing, criticism, adaptation, and community feedback.
- Added a concise `Start here` path in the README for first-time readers.

### Added

- **Generic End-to-End Example**, showing a complete implementation-independent flow from Execution Specification through validation, authorization, execution, result, conformance, Handoff Record, Receiving Conditions, and acceptance.
- `CONTRIBUTING.md` with guidance for:
  - conceptual criticism;
  - real-world experiments;
  - failed adoption reports;
  - implementation patterns;
  - prior-art references;
  - documentation and model improvements.
- Public invitation: **Try it. Challenge it. Adapt it. Share what worked and what did not.**

### Status

**Public Draft v0.3.** SDO is intentionally open for testing and challenge. It is not a finished standard.

## [0.2] — 2026-09-14

### Changed

- Reframed SDO from a human/AI or hybrid-execution concept to an **executor-independent organizational execution methodology**.
- Defined the core distinction between the operational obligation and the concrete execution instance.
- Established that execution success is determined by result and evidence conformance to the applicable specification, not by executor identity.
- Replaced actor-centered language in the foundational model with:
  - Execution Specification;
  - Execution Instance;
  - Result;
  - Evidence;
  - Validation and Verification;
  - Controlled Exception;
  - Handoff;
  - Trace.
- Clarified that executor identity remains relevant only when authority, law, certification, safety, access, accountability, segregation of duties, or policy legitimately requires it.
- Repositioned SDO as a **general-purpose and implementation-independent methodology** rather than a methodology specifically for hybrid human-agent operations.
- Aligned Core Concepts and Glossary with executor independence and conformance-based success.
- Clarified that **Notification is not Handoff** and that responsibility transfer depends on explicit Receiving Conditions.
- Established channel independence for handoffs: SDO defines transfer semantics but does not mandate the communication or transport technology.

### Added

- Open Methodology Philosophy.
- Executor Independence as a foundational principle.
- Minimum Viable Model for generic adoption.
- Initial Execution Specification reference model and YAML template.
- **SDO Core Model v0.1**, defining eight core entities:
  - Execution Specification;
  - Execution Instance;
  - Result;
  - Evidence;
  - Conformance Evaluation;
  - Controlled Exception;
  - Handoff;
  - Trace.
- Formal core relations and minimum cardinalities.
- Ten Core Model invariants, including specification identity, obligation independence, result-before-success, conformance-based success, evidence integrity, exception visibility, version traceability, handoff validity, executor traceability when required, and implementation independence.
- Three-layer structural separation: **Obligation → Execution → Conformance**.
- Abstract conformance rule for minimum SDO execution success.
- Minimum structural SDO conformance criteria.
- **SDO Handoff Model v0.1**, defining:
  - Handoff Record;
  - Receiving Conditions;
  - source and receiver responsibilities;
  - transfer and acceptance as distinct states;
  - explicit blocked, rejected, accepted, and conditional outcomes;
  - chainable responsibility transfers with Trace continuity.
- **SDO Adoption Model v0.1**, defining:
  - Level 1 — Manual;
  - Level 2 — System-Assisted;
  - Level 3 — Machine-Enforced;
  - progressive adoption without changing the semantic model;
  - a generic eight-step pilot method;
  - minimum viable tooling test;
  - role responsibilities without mandatory job titles;
  - adoption anti-patterns.
- **Implementation Minimalism** as an adoption principle.
- Guiding statement: **Use the systems you already have before adding new ones.**
- Guiding statement: **Notification is not handoff.**
- Novelty and differentiation research notes.
- Explicit publication philosophy: `Concept Draft → Public Draft → Release Candidate → 1.0`.
- **Creative Commons Attribution 4.0 International (CC BY 4.0)** licensing for methodology documentation, templates, diagrams, and research notes unless otherwise noted.
- Guiding statement: **Adapt the implementation. Preserve the principles.**

### Status

**Concept Draft v0.2.** The methodology remains under active conceptual development and has not yet been declared stable.

## [0.1] — 2026-09-14

### Added

- Initial definition of **Specification-Driven Operations (SDO)**.
- Origin in Spec-Driven Development (SDD) documented.
- Initial SDO lifecycle: `SPECIFY → VALIDATE → AUTHORIZE → EXECUTE → VERIFY → HANDOFF`.
- Initial core vocabulary:
  - Execution Specification;
  - Execution Unit;
  - Execution Agent;
  - Validation Gate;
  - Execution Contract;
  - Evidence;
  - Handoff;
  - Controlled Exception.
- Initial set of foundational principles.
- Controlled Exception model and initial exception taxonomy.
- Distinction between normal Authorization and Conditional Authorization.
- Initial glossary.
- Research area established for comparison with adjacent methodologies and disciplines.

### Status

**Concept Draft v0.1.** No stable methodology release has been declared.

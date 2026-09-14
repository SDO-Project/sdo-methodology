# SDO Manifesto

> **Specification-Driven Operations — Concept Draft v0.1**

Modern organizations have digitized their records, communication, tasks, and workflows. Yet a large part of operational execution still depends on incomplete requests, free-text instructions, informal agreements, tacit knowledge, and subjective interpretation.

The result is predictable: work advances without the information required by the next stage, hidden inconsistencies accumulate, responsibility becomes ambiguous, and defects are discovered only after execution has already consumed time and resources.

SDO proposes a different operational discipline.

## Our premise

**Execution should be driven by explicit specifications, not by assumptions.**

Before work advances, the organization should be able to determine whether the conditions required for the next execution stage are actually satisfied.

This does not mean turning every activity into bureaucracy. It means making critical operational expectations explicit, structured, verifiable, and traceable at the points where ambiguity creates risk.

## We believe

### Specification before execution

Important work should begin from an explicit definition of what is required, what constraints apply, what result is expected, and how completion will be verified.

### Validation before transfer

A handoff is not complete because the previous actor declared their task finished. A handoff is complete when the receiving conditions defined for the next stage are satisfied.

### Structured information over avoidable ambiguity

Free text remains useful for context, explanation, and judgment. It should not be the sole carrier of information that can and should be represented as structured operational data.

### Failure should surface as early as possible

Missing, contradictory, or invalid conditions should be detected before downstream execution whenever practical.

### Completion should be verifiable

Critical completion states should be supported by objective evidence appropriate to the work being performed.

### Specifications must evolve with reality

Operational specifications are living artifacts. When reality changes, the active specification must change explicitly rather than allowing execution and documentation to diverge.

### Exceptions are part of real operations

A useful methodology cannot assume perfect conditions. Exceptions must be possible, but they must be visible, justified, authorized, bounded, and traceable.

> **SDO does not eliminate exceptions. It eliminates invisible exceptions.**

### Traceability enables learning

The purpose of traceability is not merely to assign blame. A trustworthy history of changes, decisions, exceptions, evidence, and outcomes allows organizations to understand why execution diverged and to improve their specifications.

## The operating idea

SDO organizes critical work around a recurring lifecycle:

```text
SPECIFY → VALIDATE → AUTHORIZE → EXECUTE → VERIFY → HANDOFF
```

When normal requirements cannot be satisfied, the flow moves into a controlled exception path rather than bypassing governance informally.

## The ambition

SDO is intended to be applicable regardless of who or what performs the work. An **Execution Agent** may be a person, team, supplier, software service, automation, robot, or AI agent.

The methodology therefore seeks a common operational language for increasingly hybrid organizations in which human and automated execution coexist.

## Guiding statement

> **Specify before execution. Validate before transfer.**

---

**Status:** Concept Draft v0.1 — September 2026

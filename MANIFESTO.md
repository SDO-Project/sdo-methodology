# SDO Manifesto

> **Specification-Driven Operations — Concept Draft v0.2**

Modern organizations have digitized records, communication, tasks, workflows, automation, and decision support. Yet a large part of operational execution still depends on incomplete requests, free-text instructions, informal agreements, tacit knowledge, and assumptions about who will perform the work.

The result is predictable: work advances without the information required by the next stage, hidden inconsistencies accumulate, responsibility becomes ambiguous, and defects are discovered only after execution has already consumed time and resources.

SDO proposes a different operational discipline.

## Our premise

**Execution should be governed by explicit specifications, not by assumptions about the executor.**

Before work begins, advances, or is transferred, the organization should be able to determine what obligation applies, what conditions must be satisfied, what result is expected, and how conformance will be verified.

This does not mean turning every activity into bureaucracy. It means making critical operational expectations explicit, structured, verifiable, versioned, and traceable where ambiguity creates material risk.

## We believe

### Specification before execution

Important work should begin from an explicit definition of what is required, what constraints apply, what result is expected, and how completion will be verified.

### The obligation is independent from the executor

The specification defines the operational obligation. A concrete execution records how that obligation was attempted and by whom or by what.

A person, team, software system, automation, AI agent, machine, supplier, or future execution mechanism may perform the work when applicable constraints permit it. The methodology does not need to change merely because the executor changes.

> **The executor belongs to the execution. The obligation belongs to the specification.**

### Conformance defines success

Execution is successful when the result and required evidence conform to the applicable specification.

> **Execution is judged by conformance to the specification, not by the identity of the executor.**

Executor identity remains relevant where authority, law, certification, safety, accountability, segregation of duties, or organizational policy makes it a legitimate requirement.

### Validation before transfer

A handoff is not complete because the previous executor declared the work finished. A handoff is complete when the receiving conditions defined for the next stage are satisfied.

### Structured information over avoidable ambiguity

Free text remains useful for context, explanation, and judgment. It should not be the sole carrier of information that can and should be represented as structured operational data.

### Failure should surface as early as possible

Missing, contradictory, invalid, or unsatisfied conditions should be detected before downstream execution whenever practical.

### Completion should be verifiable

Critical completion states should be supported by evidence appropriate to the work and its risk.

### Specifications must evolve with reality

Operational specifications are living artifacts. When reality changes materially, the active specification must change explicitly rather than allowing execution and documentation to diverge.

### Exceptions are part of real operations

A useful methodology cannot assume perfect conditions. Exceptions must be possible, but they must be visible, justified, authorized, bounded, and traceable.

> **SDO does not eliminate exceptions. It eliminates invisible exceptions.**

### Traceability enables learning

The purpose of traceability is not merely to assign blame. A trustworthy history of specifications, decisions, exceptions, evidence, executions, and outcomes allows organizations to understand divergence and improve the system.

### Governance should be proportional

Not every unit of work requires the same rigor. Specification detail, evidence, approvals, verification, and exception controls should be proportional to risk and consequence.

## The operating idea

SDO organizes governed work around a recurring lifecycle:

```text
SPECIFY → VALIDATE → AUTHORIZE → EXECUTE → VERIFY → HANDOFF
```

The core execution model is:

```text
EXECUTION SPECIFICATION
          ↓
   EXECUTION INSTANCE
          ↓
        RESULT
          ↓
 CONFORMANCE CHECK
      /        \
    PASS       FAIL
     ↓           ↓
 HANDOFF     REWORK /
             EXCEPTION
```

When normal requirements cannot be satisfied, execution moves into a controlled exception path rather than bypassing governance informally.

## The ambition

SDO is proposed as a **general-purpose, open methodology for organizational execution**.

It is intended for a world in which work may be performed by humans, software, automation, AI agents, machines, external parties, or mechanisms that do not yet exist.

SDO does not prescribe a software platform and does not require organizations to implement the methodology in one particular way.

> **Adapt the implementation. Preserve the principles.**

The methodology is intended to be studied, tested, criticized, adapted, and improved through practical use.

## Guiding statements

> **Specify before execution. Validate before transfer.**

> **Execution is judged by conformance to the specification, not by the identity of the executor.**

> **SDO does not eliminate exceptions. It eliminates invisible exceptions.**

> **Adapt the implementation. Preserve the principles.**

---

SDO is developed as an open methodology. Unless otherwise noted, the project documentation is licensed under **CC BY 4.0**.

**Status:** Concept Draft v0.2 — September 2026

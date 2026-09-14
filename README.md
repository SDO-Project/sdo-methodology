# SDO — Specification-Driven Operations

> **Concept Draft v0.2**

**Specification-Driven Operations (SDO)** is an open methodology proposal for modern organizational execution.

SDO defines operational obligations through explicit, structured, versioned specifications and evaluates execution by the conformance of results and evidence to those specifications.

It is inspired by the **Spec-Driven Development (SDD)** principle that execution becomes more reliable when the specification is made explicit before implementation begins. SDO generalizes that principle beyond software development and applies it to organizational work regardless of whether execution is performed by a person, team, software system, automation, AI agent, machine, external party, or another execution mechanism.

## Core thesis

Organizations have digitized tasks, communication, records, automation, and workflows, but many operational handoffs still depend on incomplete requests, free text, informal agreements, tacit knowledge, and assumptions about who will perform the work.

SDO proposes a different default:

> **Specify before execution. Validate before transfer.**

The specification defines the obligation. A concrete execution produces a result. That result is then verified against the applicable specification.

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

## Executor independence

A central principle of SDO is that the operational obligation should not be unnecessarily coupled to the identity or class of the executor.

> **The executor belongs to the execution. The obligation belongs to the specification.**

A person, team, software service, automation, AI agent, robot, supplier, or future execution mechanism may perform the work when applicable constraints permit it. SDO does not need to change merely because the executor changes.

> **Execution is judged by conformance to the specification, not by the identity of the executor.**

Executor identity remains relevant when authority, law, certification, safety, accountability, segregation of duties, access, or organizational policy makes it a legitimate requirement. Such restrictions should be expressed explicitly rather than embedded as undocumented assumptions.

## The SDO lifecycle

```text
SPECIFY
   ↓
VALIDATE
   ↓
AUTHORIZE
   ↓
EXECUTE
   ↓
VERIFY
   ↓
HANDOFF
```

When a specification cannot be satisfied, execution may enter a **Controlled Exception** path. SDO does not assume that exceptions can be eliminated; it requires them to become visible, justified, authorized, bounded, and traceable.

> **SDO does not eliminate exceptions. It eliminates invisible exceptions.**

## Handoff and responsibility transfer

SDO distinguishes communication from transfer of responsibility.

> **Notification is not handoff.**

A valid handoff carries the verified Result, required Evidence, governing specification reference, applicable exceptions, Receiving Conditions, and Trace context to the next execution boundary.

The receiving boundary defines the conditions under which it accepts responsibility. A message, email, status change, event, or task notification may announce that work is available, but responsibility transfers only when the receiving conditions are satisfied or a Controlled Exception explicitly authorizes conditional transfer.

The canonical transfer structure is the **Handoff Record**, defined in the [SDO Handoff Model v0.1](docs/11-handoff-model.md).

## Foundational concepts

- **Execution Specification** — the authoritative definition of the operational obligation, including conditions, constraints, expected result, acceptance criteria, evidence, exceptions, and handoff requirements.
- **Execution Unit** — a bounded unit of governed work.
- **Execution Instance** — a concrete attempt to satisfy an Execution Specification.
- **Result** — the output, decision, state change, service, or other observable outcome produced by an Execution Instance.
- **Conformance Evaluation** — the determination of whether the Result and required Evidence satisfy the applicable specification.
- **Validation Gate** — the mechanism that determines whether required conditions are satisfied before advancement.
- **Evidence** — objective information used to support a conformance or verification decision.
- **Controlled Exception** — a formally declared and authorized deviation from the normal specification.
- **Handoff Record** — the canonical information set used to represent transfer of responsibility between execution boundaries.
- **Receiving Conditions** — the explicit conditions that must be satisfied before the receiving boundary accepts responsibility.
- **Handoff** — a validated transfer of a conformant result and required context to the next execution boundary.
- **Trace** — the auditable history linking specification, execution, result, evidence, decisions, exceptions, and handoff.

The formal relationships, invariants, and minimum conformance rules are defined in the [SDO Core Model v0.1](docs/10-core-model.md).

## Adoption and implementation

SDO is a methodology, not a mandatory software layer.

Organizations should use existing systems whenever those systems can preserve the required semantics with acceptable reliability.

> **Use the systems you already have before adding new ones.**

The [SDO Adoption Model v0.1](docs/12-adoption-model.md) defines three reference adoption levels:

```text
LEVEL 1 — MANUAL
LEVEL 2 — SYSTEM-ASSISTED
LEVEL 3 — MACHINE-ENFORCED
```

These are implementation options, not mandatory maturity stages. A manual implementation that faithfully preserves SDO semantics may be more conformant than a sophisticated platform that does not.

This adoption principle is called **Implementation Minimalism**.

## Open methodology

SDO is intended to be **open, adaptable, implementation-independent, and usable across organizational contexts**.

It is not a proprietary workflow product, a closed operating system, or a mandatory certification scheme.

Organizations may implement SDO using forms, spreadsheets, ERP/CRM systems, BPM engines, databases, APIs, policy engines, automation platforms, AI-agent orchestration systems, machines, custom software, or combinations of them.

> **Adapt the implementation. Preserve the principles.**

Use, experimentation, criticism, adaptation, and publication of implementation patterns are encouraged.

Unless otherwise noted, the methodology documentation, templates, diagrams, and research notes in this repository are licensed under **Creative Commons Attribution 4.0 International (CC BY 4.0)**. See [LICENSE](LICENSE).

## Documentation

- [Manifesto](MANIFESTO.md)
- [Introduction](docs/01-introduction.md)
- [Origin and Motivation](docs/02-origin-and-motivation.md)
- [Core Concepts](docs/03-core-concepts.md)
- [Principles](docs/04-principles.md)
- [Execution Lifecycle](docs/05-execution-lifecycle.md)
- [Controlled Exceptions](docs/06-controlled-exceptions.md)
- [Glossary](docs/07-glossary.md)
- [Minimum Viable Model](docs/08-minimum-viable-model.md)
- [Open Methodology Philosophy](docs/09-open-methodology.md)
- [SDO Core Model v0.1](docs/10-core-model.md)
- [SDO Handoff Model v0.1](docs/11-handoff-model.md)
- [SDO Adoption Model v0.1](docs/12-adoption-model.md)
- [Execution Specification v0.2](spec/execution-spec-v0.1.md)
- [Execution Specification YAML Template](templates/execution-spec.yaml)
- [Novelty Assessment](research/novelty-assessment-v0.1.md)
- [Executor Independence Differentiation](research/executor-independence-differentiation-v0.1.md)
- [Research Notes](research/README.md)

## Research position

SDO does not claim ownership over the underlying ideas of specifications, workflow validation, evidence, traceability, exception handling, process management, automation, or agentic execution. These concepts have substantial prior histories across multiple disciplines.

The current research hypothesis is narrower: SDO may be differentiated by synthesizing these mechanisms into a **general-purpose, technology-independent organizational methodology in which operational obligations are defined independently from executors and execution success is determined by conformance to the applicable specification**.

No claim of historical first invention is made at this stage.

## Status

SDO is currently under conceptual development. Terminology, scope, principles, and formal mechanisms may change while the methodology is tested against different operational contexts.

This repository is the source of truth for that development.

## Version

**Concept Draft v0.2 — September 2026**

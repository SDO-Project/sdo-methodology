# SDO — Specification-Driven Operations

> **Concept Draft v0.1**

**Specification-Driven Operations (SDO)** is an emerging methodology for organizational execution in which work is specified, validated, authorized, executed, verified, and transferred through explicit, structured, traceable specifications.

SDO is inspired by the **Spec-Driven Development (SDD)** principle that execution becomes more reliable when the specification is made explicit before implementation begins. SDO generalizes that idea beyond software development and applies it to operational work performed by people, teams, systems, automations, and AI agents.

## Core thesis

Organizations have digitized tasks, communication, and records, but many operational handoffs still depend on incomplete requests, free text, informal agreements, and human interpretation.

SDO proposes a different default:

> **Specify before execution. Validate before transfer.**

A work item should not advance merely because someone marked a task as complete. It advances when the conditions required by the next execution stage are explicitly satisfied or when a controlled exception has been formally authorized.

## Actor-neutral execution

A distinguishing objective of SDO is to separate the **work contract** from the **executor**.

Where capability and authority permit, the same core Execution Specification should be able to govern work performed by a human, team, AI agent, software system, automation, external party, or hybrid combination without redefining the business obligation.

> **Define the work once. Govern every executor by the contract.**

Actor-specific controls remain possible through capability, authority, segregation-of-duties, verification, and execution-profile requirements.

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

## Foundational concepts

- **Execution Specification** — the explicit definition of the conditions, data, rules, dependencies, criteria, and evidence required for execution.
- **Execution Unit** — a bounded stage or unit of work responsible for producing an expected result.
- **Execution Agent** — a person, team, system, automation, supplier, robot, or AI agent performing the work.
- **Validation Gate** — the mechanism that verifies whether an execution is eligible to advance.
- **Execution Contract** — the structured agreement governing a handoff between execution units.
- **Evidence** — objective information used to verify execution or completion.
- **Controlled Exception** — a formally declared and authorized deviation from the normal specification.
- **Handoff** — a validated transfer of responsibility from one execution unit to another.

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
- [Execution Specification v0.1](spec/execution-spec-v0.1.md)
- [Execution Specification YAML Template](templates/execution-spec.yaml)
- [Novelty Assessment](research/novelty-assessment-v0.1.md)
- [Research Notes](research/README.md)

## Research position

Current research shows substantial prior work in declarative BPM, artifact-centric processes, case management, policy-as-code, human-in-the-loop AI, agentic orchestration, and shared specifications for humans and AI in technical domains.

The current SDO research hypothesis is therefore deliberately narrower: SDO may be differentiated by combining these mechanisms into a **general-purpose, technology-independent organizational methodology centered on actor-neutral Execution Specifications**.

No claim of historical first invention is made at this stage.

## Status

SDO is currently under conceptual development. Terminology, scope, principles, and formal mechanisms may change while the methodology is tested against real operational processes.

This repository is the source of truth for that development.

## Version

**Concept Draft v0.1 — September 2026**

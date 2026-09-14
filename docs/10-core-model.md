# SDO Core Model v0.1

> **Concept Draft — Formal Reference Model**

The SDO Core Model defines the minimum conceptual structure required to represent specification-driven organizational execution independently from industry, software platform, or executor type.

Its central rule is:

> **The executor belongs to the execution. The obligation belongs to the specification.**

An execution is considered successful when its result conforms to the applicable specification.

```text
Execution Success = Result conforms to Applicable Specification
```

Conceptually:

```text
Result ⊨ Specification
```

This model does not assume that execution is human, automated, agentic, robotic, external, or hybrid. Executor identity is execution metadata unless the specification explicitly imposes restrictions for legitimate operational reasons.

---

## 1. Canonical model

```text
                   ┌─────────────────────────┐
                   │ EXECUTION SPECIFICATION │
                   │                         │
                   │ obligation              │
                   │ inputs                  │
                   │ preconditions           │
                   │ constraints             │
                   │ expected result         │
                   │ acceptance criteria     │
                   │ evidence requirements   │
                   │ exception policy        │
                   │ handoff conditions      │
                   └────────────┬────────────┘
                                │ governs
                                ▼
                   ┌─────────────────────────┐
                   │   EXECUTION INSTANCE    │
                   │                         │
                   │ spec version            │
                   │ actual inputs           │
                   │ executor metadata       │
                   │ authorization           │
                   │ runtime trace           │
                   │ exceptions              │
                   └────────────┬────────────┘
                                │ produces
                                ▼
                        ┌──────────────┐
                        │    RESULT    │
                        └──────┬───────┘
                               │ supported by
                               ▼
                        ┌──────────────┐
                        │   EVIDENCE   │
                        └──────┬───────┘
                               │
                               ▼
                   ┌─────────────────────────┐
                   │   CONFORMANCE CHECK     │
                   │ Result vs Specification │
                   └────────────┬────────────┘
                                │
                     ┌──────────┴──────────┐
                     │                     │
                   PASS                   FAIL
                     │                     │
                     ▼                     ▼
                  HANDOFF          REWORK / EXCEPTION
                     │
                     ▼
             NEXT EXECUTION UNIT
```

The executor does not appear as a first-class node in the canonical flow because SDO evaluates the obligation primarily through result conformance.

---

## 2. Core entities

The minimum formal model contains eight core entities.

### 2.1 Execution Specification

The **Execution Specification** is the authoritative definition of an operational obligation.

It defines what must be true before execution, what constraints apply during execution, what result is required, how that result will be evaluated, what evidence is required, how exceptions are governed, and what conditions allow handoff.

The specification MUST be version-identifiable.

The specification SHOULD describe the obligation independently from the implementation used to satisfy it.

The specification MAY restrict executor characteristics where capability, authority, regulation, safety, segregation of duties, or other legitimate requirements make executor identity relevant.

### 2.2 Execution Instance

An **Execution Instance** is one concrete attempt to satisfy one applicable Execution Specification.

It records the operational facts of that attempt, including:

- execution identifier;
- applicable specification and version;
- actual inputs;
- authorization state;
- executor identity or identities, when applicable;
- executor class or implementation, when useful;
- start and end timestamps;
- runtime decisions and events;
- exceptions invoked;
- produced result;
- evidence references;
- verification and conformance outcome;
- handoff outcome.

The Execution Instance is where executor identity belongs.

### 2.3 Result

A **Result** is the observable outcome produced by an Execution Instance.

A result may be:

- structured data;
- an artifact;
- a decision;
- a state transition;
- a physical outcome;
- a service outcome;
- a combination of these.

A result is not automatically successful because execution completed. It becomes acceptable only through conformance evaluation against the applicable specification.

### 2.4 Evidence

**Evidence** is verifiable information that supports a claim about execution, result, authorization, exception, or conformance.

Evidence may include:

- measurements;
- records;
- logs;
- signatures;
- approvals;
- test results;
- documents;
- photos;
- generated artifacts;
- system events;
- provenance information.

Evidence requirements SHOULD be proportional to operational risk.

### 2.5 Conformance Evaluation

**Conformance Evaluation** determines whether the Result and required Evidence satisfy the acceptance criteria and other applicable conditions defined by the Execution Specification.

Minimum outcomes are:

```text
PASS
FAIL
CONDITIONAL
```

`CONDITIONAL` is valid only when an approved Controlled Exception explicitly permits the deviation.

Conformance may be evaluated by a person, deterministic rule, software system, AI system, independent reviewer, measurement process, or combination of methods. The evaluator is not conceptually privileged over the executor; what matters is that the verification method itself satisfies the applicable specification.

### 2.6 Controlled Exception

A **Controlled Exception** is a formally governed deviation from one or more normal specification conditions.

An exception MUST be explicit and traceable.

At minimum it records:

- affected requirement;
- reason;
- scope;
- risk or impact;
- requested deviation;
- approving authority;
- decision;
- compensating controls, where applicable;
- validity or expiration;
- closure or review condition.

An approved exception does not erase the original rule. It creates an explicit conditional basis for execution or conformance.

### 2.7 Handoff

A **Handoff** is the formal transfer of a verified result and its required context into the responsibility boundary of another Execution Unit or process boundary.

A handoff occurs only when downstream entry conditions are satisfied or when an approved Controlled Exception permits transfer.

A handoff SHOULD carry enough information for the receiving side to determine readiness without relying on undocumented conversation.

### 2.8 Trace

A **Trace** is the ordered, attributable history of material execution events.

It connects:

```text
Specification
→ Validation
→ Authorization
→ Execution
→ Result
→ Evidence
→ Exceptions
→ Conformance
→ Handoff
```

Traceability exists for accountability, auditability, diagnosis, learning, and specification improvement.

---

## 3. Supporting concepts

The following concepts are important but are not first-class core entities in the universal model.

### Execution Unit

An **Execution Unit** is a bounded operational responsibility governed by an Execution Specification.

It is a modeling boundary used to decompose processes into meaningful obligations.

### Executor

An **Executor** is the person, team, system, automation, AI agent, robot, external party, machine, or combination that performs a particular Execution Instance.

Executor is intentionally modeled as a property of an execution rather than as the source of the obligation.

### Validation Gate

A **Validation Gate** determines whether the conditions required to proceed into a subsequent lifecycle state are satisfied.

### Authorization

**Authorization** determines whether an otherwise valid Execution Instance is permitted to proceed.

Validation and authorization remain distinct:

```text
VALID ≠ AUTHORIZED
```

### Execution Contract

An **Execution Contract** is the subset or projection of specification conditions relevant to a transfer of responsibility between Execution Units.

It is primarily a handoff concept rather than a separate source of truth from the Execution Specification.

---

## 4. Core relations

The formal relationships are:

```text
Execution Specification
    governs 1..n Execution Instances

Execution Instance
    references exactly 1 applicable Specification Version
    consumes 0..n Inputs
    records 0..n Executor identities
    produces 1..n Results
    references 0..n Evidence items
    invokes 0..n Controlled Exceptions
    produces 1 Conformance Outcome
    may produce 0..n Handoffs

Result
    is evaluated against 1 applicable Specification Version

Evidence
    supports 1..n operational claims

Controlled Exception
    refers to 1..n Specification conditions

Handoff
    transfers verified Result + required context

Trace
    links all material lifecycle events
```

---

## 5. Core invariants

An SDO-conformant implementation SHOULD preserve the following invariants.

### I-01 — Specification identity

Every governed Execution Instance MUST reference an identifiable Execution Specification version.

### I-02 — Obligation independence

The core obligation SHOULD be defined independently from the executor unless executor characteristics are themselves legitimate operational constraints.

### I-03 — Result before success

Execution completion alone MUST NOT imply successful conformance.

### I-04 — Conformance-based success

A successful execution MUST be supported by a conformance decision against the applicable specification.

### I-05 — Evidence integrity

Where evidence is required, conformance MUST NOT be declared without the required evidence or an approved exception.

### I-06 — Exception visibility

A deviated requirement MUST remain visible in the execution history even when an exception is approved.

### I-07 — Version traceability

The specification version used for validation, authorization, execution, and conformance MUST be traceable.

### I-08 — Handoff validity

A handoff MUST NOT be considered complete unless downstream entry conditions are satisfied or an approved exception explicitly allows the transfer.

### I-09 — Executor traceability

When accountability, security, authority, audit, safety, or regulation requires executor identity, it MUST be recorded in the Execution Instance.

### I-10 — Implementation independence

Changing the implementation or executor SHOULD NOT require redefining the core obligation when the expected result and governing conditions remain unchanged.

---

## 6. Separation of obligation and implementation

SDO distinguishes three layers:

```text
LAYER 1 — OBLIGATION
Execution Specification
What must be satisfied?

LAYER 2 — EXECUTION
Execution Instance
How was this attempt performed?

LAYER 3 — CONFORMANCE
Result + Evidence vs Specification
Was the obligation satisfied?
```

This separation is central to SDO.

A workflow implementation may change without changing the obligation.

An executor may change without changing the obligation.

A software platform may change without changing the obligation.

A process may become more automated without changing the obligation.

The specification changes only when the operational obligation or its governing conditions change.

---

## 7. Conformance rule

The minimum abstract conformance rule is:

```text
ConformantExecution(E) =
    ApplicableSpecExists(E)
    AND PreconditionsSatisfied(E)
    AND AuthorizationValid(E)
    AND RequiredOutputsProduced(E)
    AND AcceptanceCriteriaSatisfied(E)
    AND RequiredEvidencePresent(E)
    AND ExceptionsValid(E)
```

An organization may add additional conditions, but it SHOULD NOT remove the distinction between execution occurrence and execution conformance.

---

## 8. Lifecycle mapping

The Core Model maps to the SDO lifecycle as follows:

| Lifecycle stage | Primary model objects |
|---|---|
| SPECIFY | Execution Specification |
| VALIDATE | Specification + Inputs + Validation Gate |
| AUTHORIZE | Execution Instance + Authorization |
| EXECUTE | Execution Instance + Trace |
| VERIFY | Result + Evidence + Conformance Evaluation |
| HANDOFF | Verified Result + Handoff Contract + Trace |

Controlled Exceptions may intersect VALIDATE, AUTHORIZE, EXECUTE, VERIFY, or HANDOFF.

---

## 9. Technology independence

The Core Model is conceptual and does not prescribe storage or implementation technology.

It may be represented through:

- forms;
- spreadsheets;
- databases;
- JSON or YAML;
- APIs;
- ERP/CRM/ITSM/WMS/MES systems;
- BPM/workflow engines;
- policy engines;
- AI-agent orchestration platforms;
- custom software;
- physical or administrative control systems.

The implementation may differ. The semantics should remain recognizable.

> **Adapt the implementation. Preserve the principles.**

---

## 10. Minimum SDO conformance

A process implementation can reasonably claim minimum SDO conformance when:

1. its operational obligations are represented by identifiable specifications;
2. executions reference the applicable specification version;
3. completion is separated from result conformance;
4. results are evaluated against explicit acceptance criteria;
5. required evidence supports verification;
6. deviations are handled through visible Controlled Exceptions;
7. handoffs depend on explicit receiving conditions;
8. material execution events remain traceable;
9. the obligation is not unnecessarily coupled to a particular executor or technology.

This is the structural foundation upon which adoption guides, profiles, tooling, maturity models, and domain adaptations can be built.

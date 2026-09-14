# SDO Handoff Model v0.1

> **Concept Draft — normative reference model**

The **SDO Handoff Model** defines how responsibility, verified results, evidence, exceptions, and execution context move from one execution boundary to another without requiring a specific software platform.

SDO distinguishes **communication** from **handoff**.

> **Notification is not handoff.**

An email, message, mention, ticket update, API event, or verbal notice may communicate that work exists or has changed. A handoff occurs only when the receiving conditions are satisfied, or when a Controlled Exception explicitly authorizes transfer.

## 1. Core rule

A handoff is a governed transfer of responsibility.

A valid handoff MUST identify:

- what result is being transferred;
- which Execution Specification and version governed it;
- what evidence supports its conformance;
- which exceptions remain applicable;
- the origin execution boundary;
- the receiving execution boundary;
- whether the receiving conditions are satisfied;
- the trace identifier linking the transfer to the execution history.

## 2. The Handoff Record

The **Handoff Record** is the canonical representation of the SDO handoff.

It is not necessarily a file or database object. It is the minimum information set required to represent the transfer consistently.

A Handoff Record SHOULD contain:

```text
handoff_id
trace_id
source_execution_id
source_spec_id
source_spec_version
result_reference
evidence_references
approved_exception_references
source_boundary
target_boundary
receiving_conditions
receiving_conditions_status
handoff_status
handoff_timestamp
```

Organizations MAY add fields according to their operational, legal, regulatory, or technological needs.

## 3. Receiving Conditions

The receiving boundary defines what must be true before it accepts responsibility.

The sender SHOULD NOT unilaterally determine that a downstream unit is ready to receive work.

Receiving Conditions may include:

- required result state;
- mandatory fields or artifacts;
- required evidence;
- unresolved-risk thresholds;
- approved exceptions;
- authorization state;
- timing conditions;
- dependency state;
- regulatory or policy constraints.

This prevents a common operational ambiguity:

> **The sender believes the work is complete while the receiver believes required information is still missing.**

In SDO, the receiving conditions are explicit before transfer whenever practical.

## 4. Handoff states

A minimal Handoff lifecycle MAY use:

```text
PREPARED
READY_FOR_TRANSFER
TRANSFERRED
ACCEPTED
REJECTED
BLOCKED
CONDITIONALLY_ACCEPTED
```

Meaning:

- `PREPARED` — the source has assembled the handoff information;
- `READY_FOR_TRANSFER` — source-side requirements are complete;
- `TRANSFERRED` — the Handoff Record was delivered through the chosen channel;
- `ACCEPTED` — receiving conditions were satisfied and responsibility transferred;
- `REJECTED` — the receiver evaluated the handoff and refused it;
- `BLOCKED` — transfer cannot proceed because required conditions are missing or invalid;
- `CONDITIONALLY_ACCEPTED` — responsibility transferred under one or more approved Controlled Exceptions.

## 5. Channel independence

SDO does not prescribe the transport mechanism used to carry a Handoff Record.

The same handoff semantics may be implemented through:

- paper or structured forms;
- spreadsheets;
- email plus a governed form or checklist;
- task-management systems;
- ERP, CRM, ITSM, WMS, MES, or project systems;
- BPM/workflow engines;
- shared databases;
- APIs;
- event buses;
- AI-agent orchestration platforms;
- custom software.

The channel is an implementation detail.

> **The channel carries information. The Handoff Record carries responsibility.**

## 6. Sender and receiver responsibilities

### Source responsibility

The source boundary is responsible for:

- producing the required result;
- providing required evidence;
- identifying the applicable specification version;
- declaring applicable approved exceptions;
- assembling the Handoff Record;
- not representing the handoff as complete before receiving conditions are met.

### Receiving responsibility

The receiving boundary is responsible for:

- defining its entry conditions;
- evaluating the incoming Handoff Record;
- explicitly accepting, rejecting, blocking, or conditionally accepting the transfer;
- preserving the transfer decision in the Trace.

## 7. Responsibility transfer rule

Responsibility transfers only when one of the following is true:

1. all required Receiving Conditions are satisfied and the receiver accepts the handoff; or
2. a valid Controlled Exception explicitly authorizes the transfer despite one or more unmet conditions.

Therefore:

```text
TRANSFERRED != ACCEPTED
```

and:

```text
NOTIFIED != HANDED_OFF
```

## 8. Failure behavior

When receiving conditions are not satisfied, the handoff MUST NOT disappear into informal communication.

The receiving boundary should return an explicit state such as:

```text
BLOCKED
REJECTED
EXCEPTION_REQUIRED
```

The reason SHOULD identify the failed condition or missing requirement.

## 9. Handoff chaining

A process may contain multiple execution boundaries:

```text
EXECUTION A
   ↓
HANDOFF A→B
   ↓
EXECUTION B
   ↓
HANDOFF B→C
   ↓
EXECUTION C
```

Each transfer retains a reference to the same Trace or to a traceable parent/child relation.

This allows the organization to answer:

- where responsibility currently resides;
- which handoff failed;
- what information crossed each boundary;
- which exception enabled a conditional transfer;
- which specification version governed each execution.

## 10. Minimal Handoff Record example

```yaml
handoff_id: HND-000123
trace_id: TRACE-000045
source_execution_id: EXEC-000122
source_spec:
  id: SPEC-001
  version: 0.2
result:
  reference: RESULT-000122
  conformance_status: passed
evidence_refs:
  - EV-001
  - EV-002
approved_exception_refs: []
source_boundary: UNIT-A
target_boundary: UNIT-B
receiving_conditions:
  - id: RC-001
    status: satisfied
  - id: RC-002
    status: satisfied
handoff_status: accepted
accepted_at: 2026-09-14T13:00:00Z
```

## 11. Minimum conformance

An implementation conforms to the SDO Handoff Model when:

1. communication and responsibility transfer are treated as distinct concepts;
2. receiving conditions are explicit;
3. a transfer preserves the governing specification reference;
4. result and evidence references travel with the handoff when required;
5. approved exceptions remain visible;
6. the receiver produces an explicit transfer decision;
7. the decision is traceable;
8. no specific transport technology is required by the methodology.

## 12. Design objective

The Handoff Model exists to make SDO practically adoptable across organizations of different sizes and maturity levels.

A company should be able to implement the same transfer semantics using a checklist today, an ERP tomorrow, and APIs or autonomous agents later without redefining the underlying operational contract.

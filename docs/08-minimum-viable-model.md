# SDO Minimum Viable Model

> **Concept Draft v0.2**

The Minimum Viable Model (MVM) defines the smallest complete form of **Specification-Driven Operations (SDO)** that can be applied to any organizational process without depending on industry, department, software platform, workflow technology, or executor type.

SDO governs **execution against a specification**. The methodology is intentionally independent from who or what performs the work.

## 1. Core proposition

A unit of work should not begin, advance, be accepted, or be transferred merely because an executor declares it ready or complete. It advances because the conditions defined by an explicit specification have been satisfied, or because a controlled exception has been formally authorized.

The minimum SDO lifecycle is:

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

A controlled exception path may be entered whenever the normal specification cannot be satisfied.

## 2. Executor Independence

SDO separates the **obligation** from the **executor**.

The Execution Specification defines what must be true: required inputs, preconditions, constraints, expected result, acceptance criteria, evidence requirements, exception policy, and handoff conditions.

The executor is a property of an **Execution Instance**, not a defining property of the obligation.

```text
EXECUTION SPECIFICATION
        │
        ▼
 EXECUTION INSTANCE
        │
        ▼
      RESULT
        │
        ▼
CONFORMANCE CHECK
     /      \
   PASS      FAIL
    │          │
    ▼          ▼
 HANDOFF   REWORK / EXCEPTION
```

A human, team, AI agent, software service, automation, robot, supplier, or other mechanism may produce the result. SDO evaluates the result and evidence against the same applicable specification.

> **Execution is judged by conformance to the specification, not by the identity of the executor.**

Executor independence does not override legitimate governance requirements. A specification or policy may require a certification, authority level, segregation of duties, licensed professional, human approval, approved system, or other execution restriction. These are explicit constraints on a particular execution; they do not make executor identity the foundation of the methodology.

## 3. Minimum entities

An SDO implementation requires the following conceptual entities.

### 3.1 Execution Specification

The authoritative definition of the obligation and the conditions that govern successful execution.

Minimum contents:

- intended outcome;
- required inputs;
- preconditions;
- constraints and business rules;
- required outputs or resulting state;
- acceptance criteria;
- required evidence;
- exception policy;
- handoff conditions;
- version.

### 3.2 Execution Unit

A bounded unit of work governed by one applicable Execution Specification.

An Execution Unit may represent a task, decision, service, review, operation, approval, analysis, delivery, calculation, transformation, or any other meaningful work boundary.

### 3.3 Execution Instance

A concrete occurrence of an Execution Unit performed under a specific version of an Execution Specification.

The Execution Instance records operational facts such as:

- execution identifier;
- applicable specification and version;
- executor identity or mechanism, when traceability requires it;
- timestamps;
- inputs used;
- output/result produced;
- evidence;
- decisions;
- exceptions;
- verification outcome;
- trace.

The executor belongs here because it describes **how a particular execution occurred**, not **what the obligation means**.

### 3.4 Result

The observable output, state change, decision, artifact, service outcome, or other effect produced by an Execution Instance.

The Result is evaluated for conformance against the applicable specification.

### 3.5 Validation Gate

A deterministic or reviewable control that determines whether the required conditions for advancement are satisfied.

A gate evaluates facts against the current specification. It must not silently reinterpret the specification.

### 3.6 Evidence

Information sufficient to support a validation or verification decision.

Evidence may include structured data, documents, measurements, logs, signatures, records, tests, approvals, generated artifacts, sensor values, or other verifiable facts.

### 3.7 Controlled Exception

A formally declared deviation from the normal specification or policy.

An exception must have an explicit reason, scope, authority, risk treatment, validity, and traceable resolution.

### 3.8 Handoff

The governed transfer of a verified result and its required context into another Execution Unit or terminal destination.

## 4. Conformance rule

The central SDO success condition is:

```text
Execution Success = Result conforms to Applicable Specification
```

Conceptually:

```text
Result ⊨ Specification
```

Executor identity may affect authorization, accountability, or regulatory eligibility, but successful completion is established by satisfying the applicable specification and required evidence.

Therefore:

```text
Specification ≠ Executor
Execution ≠ Executor
Correctness ≠ Executor Identity
```

## 5. Minimum states

The MVM uses the following canonical states:

```text
DRAFT
READY_FOR_VALIDATION
VALIDATED
AUTHORIZED
IN_EXECUTION
AWAITING_VERIFICATION
VERIFIED
COMPLETED
```

Supporting states:

```text
BLOCKED
EXCEPTION_REQUESTED
EXCEPTION_APPROVED
CONDITIONALLY_AUTHORIZED
REJECTED
CANCELLED
```

Organizations may add states, but an implementation should preserve the semantic distinction between validation, authorization, execution, verification, exception, and completion.

## 6. Lifecycle rules

### SPECIFY

Create or select the applicable Execution Specification.

Output: a versioned specification complete enough to be validated.

### VALIDATE

Evaluate whether required inputs, preconditions, constraints, and applicable policy conditions are satisfied.

Output: `VALIDATED`, `BLOCKED`, or `EXCEPTION_REQUESTED`.

### AUTHORIZE

Determine whether execution is permitted to begin.

Validation answers: **Are the conditions defined by the specification satisfied?**

Authorization answers: **May this execution proceed now under the applicable authority and policies?**

Output: `AUTHORIZED`, `CONDITIONALLY_AUTHORIZED`, or `REJECTED`.

### EXECUTE

An executor or execution mechanism performs the work within the applicable constraints and produces a result.

SDO does not prescribe the internal implementation method unless that method is itself constrained by the specification or policy.

### VERIFY

Evaluate the produced result and evidence against the acceptance criteria.

Output: `VERIFIED`, rework, rejection, or controlled exception.

### HANDOFF

Transfer the verified result and required context to the next Execution Unit or terminal destination.

A handoff is complete only when the receiving entry conditions are satisfied or a controlled exception explicitly permits the transfer.

## 7. Controlled exception path

An exception is not an escape from SDO. It is an explicit execution state governed by SDO.

```text
CONDITION NOT SATISFIED
       ↓
EXCEPTION REQUEST
       ↓
RISK / IMPACT ASSESSMENT
       ↓
AUTHORITY DECISION
   ┌───────┴────────┐
 APPROVE           DENY
    ↓                ↓
CONDITIONAL       BLOCK / RETURN
AUTHORIZATION
```

Minimum exception record:

- condition not satisfied;
- reason;
- affected scope;
- risk or impact;
- requested action;
- authority required;
- decision;
- compensating controls, if any;
- expiration or closure condition;
- evidence and trace.

**Principle:** SDO does not eliminate exceptions. It eliminates invisible exceptions.

## 8. Handoff contract

Every governed transfer has a minimum handoff contract.

The sending execution must provide:

- verified result;
- required evidence;
- current specification version;
- unresolved conditions, if any;
- approved exceptions, if any;
- traceability identifiers.

The receiving unit must be able to determine, without relying on undocumented conversation, whether its entry conditions are satisfied.

## 9. Execution restrictions

SDO is executor-independent by default, but not executor-blind.

When necessary, policies or specifications may constrain an execution through requirements such as:

- required capability;
- approval authority;
- professional certification or license;
- approved technology or environment;
- segregation of duties;
- mandatory human decision;
- prohibited executor class;
- independent verifier requirement.

These restrictions should be explicit and justifiable. They constrain eligibility for a specific execution without redefining the fundamental work obligation around an executor class.

## 10. Proportional governance

Not every unit of work needs the same level of rigor.

The MVM permits three implementation levels:

### Level A — Lightweight

For low-risk, reversible work.

Minimum: inputs, expected result, acceptance criteria, trace.

### Level B — Controlled

For material operational work.

Adds explicit validation, authorization, evidence, versioning, and exception handling.

### Level C — Assured

For high-impact, regulated, safety-critical, financial, or irreversible work.

Adds independent verification, segregation of duties, stronger evidence retention, explicit authority boundaries, and any mandatory executor restrictions required by policy or regulation.

The SDO model remains the same; rigor scales with risk.

## 11. Minimum traceability

Every execution should be able to answer:

- What specification governed this execution?
- Which version?
- What inputs were used?
- What execution instance produced the result?
- Who or what executed it, when that fact is required for traceability?
- What authority allowed execution?
- What result was produced?
- What evidence supports conformance?
- Which gates were passed?
- Were exceptions used?
- How was the result verified?
- What was handed off next?

The implementation technology may vary, but these questions define the minimum traceability target.

## 12. Technology and executor independence

SDO is a methodology, not a workflow engine and not an automation framework.

The MVM may be implemented with:

- paper or structured forms;
- spreadsheets;
- ERP, CRM, ITSM, WMS, MES, or project systems;
- BPM/workflow engines;
- databases and APIs;
- policy engines;
- AI orchestration platforms;
- industrial automation;
- custom software;
- combinations of these mechanisms.

Likewise, the execution itself may be performed by any mechanism capable and authorized to satisfy the specification.

A change of executor should not require a change to the core specification unless that change alters the obligation, constraints, evidence, or governance requirements.

## 13. Minimum adoption path

A generic SDO pilot can be created with seven steps:

1. Select one bounded process or operational flow.
2. Identify its meaningful Execution Units.
3. Define the expected result and one Execution Specification per unit or reusable unit type.
4. Define validation and authorization gates.
5. Define acceptance criteria and evidence.
6. Define controlled exception rules.
7. Execute, verify conformance, and use exception/rework data to improve the specifications.

The first objective is not maximal automation. It is to replace ambiguous execution boundaries with explicit, testable specifications.

## 14. Success criteria for an SDO MVP

An implementation qualifies as an SDO MVP when:

- at least one process is decomposed into explicit Execution Units;
- each governed unit has a versioned Execution Specification;
- advancement depends on applicable gates rather than status declaration alone;
- verification evaluates the produced result against explicit acceptance criteria;
- completion is supported by defined evidence;
- exceptions are explicit and traceable;
- handoffs expose enough information for the receiving unit to validate entry;
- execution traceability can identify the actual executor when required;
- replacing one eligible executor with another does not require redefining the core work obligation.

That final criterion expresses the executor independence of SDO and is one of the methodology's central portability properties.
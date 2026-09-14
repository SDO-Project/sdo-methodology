# SDO Minimum Viable Model

> **Concept Draft v0.1**

The Minimum Viable Model (MVM) defines the smallest complete form of **Specification-Driven Operations (SDO)** that can be applied to any organizational process without depending on a specific industry, department, software platform, or execution technology.

The model is intentionally generic. It is designed to govern work executed by people, teams, software systems, automations, AI agents, suppliers, or combinations of these actors under the same operational logic.

## 1. Core proposition

A unit of work should not begin, advance, or be transferred solely because someone or something declares it ready. It should advance because the conditions defined by an explicit specification have been satisfied, or because a controlled exception has been formally authorized.

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

## 2. Actor-neutral execution

The SDO MVM separates **what must be true** from **who or what performs the work**.

An Execution Specification defines the required outcome, inputs, constraints, evidence, acceptance criteria, and handoff conditions. It should not depend unnecessarily on whether the executor is a human, an AI agent, a software service, a robot, or a mixed team.

This creates an **actor-neutral execution contract**.

```text
                    EXECUTION SPEC
                          │
              ┌───────────┼───────────┐
              │           │           │
            HUMAN      AI AGENT     SYSTEM
              │           │           │
              └───────────┼───────────┘
                          │
                     SAME OUTCOME
                     SAME EVIDENCE
                     SAME GATES
```

Actor neutrality does not mean every actor is interchangeable. A specification may impose capability, authority, certification, segregation-of-duties, or human-approval requirements. The principle is that these restrictions are declared as part of the specification rather than hidden inside an informal operating convention.

## 3. Minimum entities

An SDO implementation requires only six conceptual entities.

### 3.1 Execution Specification

The authoritative definition of the work to be performed and the conditions that govern it.

Minimum contents:

- purpose or intended outcome;
- required inputs;
- preconditions;
- constraints and business rules;
- required capabilities or authorities;
- expected outputs;
- acceptance criteria;
- required evidence;
- exception policy;
- handoff conditions;
- version.

### 3.2 Execution Unit

A bounded unit of work governed by one Execution Specification.

An Execution Unit may represent a task, decision, service, review, operation, approval, analysis, delivery, or any other meaningful work boundary.

### 3.3 Execution Agent

The actor performing the Execution Unit.

Supported conceptual actor classes:

- human;
- team;
- AI agent;
- software system;
- automation or robot;
- external party;
- hybrid combination.

### 3.4 Validation Gate

A deterministic or reviewable control that decides whether the work is eligible to enter the next state.

A gate evaluates facts against the current specification. A gate should not silently reinterpret the specification.

### 3.5 Evidence

Information sufficient to support a verification decision.

Evidence may include structured data, documents, measurements, logs, signatures, records, test results, approvals, generated artifacts, or other verifiable facts.

### 3.6 Controlled Exception

A formally declared deviation from the normal specification.

An exception must have an explicit reason, scope, approver or authority, risk treatment, validity, and traceable resolution.

## 4. Minimum states

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

Organizations may add states, but an implementation should preserve the semantic distinction between validation, authorization, execution, and verification.

## 5. Lifecycle rules

### SPECIFY

Create or select the applicable Execution Specification.

Output: a versioned specification that is complete enough to be validated.

### VALIDATE

Evaluate whether required inputs, preconditions, constraints, and eligibility conditions are satisfied.

Output: `VALIDATED`, `BLOCKED`, or `EXCEPTION_REQUESTED`.

### AUTHORIZE

Determine whether execution is allowed to begin.

Validation answers: **Can this work proceed according to the specification?**

Authorization answers: **Is this work permitted to proceed now and under this authority?**

Output: `AUTHORIZED`, `CONDITIONALLY_AUTHORIZED`, or `REJECTED`.

### EXECUTE

The assigned Execution Agent performs the work within the specification boundaries.

The executor may choose implementation details when the specification leaves them open, but may not silently redefine the required outcome or constraints.

### VERIFY

Evaluate produced outputs and evidence against acceptance criteria.

Output: `VERIFIED`, return for rework, or enter an exception path.

### HANDOFF

Transfer the verified output and required context to the next Execution Unit.

A handoff is complete only when the receiving unit's entry conditions are satisfied or a controlled exception explicitly allows the transfer.

## 6. Controlled exception path

An exception is not an escape from SDO. It is an explicit execution state governed by SDO.

```text
VALIDATION FAILURE
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

- requirement or condition not satisfied;
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

## 7. Handoff contract

Every inter-unit transfer has a minimum handoff contract.

The sender must provide:

- verified output;
- required evidence;
- current specification version;
- unresolved conditions, if any;
- approved exceptions, if any;
- traceability identifiers.

The receiver must be able to determine, without relying on undocumented conversation, whether its entry conditions are satisfied.

## 8. Executor eligibility

SDO distinguishes the **work contract** from **executor eligibility**.

A specification may state:

```text
eligible_executor_classes:
  - human
  - ai_agent
```

or impose capabilities:

```text
required_capabilities:
  - financial_approval_level_2
  - access_to_customer_record
```

This allows executor substitution without rewriting the process when two different actor classes are legitimately capable of satisfying the same specification.

Examples:

- a human analyst or an AI agent may classify a low-risk document if both satisfy the same acceptance and evidence requirements;
- a payment approval may require a named human authority even if an AI agent prepares the recommendation;
- an automated system may execute a calculation while a human or AI agent verifies anomalous results.

The specification, not the actor type, defines the operational truth.

## 9. Proportional governance

Not every unit of work needs the same level of rigor.

The MVM permits three implementation levels:

### Level A — Lightweight

For low-risk, reversible work.

Minimum: inputs, expected output, acceptance criteria, trace.

### Level B — Controlled

For material operational work.

Adds explicit validation, authorization, evidence, versioning, and exception handling.

### Level C — Assured

For high-impact, regulated, safety-critical, financial, or irreversible work.

Adds independent verification, segregation of duties, stronger evidence retention, explicit authority boundaries, and possibly mandatory human control.

The SDO model remains the same; rigor scales with risk.

## 10. Minimum traceability

Every execution should be able to answer:

- What specification governed this work?
- Which version?
- What inputs were used?
- Who or what executed it?
- What authority allowed execution?
- What output was produced?
- What evidence supports completion?
- Which gates were passed?
- Were exceptions used?
- Who or what verified the result?
- What was handed off next?

The implementation technology may vary, but these questions define the minimum traceability target.

## 11. Technology independence

SDO is a methodology, not a workflow engine.

The MVM may be implemented with:

- paper or structured forms;
- spreadsheets;
- ERP, CRM, ITSM, WMS, MES, or project systems;
- BPM/workflow engines;
- databases and APIs;
- policy engines;
- AI agent orchestration platforms;
- custom software.

A mature implementation may automate gates and evidence collection, but software automation is not required for a process to follow SDO.

## 12. Minimum adoption path

A generic SDO pilot can be created with seven steps:

1. Select one bounded process or workflow.
2. Identify its meaningful Execution Units.
3. Define one Execution Specification per unit or reusable unit type.
4. Define validation and authorization gates.
5. Define evidence and acceptance criteria.
6. Define controlled exception rules.
7. Run executions and use exception/rework data to improve the specifications.

The first objective is not maximal automation. It is to replace ambiguous execution boundaries with explicit, testable contracts.

## 13. Success criteria for an SDO MVP

An implementation qualifies as an SDO MVP when:

- at least one process is decomposed into explicit Execution Units;
- each governed unit has a versioned Execution Specification;
- advancement depends on a gate rather than status declaration alone;
- completion is supported by defined evidence;
- exceptions are explicit and traceable;
- handoffs expose enough information for the receiving unit to validate entry;
- executor identity and class are recorded;
- the specification can, where capability and authority allow, govern more than one executor class without redefining the work contract.

That final criterion is the foundation for hybrid human-agent operations.
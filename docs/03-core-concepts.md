# 3. Core Concepts

## Execution Specification

An **Execution Specification** defines an operational obligation and the conditions under which a concrete execution may be considered conformant.

It may include:

- required data;
- business rules;
- dependencies;
- constraints;
- acceptance criteria;
- required approvals;
- expected outputs;
- evidence requirements;
- exception rules;
- handoff conditions;
- version information.

An Execution Specification is not necessarily a document. It may be represented by structured fields, schemas, forms, records, APIs, workflow definitions, or other machine- and human-readable forms.

The specification SHOULD define the obligation independently from a particular executor or technology unless executor characteristics are themselves legitimate operational requirements.

## Execution Unit

An **Execution Unit** is a bounded operational responsibility governed by an Execution Specification.

It exists to decompose a broader process into explicit obligations that can be validated, authorized, executed, verified, and handed off.

## Execution Instance

An **Execution Instance** is one concrete attempt to satisfy an applicable Execution Specification.

It records what happened in that attempt, including the applicable specification version, actual inputs, executor metadata, authorization, runtime events, result, evidence, exceptions, verification, and handoff.

The executor belongs to the Execution Instance rather than defining the obligation itself.

## Executor

An **Executor** is whoever or whatever performs a particular Execution Instance.

Examples include:

- a person;
- a team;
- a supplier;
- a software service;
- an automation;
- a robot;
- an AI agent;
- a machine;
- a combination of multiple executors.

In SDO, executor identity is secondary to specification conformance. It remains important where authority, accountability, capability, regulation, safety, security, or audit requires it.

## Result

A **Result** is the observable outcome produced by an Execution Instance.

Execution completion alone does not make the result acceptable. The result must be evaluated against the applicable specification.

## Conformance Evaluation

**Conformance Evaluation** determines whether the Result and required Evidence satisfy the active specification.

The central SDO rule is:

```text
Execution Success = Result conforms to Applicable Specification
```

Conceptually:

```text
Result ⊨ Specification
```

Minimum conformance outcomes are:

```text
PASS
FAIL
CONDITIONAL
```

A conditional outcome requires an approved Controlled Exception.

## Validation Gate

A **Validation Gate** evaluates whether the conditions required to advance are satisfied.

A gate may be manual, automated, or implemented through any valid control mechanism.

A gate should return an explicit result such as:

```text
VALID
INVALID
REQUIRES_APPROVAL
EXCEPTION_REQUESTED
```

## Authorization

Validation and authorization are distinct.

A specification can be complete and internally consistent while still requiring approval before execution begins.

```text
VALID ≠ AUTHORIZED
```

Authorization determines whether execution may proceed.

## Execution Contract

An **Execution Contract** governs the conditions under which responsibility may be transferred between Execution Units.

It is normally a projection of the applicable specification and receiving conditions rather than a separate source of operational truth.

## Verification

**Verification** is the act of evaluating the produced Result and required Evidence against the applicable Execution Specification.

Verification produces or supports a Conformance Evaluation.

## Evidence

**Evidence** is objective information supporting a verification or decision.

Examples include:

- test results;
- approvals;
- digital signatures;
- system records;
- measurements;
- photos;
- logs;
- generated reports;
- customer acceptance;
- provenance records.

Evidence requirements should be proportional to operational risk.

## Handoff

A **Handoff** is the validated transfer of responsibility, result, and required context between Execution Units.

In SDO, a handoff should not be inferred merely from task status. It occurs when receiving conditions are met or a Controlled Exception explicitly authorizes transfer.

## Controlled Exception

A **Controlled Exception** is an explicit, justified, authorized, limited, and traceable deviation from the normal specification.

Exceptions are part of the formal model, not an informal bypass around it.

## Trace

A **Trace** is the ordered, attributable history of material events connecting specification, validation, authorization, execution, result, evidence, exceptions, conformance, and handoff.

The trace supports accountability, auditability, diagnosis, learning, and specification improvement.

## Structural rule

SDO separates three layers:

```text
OBLIGATION
Execution Specification

EXECUTION
Execution Instance

CONFORMANCE
Result + Evidence vs Specification
```

This separation allows executors, technologies, and implementation mechanisms to change without redefining the operational obligation when the required result and governing conditions remain the same.

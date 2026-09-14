# 3. Core Concepts

## Execution Specification

An **Execution Specification** defines the conditions under which a unit of work may be executed and verified.

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
- version information.

An Execution Specification is not necessarily a document. It may be represented by structured fields, schemas, forms, records, APIs, workflow definitions, or other machine- and human-readable forms.

## Execution Unit

An **Execution Unit** is a bounded stage of work that receives validated inputs and is responsible for producing an expected output.

Examples include:

- prepare an implementation order;
- approve a purchase;
- schedule a technician;
- deploy a system;
- review a technical design;
- process a customer request.

## Execution Agent

An **Execution Agent** performs work within an Execution Unit.

The agent may be:

- a person;
- a team;
- a supplier;
- a software service;
- an automation;
- a robot;
- an AI agent.

SDO aims to make the execution model independent of agent type.

## Validation Gate

A **Validation Gate** evaluates whether the conditions required to advance are satisfied.

A gate may be:

- automatic;
- manual;
- hybrid.

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

An **Execution Contract** governs the transfer between two Execution Units.

It defines what the receiving unit requires before accepting responsibility for the work.

An Execution Contract may reference one or more Execution Specifications.

## Verification

**Verification** determines whether the result of execution satisfies the criteria defined by the active specification.

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
- customer acceptance.

Evidence requirements should be proportional to operational risk.

## Handoff

A **Handoff** is the validated transfer of responsibility between Execution Units.

In SDO, a handoff should not be inferred merely from task status. It occurs when the receiving conditions are met or a Controlled Exception authorizes the transfer.

## Controlled Exception

A **Controlled Exception** is an explicit, justified, authorized, limited, and traceable deviation from the normal specification.

Exceptions are part of the formal model, not an informal bypass around it.

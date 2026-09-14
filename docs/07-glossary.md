# 7. Glossary

This glossary defines the current working vocabulary of SDO. Terms may change while the methodology remains in Concept Draft.

## Authorization

Formal permission for an Execution Instance to begin or continue work.

## Conditional Authorization

Authorization granted under one or more approved Controlled Exceptions.

## Conformance Evaluation

The determination of whether a Result and its required Evidence satisfy the applicable Execution Specification.

Minimum outcomes are `PASS`, `FAIL`, and `CONDITIONAL`.

## Controlled Exception

An explicit, justified, authorized, bounded, and traceable deviation from one or more normal specification conditions.

## Evidence

Verifiable information used to support verification, approval, completion, exception, or conformance decisions.

## Execution Contract

The structured set of conditions governing a transfer of responsibility between Execution Units. In SDO, it is typically a projection of the applicable specification and downstream receiving conditions rather than a separate source of truth.

## Execution Instance

One concrete attempt to satisfy an applicable Execution Specification.

It records the actual inputs, authorization, executor metadata, runtime events, result, evidence, exceptions, verification, conformance outcome, and handoff outcome for that attempt.

## Execution Specification

The authoritative definition of an operational obligation, including the conditions, data, rules, dependencies, constraints, expected outputs, acceptance criteria, evidence, exception policy, and handoff requirements relevant to execution.

## Execution State

A formally represented state describing the current condition of an Execution Instance, such as `VALIDATED`, `AUTHORIZED`, `IN_EXECUTION`, `AWAITING_VERIFICATION`, `VERIFIED`, or `BLOCKED`.

## Execution Unit

A bounded operational responsibility governed by an Execution Specification.

## Executor

The person, team, system, automation, AI agent, robot, machine, external party, or combination that performs a particular Execution Instance.

Executor identity belongs to the execution, not to the obligation itself, unless the specification explicitly defines executor-related restrictions.

## Handoff

A validated transfer of a Result and required context from one Execution Unit or process boundary to another.

## Living Specification

A specification that evolves explicitly and versionably as operational reality changes.

## Receiving Conditions

The conditions that must be true before a downstream Execution Unit accepts responsibility for work.

## Result

The observable outcome produced by an Execution Instance.

A Result is not considered successful merely because execution ended; it must satisfy the applicable specification through Conformance Evaluation.

## Specification Version

The identifiable version of an Execution Specification that governed a particular validation, authorization, execution, verification, or handoff decision.

## Trace

The ordered, attributable history of material lifecycle events connecting specification, validation, authorization, execution, result, evidence, exceptions, conformance, and handoff.

## Validation

The act of determining whether required conditions to proceed are present, consistent, and eligible for further execution.

## Validation Gate

A manual, automated, or otherwise governed control that evaluates whether an Execution Instance may advance to a subsequent lifecycle state.

## Verification

The act of comparing an execution Result and required Evidence against the applicable Execution Specification.

## Working distinction: Validation vs Verification

SDO currently uses the following distinction:

- **Validation** asks whether the conditions to proceed are satisfied.
- **Verification** asks whether the executed Result satisfies what was specified.

Verification supports the final **Conformance Evaluation**.

## Core equation

```text
Execution Success = Result conforms to Applicable Specification
```

Conceptually:

```text
Result ⊨ Specification
```

This formulation is descriptive of the SDO model and does not prescribe a particular mathematical logic or implementation technology.

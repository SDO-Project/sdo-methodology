# 7. Glossary

This glossary defines the current working vocabulary of SDO. Terms may change while the methodology remains in Concept Draft.

## Authorization

Formal permission for an Execution Unit to begin or continue work.

## Conditional Authorization

Authorization granted under one or more approved Controlled Exceptions.

## Controlled Exception

An explicit, justified, authorized, bounded, and traceable deviation from the normal specification.

## Evidence

Objective information used to support verification, approval, completion, or exception decisions.

## Execution Agent

The actor that performs work. It may be a person, team, supplier, software system, automation, robot, or AI agent.

## Execution Contract

The structured agreement governing the conditions under which responsibility may be transferred between Execution Units.

## Execution Specification

The explicit definition of the conditions, data, rules, dependencies, constraints, expected outputs, acceptance criteria, evidence, and exception rules relevant to execution.

## Execution State

A formally represented state describing the current condition of an execution, such as `VALIDATED`, `AUTHORIZED`, `IN_EXECUTION`, or `BLOCKED`.

## Execution Unit

A bounded stage or unit of work that receives inputs, performs execution, and produces an expected output.

## Handoff

A validated transfer of responsibility from one Execution Unit to another.

## Living Specification

A specification that evolves explicitly and versionably as operational reality changes.

## Receiving Conditions

The conditions that must be true before a downstream Execution Unit accepts responsibility for work.

## Specification Version

The identifiable version of an Execution Specification that governed a particular execution or decision.

## Validation

The act of determining whether required conditions are present, consistent, and eligible for further execution.

## Validation Gate

A manual, automated, or hybrid control that evaluates whether execution may advance to a subsequent state.

## Verification

The act of comparing an execution result against the active specification and its acceptance criteria.

## Working distinction: Validation vs Verification

SDO currently uses the following distinction:

- **Validation** asks whether the conditions to proceed are satisfied.
- **Verification** asks whether the executed result satisfies what was specified.

This distinction will be reviewed against established terminology in adjacent disciplines before SDO reaches a stable version.

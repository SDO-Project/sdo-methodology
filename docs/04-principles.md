# 4. Principles

SDO currently defines the following foundational principles. Their wording may evolve while the methodology is tested.

## 1. Specification Before Execution

Critical work should begin from an explicit specification of the conditions required for execution and completion.

The purpose is not to document everything. The purpose is to make operationally important assumptions explicit before they become downstream defects.

## 2. Actor-Neutral Specification

Define the obligation before selecting the executor.

Where capability and authority permit, the same core Execution Specification should govern human, team, AI-agent, automated-system, external-party, or hybrid execution.

The specification should describe the intended outcome, constraints, evidence, acceptance criteria, and handoff conditions without unnecessarily coupling the work to the way it happens to be performed today.

Actor neutrality does **not** imply unrestricted interchangeability. A specification may require specific capabilities, certifications, access rights, segregation of duties, independent verification, or mandatory human authority. These restrictions should be explicit parts of the execution contract.

The objective is to separate:

- **what must be achieved**;
- **what rules must be respected**;
- **what evidence must exist**;

from:

- **which eligible actor performs this execution**.

## 3. Contract-Based Handoffs

Responsibility should transfer between Execution Units through explicit receiving conditions.

The upstream unit does not unilaterally define when the downstream unit is ready to accept work. The handoff contract must reflect what the receiving execution actually requires.

## 4. Fail-First Validation

Missing, invalid, contradictory, or incomplete conditions should be identified as early as practical.

SDO prefers preventing invalid execution over discovering avoidable defects after downstream work has already consumed resources.

## 5. Living Specifications

Specifications must remain aligned with the reality being executed.

Material changes to scope, constraints, requirements, dependencies, or acceptance criteria must update the active specification and be traceable.

Execution should not silently continue against an obsolete specification.

## 6. Evidence-Based Completion

For critical work, completion should be supported by evidence appropriate to the risk and nature of the activity.

A status change alone is not always sufficient proof that the expected result was achieved.

## 7. Immutable Traceability

Relevant changes, approvals, exceptions, versions, evidence, executor identity, and decisions should preserve an auditable history.

Traceability should support accountability, investigation, learning, and continuous improvement regardless of whether execution was human or machine-performed.

## 8. Controlled Exceptions

SDO must allow real-world deviations without allowing invisible bypasses.

Exceptions should be:

- explicit;
- justified;
- authorized by an appropriate authority;
- limited in scope and duration;
- associated with known risks and mitigation when applicable;
- traceable;
- reviewed when recurrent.

> **SDO does not eliminate exceptions. It eliminates invisible exceptions.**

## 9. Proportional Governance

The rigor of a specification, gate, evidence requirement, and approval path should be proportional to operational risk.

SDO should not require a low-risk routine activity to carry the same governance overhead as a safety-critical, financial, contractual, or irreversible operation.

This principle exists to prevent SDO from becoming bureaucracy for its own sake.

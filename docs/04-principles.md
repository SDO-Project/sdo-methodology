# 4. Principles

SDO currently defines the following foundational principles. Their wording may evolve while the methodology is tested.

## 1. Specification Before Execution

Critical work should begin from an explicit specification of the conditions required for execution and completion.

The purpose is not to document everything. The purpose is to make operationally important assumptions explicit before they become downstream defects.

## 2. Executor Independence

Define the obligation independently from the executor.

SDO evaluates execution by whether the produced result conforms to the applicable specification, not by whether the work was performed by a particular type of actor.

> **Execution is judged by conformance to the specification, not by the identity of the executor.**

The executor may be a person, team, AI agent, software service, automation, robot, supplier, or another mechanism. The methodology does not change because the executor changes.

Executor independence does not mean executor identity is never relevant. Capability, authority, certification, segregation of duties, approved technology, mandatory human control, or other restrictions may be explicitly required where justified by risk, policy, law, regulation, contract, or the nature of the obligation.

The objective is to separate:

- **what must be achieved**;
- **what rules must be respected**;
- **what evidence must exist**;

from:

- **who or what happens to perform a particular execution**.

The executor belongs to the Execution Instance. The obligation belongs to the Execution Specification.

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

Relevant changes, approvals, exceptions, versions, evidence, execution identity, and decisions should preserve an auditable history.

Traceability should support accountability, investigation, learning, and continuous improvement regardless of the execution mechanism used.

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
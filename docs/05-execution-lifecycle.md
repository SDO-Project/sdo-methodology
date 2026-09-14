# 5. Execution Lifecycle

The current SDO lifecycle contains six stages:

```text
SPECIFY → VALIDATE → AUTHORIZE → EXECUTE → VERIFY → HANDOFF
```

## 1. Specify

Define the conditions required for execution.

Typical elements:

- required inputs;
- constraints;
- dependencies;
- responsibilities;
- expected outputs;
- acceptance criteria;
- evidence requirements;
- exception rules.

The specification should be detailed enough to remove material ambiguity without creating unnecessary overhead.

## 2. Validate

Determine whether the specification is complete, internally consistent, and eligible to continue.

Validation may be automatic, manual, or hybrid.

Examples:

- required fields present;
- dates logically consistent;
- dependency completed;
- customer information valid;
- equipment compatible;
- required document attached;
- business rule satisfied.

Validation failure should return actionable information to the responsible origin rather than merely reporting a generic error.

## 3. Authorize

Determine whether execution is permitted to begin.

Authorization may depend on:

- role-based approval;
- budget;
- contractual authority;
- risk classification;
- resource availability;
- exception approval.

A validated work item is not necessarily authorized.

## 4. Execute

The Execution Agent performs the work under the active specification.

Material deviations discovered during execution should not remain implicit. They may trigger:

- specification update;
- revalidation;
- Controlled Exception;
- suspension;
- cancellation.

## 5. Verify

Evaluate the execution result against the active specification and acceptance criteria.

Verification answers:

> Did the execution produce the result that was specified?

Evidence should be collected where appropriate.

## 6. Handoff

Transfer responsibility to the next Execution Unit only when its receiving conditions are satisfied or a Controlled Exception explicitly permits the transfer.

The output of one Execution Unit often becomes part of the specification input for the next.

```text
UNIT A
  ↓ result + evidence
GATE
  ↓ validated handoff
UNIT B
```

## Lifecycle states

A future formal state model may include:

```text
DRAFT
SPECIFIED
VALIDATION_FAILED
VALIDATED
AWAITING_AUTHORIZATION
AUTHORIZED
EXCEPTION_REQUESTED
EXCEPTION_APPROVED
CONDITIONALLY_AUTHORIZED
IN_EXECUTION
AWAITING_VERIFICATION
VERIFIED
HANDED_OFF
COMPLETED
BLOCKED
CANCELLED
```

These states are provisional in Concept Draft v0.1 and require validation against real cases.

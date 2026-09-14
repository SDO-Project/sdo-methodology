# Generic End-to-End SDO Example

> **Public Draft example**

This example demonstrates the minimum SDO flow without depending on a specific industry, department, software platform, or executor type.

The scenario is intentionally generic: one Execution Unit produces a verified result that another Execution Unit can accept.

## 1. Execution Specification

```yaml
spec_id: SDO-EXAMPLE-001
name: Prepare and Transfer a Verified Work Package
version: 0.1
status: active

intent:
  expected_outcome: A complete and verified work package is available for the next execution boundary.

inputs:
  required_inputs:
    - source_record
    - required_context

preconditions:
  - source_record_exists
  - required_context_is_current

outputs:
  required_outputs:
    - verified_work_package

acceptance:
  acceptance_criteria:
    - required_fields_are_complete
    - internal_consistency_check_passes
    - required_evidence_is_present

evidence:
  required_evidence:
    - validation_record
    - verification_record

exceptions:
  allowed: true

handoff:
  downstream_entry_conditions:
    - result_is_verified
    - evidence_is_available
    - active_spec_version_is_recorded
    - approved_exceptions_are_disclosed
```

The specification defines the obligation. It does not prescribe whether the work is performed by a person, software system, automation, AI agent, external party, or another eligible execution mechanism.

## 2. Validate

Before execution begins, the required inputs and preconditions are evaluated.

Possible outcome:

```text
VALIDATED
```

If a required condition is missing, the execution is blocked or a Controlled Exception is requested.

## 3. Authorize

Validation does not automatically imply authorization.

The organization determines whether the Execution Instance is permitted to proceed under the applicable authority and policy.

Possible outcome:

```text
AUTHORIZED
```

## 4. Execute

A concrete Execution Instance is created.

```yaml
execution_id: EXEC-0001
spec_id: SDO-EXAMPLE-001
spec_version: 0.1
executor:
  identity: <recorded_if_required>
  class: <human|system|agent|automation|external_party|other>
```

The executor produces a Result.

```yaml
result_id: RESULT-0001
execution_id: EXEC-0001
status: produced
```

## 5. Verify and evaluate conformance

The Result and required Evidence are evaluated against the active specification.

```text
Result + Evidence
        ↓
Conformance Evaluation
        ↓
       PASS
```

A completed action alone is not sufficient. Success exists only when the result conforms to the applicable specification.

## 6. Create the Handoff Record

The verified result is prepared for transfer.

```yaml
handoff_id: HANDOFF-0001
source_execution_id: EXEC-0001
spec_id: SDO-EXAMPLE-001
spec_version: 0.1
result_ref: RESULT-0001
evidence_refs:
  - VALIDATION-0001
  - VERIFICATION-0001
approved_exceptions: []
receiving_conditions:
  result_is_verified: true
  evidence_is_available: true
  active_spec_version_is_recorded: true
  approved_exceptions_are_disclosed: true
trace_id: TRACE-0001
```

The Handoff Record is the structured representation of the transfer. It may be stored in an ERP, CRM, task manager, workflow engine, spreadsheet, form, API payload, database, document, or another existing channel.

## 7. Notify

A notification may be sent using any available communication channel.

Examples:

- email;
- chat;
- task assignment;
- workflow notification;
- API event.

But:

> **Notification is not handoff.**

The notification only informs the receiver that a transfer is available.

## 8. Receive and accept

The downstream boundary evaluates its Receiving Conditions.

If satisfied:

```text
TRANSFERRED → ACCEPTED
```

If they are not satisfied:

```text
TRANSFERRED → REJECTED / BLOCKED / EXCEPTION_REQUESTED
```

A sender cannot unilaterally declare a successful handoff merely by sending information.

## 9. Full flow

```text
EXECUTION SPECIFICATION
        ↓
     VALIDATE
        ↓
    AUTHORIZE
        ↓
EXECUTION INSTANCE
        ↓
      RESULT
        ↓
RESULT + EVIDENCE
        ↓
CONFORMANCE EVALUATION
        ↓
       PASS
        ↓
  HANDOFF RECORD
        ↓
  EXISTING CHANNEL
        ↓
RECEIVING CONDITIONS
        ↓
      ACCEPT
```

## 10. Why this example is implementation-independent

The same semantic flow could be implemented as:

```text
Form + Spreadsheet
```

or:

```text
Task Manager + Required Fields + Checklist
```

or:

```text
ERP + Workflow Rules
```

or:

```text
API + Schema + Policy Engine + Agent Orchestration
```

The tooling changes. The SDO contract does not.

> **Adapt the implementation. Preserve the principles.**

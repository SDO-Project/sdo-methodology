# Execution Specification v0.2

> **Normative concept draft for SDO**

An **Execution Specification** is the authoritative operational contract for one bounded unit of work under Specification-Driven Operations (SDO).

Its purpose is to define the obligation and the conditions for successful execution independently from undocumented assumptions and, by default, independently from executor identity.

## 1. Design goal

An Execution Specification defines **what must be true before, during, and after execution** without unnecessarily prescribing who performs the work or how the work is internally implemented.

A valid specification is outcome-oriented, constraint-aware, verifiable, versioned, and portable across eligible execution mechanisms.

The central rule is:

> **Execution is judged by conformance to the specification, not by the identity of the executor.**

## 2. Canonical structure

Every Execution Specification SHOULD define the following fields.

### Identity

- `spec_id` — stable identifier;
- `name` — human-readable name;
- `version` — immutable specification version;
- `status` — draft, active, deprecated, retired;
- `owner` — authority responsible for the specification;
- `effective_from` — date/time or version activation point.

### Intent

- `purpose` — why the unit exists;
- `expected_outcome` — result that must be achieved;
- `scope` — what is included;
- `out_of_scope` — explicit exclusions when useful.

### Inputs

- `required_inputs` — data or artifacts required before validation;
- `optional_inputs` — useful but non-blocking context;
- `input_quality_rules` — completeness, freshness, format, provenance, or consistency requirements.

### Preconditions

- `preconditions` — facts that must be true before execution can be authorized.

### Constraints

- `rules` — operational or business constraints;
- `prohibited_actions` — actions explicitly disallowed;
- `time_constraints` — deadlines, windows, or sequencing constraints;
- `resource_constraints` — resource, environment, or system conditions.

### Execution restrictions

Execution restrictions are OPTIONAL and SHOULD only be used when executor-related requirements are operationally, legally, contractually, or risk-relevantly necessary.

- `required_capabilities` — skills, permissions, certifications, tools, or access;
- `authority_requirements` — decision or approval authority required;
- `segregation_rules` — restrictions between executor, approver, or verifier;
- `executor_constraints` — permitted or prohibited executor classes only when explicitly justified.

### Output

- `required_outputs` — produced data, artifact, state change, decision, or service result;
- `output_quality_rules` — required properties of the outputs.

### Acceptance

- `acceptance_criteria` — observable criteria used to determine success;
- `verification_method` — deterministic check, review, test, measurement, or combination;
- `verifier_requirements` — eligibility rules for verification when applicable.

### Evidence

- `required_evidence` — records needed to support the verification decision;
- `evidence_retention` — retention or traceability rules when applicable.

### Exceptions

- `exception_policy` — whether exceptions are allowed and under which classes;
- `exception_authorities` — authority required for each exception class;
- `compensating_controls` — controls required when specific rules are waived;
- `expiration_rules` — limits for temporary exceptions.

### Handoff

- `handoff_requirements` — information and artifacts that must travel with the result;
- `downstream_entry_conditions` — known conditions required by the receiving unit;
- `completion_condition` — condition under which the current unit is considered complete.

### Traceability

- `trace_requirements` — minimum execution events to retain;
- `source_references` — policies, regulations, decisions, standards, or other sources from which the specification derives.

## 3. Normative principles

### 3.1 Specification before execution

Execution MUST NOT be authorized without an applicable specification or an explicitly governed emergency mechanism.

### 3.2 Validation before authorization

Required inputs and preconditions MUST be evaluated before normal authorization.

### 3.3 Executor independence by default

The core work obligation MUST NOT depend on executor identity unless identity or executor class is itself a legitimate requirement.

The executor belongs to the Execution Instance. The obligation belongs to the Execution Specification.

### 3.4 Result-based conformance

Successful execution MUST be established by evaluating the produced result and required evidence against the applicable specification.

Conceptually:

```text
Execution Success = Result conforms to Applicable Specification
```

### 3.5 Capability and authority remain explicit

Executor independence does not remove governance. An execution MAY be constrained by capabilities, authority, certification, segregation of duties, approved technology, or mandatory human control where justified.

### 3.6 Evidence before completion

Where evidence is required, the work MUST NOT transition to `VERIFIED` solely from an executor declaration.

### 3.7 Exceptions are first-class records

A waived or deviated condition MUST NOT disappear from the execution history.

### 3.8 Specification version immutability during an execution decision

The specification version used to authorize execution MUST be recorded. If a material specification change affects active work, the applicable change policy MUST determine whether revalidation is required.

## 4. Executor-independence rule

The following question should be applied when authoring each requirement:

> **Is this requirement about the obligation and expected result, or only about how the work happens to be performed today?**

Requirements about the obligation belong in the core Execution Specification.

Requirements caused only by a particular implementation SHOULD remain outside the core obligation unless they are necessary constraints.

Example:

**Executor-coupled:**

> The analyst must open System X and manually compare fields A and B.

**Executor-independent:**

> Fields A and B must be compared using the current approved records. A mismatch must be recorded and classified before completion.

The second definition preserves the business obligation while allowing any authorized execution mechanism capable of producing a conforming result.

## 5. Execution Instance boundary

The specification defines the obligation. The Execution Instance records what actually happened.

A concrete execution may record:

```yaml
execution_id: EXEC-000123
spec_id: EXAMPLE-001
spec_version: 0.2
executor:
  identity: <human|team|agent|system|service|robot|external_party|other>
  reference: <traceable_identity_if_required>
started_at: <timestamp>
completed_at: <timestamp>
result_refs: []
evidence_refs: []
exceptions: []
```

Changing the executor SHOULD NOT require a new specification version unless that change modifies the obligation, constraints, evidence, risk treatment, or governance requirements.

## 6. Validation result

A validation result should be represented independently from the specification itself.

```yaml
spec_id: EXAMPLE-001
spec_version: 0.2
execution_id: EXEC-000123
validation_status: passed | failed | exception_required
validated_at: 2026-01-01T10:00:00Z
validator: <identity_or_mechanism>
failed_conditions: []
evidence_refs: []
```

## 7. Verification result

```yaml
spec_id: EXAMPLE-001
spec_version: 0.2
execution_id: EXEC-000123
verification_status: passed | failed | conditional
verified_at: 2026-01-01T12:00:00Z
verifier: <identity_or_mechanism>
criteria_results: []
evidence_refs: []
exceptions: []
```

## 8. Portability target

The conceptual specification is implementation-neutral. It may be expressed as JSON Schema, YAML, database entities, workflow forms, policy code, BPMN extensions, APIs, or other machine-readable formats.

The methodology should preserve semantic compatibility even when implementation technology or executor changes.

## 9. Minimal conformance

A specification is minimally conformant with SDO v0.2 when it defines:

1. identity and version;
2. intended outcome;
3. required inputs and preconditions;
4. constraints;
5. required output or resulting state;
6. acceptance criteria;
7. evidence requirements;
8. exception policy;
9. handoff/completion conditions.

Executor eligibility is not a mandatory element of the core specification. Executor-related restrictions are added only when required by governance, risk, law, contract, capability, or policy.

This minimal contract is the reusable foundation of an SDO process.
# 6. Controlled Exceptions

Real operations contain uncertainty, external dependencies, urgent situations, incomplete information, and cases that no specification anticipated.

SDO therefore treats exceptions as a first-class part of the methodology.

The objective is not to eliminate exceptions. It is to eliminate **informal and invisible exceptions**.

> **SDO does not eliminate exceptions. It eliminates invisible exceptions.**

## Exception path

```text
                VALIDATE
                   │
          Specification satisfied?
              /           \
            YES           NO
             │             │
             ▼             ▼
        AUTHORIZE     EXCEPTION REQUEST
                           │
                    justification
                           │
                      risk analysis
                           │
                       approval
                         /     \
                    APPROVED  DENIED
                       │         │
                       ▼         ▼
             CONDITIONAL      RETURN /
             AUTHORIZATION     BLOCK
```

## Mandatory properties

A Controlled Exception should identify, where applicable:

- the specification requirement that cannot be satisfied;
- the reason for the exception;
- the requesting actor;
- the approving authority;
- the operational impact;
- known risks;
- mitigation actions;
- scope;
- validity period or expiration condition;
- affected execution units;
- evidence or supporting information;
- review requirement.

## Exception classes

The initial taxonomy contains six classes.

### Waiver

A known requirement is consciously waived for a specific execution.

### Deviation

The work is authorized to proceed in a way that differs from the active specification.

### Temporary Exception

A deviation is permitted for a limited period or defined set of executions.

### Emergency Override

Urgency requires execution before the normal conditions can be satisfied.

An Emergency Override should receive strong traceability and a mandatory post-execution review when risk justifies it.

### External Dependency Exception

A requirement cannot currently be satisfied because it depends on an external party or condition outside the execution unit's control.

### Spec Gap

Execution reveals a scenario that the current specification does not adequately represent.

A Spec Gap is particularly important because it may indicate that the methodology's specification itself requires evolution.

## Exception recurrence

Repeated exceptions should be treated as operational evidence.

```text
Specification
     ↓
Executions
     ↓
Repeated same exception
     ↓
Specification review
```

If a requirement is repeatedly waived, the organization should ask whether:

- the requirement remains necessary;
- the requirement is incorrectly defined;
- the normal process is unrealistic;
- another specification branch is required;
- organizational behavior is bypassing a legitimate control.

The answer should be based on evidence rather than assumption.

## Conditional authorization

An approved exception should not make an execution appear equivalent to a normally authorized execution.

SDO therefore distinguishes normal authorization from **Conditional Authorization**.

```text
AUTHORIZED
```

means the normal specification was satisfied.

```text
CONDITIONALLY_AUTHORIZED
```

means execution was authorized under one or more explicit exceptions.

This distinction preserves operational visibility and enables later analysis.

# SDO Adoption Model v0.1

> **Concept Draft — implementation guidance**

The **SDO Adoption Model** defines how an organization can adopt Specification-Driven Operations without requiring a dedicated SDO software platform.

The objective is practical adoption with the lowest reasonable implementation burden.

> **Use the systems you already have before adding new ones.**

SDO is a methodology, not a mandatory software layer.

## 1. Adoption principle

An organization SHOULD implement SDO using its existing operational tools whenever those tools can represent the required semantics with acceptable reliability.

New software SHOULD be introduced only when current tools cannot reasonably support the required level of validation, traceability, evidence, handoff control, automation, scale, or risk management.

This principle is called **Implementation Minimalism**.

## 2. What must exist regardless of technology

An SDO implementation requires the organization to be able to represent, at minimum:

- the applicable Execution Specification;
- an Execution Instance;
- the Result;
- required Evidence;
- validation and verification decisions;
- Controlled Exceptions;
- the Handoff Record;
- Traceability.

How these are represented is implementation-specific.

## 3. Adoption levels

SDO defines three reference adoption levels.

These levels are not maturity rankings in which every organization must reach Level 3. The appropriate level depends on risk, volume, complexity, integration needs, and economics.

### Level 1 — Manual

Best suited for:

- pilots;
- low-volume processes;
- small teams;
- proof of concept;
- organizations with limited systems support;
- low-risk or reversible work.

Possible tools:

- paper forms;
- shared documents;
- spreadsheets;
- structured checklists;
- simple shared folders;
- existing email for notification.

Example implementation:

```text
Execution Specification → structured template
Execution Instance      → spreadsheet row / form instance
Evidence                → attached files or references
Validation              → checklist
Exception               → exception form
Handoff                 → handoff checklist + receiver acceptance
Trace                    → IDs and timestamps in the same record
```

An email may notify the receiver, but the email itself SHOULD NOT be treated as the handoff unless it contains or references the required governed Handoff Record.

### Level 2 — System-Assisted

Best suited for:

- recurring operational processes;
- multiple teams;
- moderate volume;
- environments already using management systems.

Possible platforms include existing:

- ERP;
- CRM;
- ITSM;
- project/task management systems;
- BPM platforms;
- WMS/MES;
- SharePoint or equivalent collaboration systems;
- low-code/no-code platforms.

Typical SDO implementation mechanisms:

- mandatory fields;
- structured forms;
- templates;
- status rules;
- conditional fields;
- approvals;
- automation rules;
- attached evidence;
- immutable or auditable history;
- dashboards for blocked or exceptional work.

The objective is to map SDO concepts onto the systems already used for execution.

### Level 3 — Machine-Enforced

Best suited for:

- high-volume execution;
- cross-system processes;
- agentic or automated operations;
- strict compliance requirements;
- complex policy enforcement;
- high-risk or irreversible execution.

Possible mechanisms:

- APIs;
- machine-readable specifications;
- JSON Schema or equivalent schemas;
- policy engines;
- BPM/workflow engines;
- event buses;
- rules engines;
- automated evidence collection;
- digital signatures;
- agent orchestration;
- automated conformance evaluation.

Example:

```text
System A
   ↓
Handoff Record / event
   ↓
Validation Gate
   ↓
Authorization / policy check
   ↓
System, human, agent, or machine execution
   ↓
Evidence + Result
   ↓
Conformance Evaluation
   ↓
Next Handoff
```

Level 3 does not change the SDO methodology. It changes the degree of enforcement and automation.

## 4. Progressive adoption

Organizations SHOULD be able to evolve without redesigning the methodology:

```text
MANUAL
  ↓
SYSTEM-ASSISTED
  ↓
MACHINE-ENFORCED
```

The representation may change while the semantic model remains stable.

For example:

```text
Today:      spreadsheet row
Tomorrow:   ERP record
Later:      API payload + policy engine
```

The Execution Specification, conformance expectations, exception semantics, and handoff obligations SHOULD remain conceptually compatible.

## 5. Generic pilot method

A minimum SDO pilot can be performed with the following sequence.

### Step 1 — Select a bounded process

Choose a process with identifiable execution boundaries and meaningful handoffs.

Prefer a process where ambiguity, missing information, rework, or transfer failures are observable.

### Step 2 — Identify Execution Units

Break the process into bounded units that each produce a meaningful result.

Do not decompose more than necessary for governance.

### Step 3 — Define the expected result

For each Execution Unit, define what must be true when execution succeeds.

Avoid starting from job titles or current executor behavior.

### Step 4 — Define Receiving Conditions

Ask the receiving boundary:

> **What must be true for you to accept responsibility and begin your work?**

Translate the answer into explicit conditions.

### Step 5 — Create the minimum Execution Specification

Capture:

- outcome;
- required inputs;
- preconditions;
- constraints;
- acceptance criteria;
- evidence;
- exception policy;
- handoff requirements.

### Step 6 — Map SDO to existing tools

Identify where each concept will live using the systems already in place.

Example mapping table:

| SDO concept | Existing implementation |
|---|---|
| Execution Specification | task template / SOP / structured form |
| Execution Instance | ticket / task / ERP record |
| Result | structured fields / attached artifact |
| Evidence | attachment / log / approval record |
| Exception | exception field / linked record |
| Handoff Record | task transition / form / linked record |
| Trace | system history / ID / audit log |

### Step 7 — Run the process

Execute real instances under the specification.

Record:

- validation failures;
- blocked handoffs;
- exceptions;
- rework;
- missing conditions;
- ambiguous criteria.

### Step 8 — Improve the specification

Use operational evidence to revise the specification and receiving conditions.

Recurring exceptions SHOULD trigger review.

## 6. Minimum viable tooling test

Before adopting a new platform, an organization SHOULD ask:

1. Can our existing system represent the required fields?
2. Can it identify the governing specification or version?
3. Can it block or flag invalid advancement?
4. Can it store or reference evidence?
5. Can exceptions be recorded explicitly?
6. Can the receiver accept or reject a handoff?
7. Can we reconstruct the execution history?

If the answer is sufficiently yes for the process risk, new software may not be necessary.

## 7. Implementation Minimalism

Implementation Minimalism is a practical SDO principle:

> **Do not add technology merely to claim SDO compliance. Add technology when it materially improves enforcement, scale, reliability, integration, traceability, or risk control.**

A manual implementation that faithfully preserves SDO semantics is preferable to a sophisticated platform that does not.

## 8. Role model without mandatory job titles

SDO defines responsibilities, not mandatory organizational positions.

Possible responsibilities include:

### Spec Owner

Maintains the meaning and version of an Execution Specification.

### Execution Responsibility

Owns or coordinates a concrete Execution Instance when organizational accountability requires it.

### Receiving Responsibility

Defines and evaluates Receiving Conditions.

### Exception Authority

Has authority to approve specified classes of Controlled Exception.

### Verifier

Evaluates the Result and Evidence against the applicable specification.

One person or system may fulfill multiple responsibilities when risk permits. Segregation SHOULD be introduced only where required by policy, regulation, safety, or risk.

## 9. Adoption anti-patterns

The following behaviors conflict with the SDO adoption philosophy:

- requiring a new platform before a pilot can begin;
- copying existing bureaucracy into a digital form without clarifying obligations;
- treating notifications as handoffs;
- creating mandatory fields that do not affect execution or conformance;
- over-specifying low-risk work;
- tying the specification unnecessarily to the current executor;
- introducing automation before the specification is sufficiently clear;
- treating exceptions as failures to hide rather than operational signals to learn from.

## 10. Adoption success criteria

An organization has a viable SDO adoption when:

- work obligations are explicit enough to be evaluated;
- execution boundaries are identifiable;
- receiving conditions are explicit;
- handoffs transfer responsibility intentionally;
- results are verified against the applicable specification;
- evidence is proportionate to risk;
- exceptions are visible and traceable;
- current tools are used effectively where possible;
- changing the executor or implementation does not unnecessarily redefine the obligation.

## 11. Guiding statements

> **Adapt the implementation. Preserve the principles.**

> **Use the systems you already have before adding new ones.**

> **Notification is not handoff.**

The Adoption Model exists to ensure SDO remains a usable organizational methodology rather than becoming dependent on a dedicated software ecosystem.

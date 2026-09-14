# 9. Open Methodology Philosophy

SDO — Specification-Driven Operations — is intended to be an **open, adaptable methodology** for modern organizational execution.

It is not designed as a proprietary operating system, a mandatory software product, or a closed certification scheme. The purpose of SDO is to provide a shared conceptual model that organizations, teams, researchers, practitioners, and technology builders can study, test, adapt, and implement according to their own context.

## 1. Open by design

SDO may be used in different industries, organizational structures, risk levels, and technology environments.

An implementation may use:

- paper or structured forms;
- spreadsheets;
- ERP, CRM, ITSM, WMS, MES, or project-management platforms;
- BPM and workflow engines;
- databases and APIs;
- policy engines;
- automation platforms;
- AI-agent orchestration systems;
- robots or machines;
- custom software;
- combinations of these approaches.

No implementation technology defines SDO.

> **Adapt the implementation. Preserve the principles.**

## 2. Executor independence

SDO is designed for an environment in which the executor of a unit of work may change over time.

The same organizational obligation may be fulfilled today by a person, tomorrow by software, later by an AI agent, or by another execution mechanism that does not yet exist.

For that reason, SDO separates the **obligation** from the **execution instance**.

The specification defines what must be satisfied. The execution records how that obligation was attempted. The result and evidence are then verified against the applicable specification.

> **The executor belongs to the execution. The obligation belongs to the specification.**

The methodology therefore does not define success by executor identity.

> **Execution is judged by conformance to the specification, not by the identity of the executor.**

Executor identity remains relevant where law, policy, authority, certification, accountability, segregation of duties, safety, or risk requires it. Such restrictions should be made explicit rather than embedded as undocumented assumptions.

## 3. Universal does not mean identical

SDO aims to provide a universal execution model, not identical operating procedures for every organization.

Organizations may adapt:

- terminology;
- workflow structure;
- specification granularity;
- evidence requirements;
- exception classes;
- governance levels;
- implementation technology;
- verification mechanisms;
- authority models.

An adaptation remains aligned with SDO when the essential operating principles remain intact.

## 4. What should be preserved

An SDO-aligned implementation should preserve, at minimum:

1. explicit specification of the operational obligation;
2. validation before normal execution or transfer;
3. separation between validation, authorization, execution, and verification where materially relevant;
4. success based on result conformance to the applicable specification;
5. evidence appropriate to the risk of the work;
6. controlled and traceable exceptions;
7. explicit handoff conditions;
8. version and execution traceability;
9. executor independence unless executor identity is itself a legitimate requirement;
10. proportional governance.

Removing these principles may produce a useful workflow, but it should not automatically be described as an SDO implementation.

## 5. Adaptation is encouraged

SDO is expected to evolve through practical use.

Implementers are encouraged to:

- test the methodology in different contexts;
- identify unnecessary complexity;
- identify missing concepts;
- propose terminology improvements;
- publish implementation patterns;
- document failures and edge cases;
- compare SDO with existing methods;
- contribute research and practical examples.

A recurring adaptation should become a candidate for a reusable SDO pattern. A recurring exception should become a candidate for specification improvement.

## 6. No claim of exclusivity

SDO does not claim ownership over the underlying ideas of specifications, workflow validation, evidence, traceability, exception handling, process management, automation, or agentic execution.

Many of these concepts have long histories across software engineering, BPM, quality management, systems engineering, governance, safety engineering, workflow systems, and other disciplines.

The SDO project proposes a particular synthesis for organizational execution and openly documents its development, influences, research, and evolution.

No claim of historical first invention is required for the methodology to be useful.

## 7. Licensing

Unless otherwise noted, the SDO methodology documentation, templates, diagrams, and research notes are published under the **Creative Commons Attribution 4.0 International License (CC BY 4.0)**.

This allows use, sharing, adaptation, and commercial application while requiring appropriate attribution.

See the repository `LICENSE` file for details.

## 8. Publication philosophy

SDO should be published as an evolving methodology rather than presented as a finished doctrine.

Recommended maturity language:

- **Concept Draft** — foundational ideas are still changing;
- **Public Draft** — stable enough for external testing and criticism;
- **Release Candidate** — core semantics are intended to remain stable;
- **1.0** — a stable reference model exists and has been tested through multiple applications.

Public feedback, criticism, experimentation, and adaptation are part of the methodology's development rather than threats to it.

## 9. Guiding statements

> **Specify before execution. Validate before transfer.**

> **SDO does not eliminate exceptions. It eliminates invisible exceptions.**

> **Execution is judged by conformance to the specification, not by the identity of the executor.**

> **Adapt the implementation. Preserve the principles.**

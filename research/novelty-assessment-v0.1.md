# SDO Novelty Assessment

## Executive finding

**Specification-Driven Operations (SDO)** should not currently be presented as if every underlying mechanism were new. The research landscape already contains mature and emerging work on declarative process constraints, artifact-centric business processes, human tasks in workflow systems, adaptive case management, policy-as-code, human-in-the-loop controls, agentic orchestration, and specification-driven work in software and engineering.

However, this review did **not** identify an established, general-purpose organizational methodology that combines all of the following as one coherent operating model:

1. a versioned **Execution Specification** as the authoritative contract for operational work;
2. a lifecycle separating **Specify → Validate → Authorize → Execute → Verify → Handoff**;
3. formal, traceable **Controlled Exceptions** rather than informal bypasses;
4. evidence-based completion and immutable execution traceability;
5. **actor-neutral execution**, where the core work contract is intentionally separated from executor identity;
6. the ability for the same specification, acceptance criteria, gates, evidence requirements, and handoff contract to govern a human, AI agent, software system, team, or hybrid executor, subject to capability and authority constraints;
7. application at the organizational operations level rather than only software engineering, AI-agent runtime governance, or workflow-engine implementation.

The strongest potential contribution of SDO is therefore **not specification, workflow validation, or human-AI orchestration in isolation**. Its most defensible differentiation is the synthesis of those ideas into a **technology-independent, actor-neutral methodology for organizational execution**.

This is an assessment of conceptual differentiation, not a legal opinion, patent search, trademark clearance, or proof that no prior publication has ever proposed an equivalent idea.

---

## 1. Research question

The central question is:

> Does an existing methodology already treat organizational work as specification-governed execution in which humans and AI agents can operate as interchangeable or composable execution actors under the same work contract, validation gates, evidence model, exception model, and handoff semantics?

The review considered both historical process-management research and the rapidly evolving 2025–2026 agentic-AI landscape.

---

## 2. Origins: Spec-Driven Development

The immediate intellectual inspiration for SDO is **Spec-Driven Development (SDD)**: the recent AI-native engineering movement in which structured specifications become an authoritative source of truth for implementation and verification.

Recent SDD work explicitly positions specifications as a mechanism for constraining probabilistic AI execution and improving reliability, traceability, and governance in software engineering. Alenezi's 2026 paper, for example, describes SDD as a structured specification-centered approach for AI-native enterprise software engineering and proposes specification contracts and deterministic validation around agentic delivery.[1]

Open-source SDD implementations go further by treating specifications as a shared source of truth for both humans and AI coding agents. SpecDD explicitly states that humans and AI agents can work from the same local specifications describing intent, architecture, behavior, boundaries, and completion criteria.[2]

These sources strongly support the intellectual bridge from SDD to SDO. They do not, however, establish a general organizational operations methodology. Their center of gravity remains software, infrastructure, automation, documentation, or engineering delivery.

**Implication for SDO:** the origin story is credible, but SDO should describe itself as a generalization of a spec-driven principle rather than claiming that specifications as execution contracts are new.

---

## 3. Declarative process management: Declare and related work

Long before current AI agents, Business Process Management research developed **declarative process modeling**. Declare is a prominent example. Instead of prescribing every allowed sequence of activities, Declare defines constraints that execution traces must satisfy. An executor may choose among multiple valid paths so long as constraints are respected.[3]

This is conceptually close to one part of SDO: defining obligations and constraints while leaving execution freedom. Declare demonstrates that the idea of specifying the boundaries of valid execution rather than prescribing every step is established process-management research.

Declare also supports runtime monitoring and conformance checking. This overlaps with SDO's Validation and Verification concepts.

What Declare generally does **not** provide as a methodology is SDO's proposed organizational contract structure around inputs, authority, evidence, executor eligibility, controlled exceptions, and handoff semantics. It is primarily a declarative process-modeling language and formalism.

**Assessment:** strong prior art for constraint-based execution; not an equivalent to SDO.

---

## 4. Artifact-centric business process management and GSM

IBM research on **business artifacts** and the **Guard-Stage-Milestone (GSM)** lifecycle is another significant antecedent. Artifact-centric BPM models a business entity together with its relevant information and lifecycle. GSM uses guards, stages, and milestones to govern when work becomes active and when business objectives are achieved.[4]

Earlier artifact-centric research also formalized business artifacts as information models plus lifecycle models, with services consulting and updating artifact state and with pre/post conditions controlling execution.[5]

This is close to SDO in several important respects:

- data and execution state are linked;
- progression is condition-driven;
- entry into stages can be guarded;
- milestones provide state-based completion semantics;
- the model is less rigid than traditional control-flow diagrams.

Nevertheless, artifact-centric BPM is a process/data modeling paradigm. It does not appear to define the same actor-neutral work contract that SDO proposes, nor does it center the methodological idea that humans, AI agents, and software systems should be governed by the same reusable Execution Specification whenever capability and authority permit.

**Assessment:** one of the closest historical conceptual foundations for SDO's data/state/gate model; still materially different in purpose and framing.

---

## 5. Human tasks as service-like process participants

The idea that humans can participate in automated process infrastructure is also established. The OASIS **WS-HumanTask** standard, approved in 2010, explicitly defines human tasks and their lifecycle. It describes human tasks as services implemented by people and provides interfaces and coordination semantics for integrating human work into service-oriented applications.[6]

This matters because SDO should not claim novelty merely from treating human work as something that can be formally orchestrated.

WS-HumanTask, however, makes a distinction around human tasks; it does not propose a single actor-neutral specification intended to allow the same work contract to be dispatched to a human, an AI agent, or another executor class.

**Assessment:** prior art for formal human participation in machine-orchestrated workflows, but not for SDO's proposed actor-neutral abstraction.

---

## 6. Adaptive Case Management and CMMN

The Object Management Group's **Case Management Model and Notation (CMMN)** addresses less predictable, knowledge-intensive work. CMMN is centered around evolving case information and allows activities to occur in flexible orders based on events and conditions. OMG describes it as complementary to BPMN and notes that it supports less structured work where humans remain central to decision-making.[7]

CMMN is relevant because it demonstrates that operational flexibility and living information are already well-established concerns. SDO should therefore avoid positioning itself merely as a solution for processes that cannot be fully predetermined.

The difference is again the center of abstraction. CMMN models cases and knowledge work. SDO proposes to govern any Execution Unit through an explicit versioned contract and to separate that work contract from the actor that performs it.

**Assessment:** adjacent but not equivalent.

---

## 7. Contract-based workflow execution

Academic work has also explored **contract-based workflow execution**. A 2020 paper proposed a contract-based, event-driven execution framework for artifact-centric business processes in dynamic collaborative environments.[8]

This terminology is particularly relevant to SDO's concept of an Execution Contract and warns against claiming that contract-governed workflow is itself new.

The SDO distinction should therefore not be "workflows with contracts." Instead, the proposed contribution is a broader methodology in which the versioned Execution Specification is the operational source of truth and the contract remains stable across eligible executor classes.

**Assessment:** close terminology and execution mechanism; insufficient evidence of a general actor-neutral organizational methodology.

---

## 8. Human-AI and agentic process orchestration

The biggest challenge to an SDO novelty claim comes from the current wave of **agentic orchestration**.

Camunda now explicitly supports AI agents inside BPMN workflows alongside human tasks, deterministic rules, and system integrations. Its documentation states that agentic orchestration allows AI agents, human tasks, and deterministic rule sets to collaborate in end-to-end processes.[9] Camunda also separates agent decisions from process execution: the LLM chooses tools while the process engine executes governed BPMN activities, stores variables, applies retries, and routes human tasks and events.[10]

This establishes several points that SDO cannot claim as new:

- humans and AI agents can coexist in the same end-to-end business process;
- agents can execute non-deterministic portions of a process;
- human escalation can be modeled;
- process engines can provide auditability, state, retries, and deterministic control around AI behavior.

Microsoft's 2026 Agentic AI maturity model similarly tells organizations to redesign processes explicitly around human-agent collaboration, including what agents do, how humans retain control, what systems and data agents need, and how success is measured.[11]

Current management thinking also increasingly describes a **hybrid workforce** of human and AI workers. McKinsey, for example, discusses organizations deploying human or AI talent and redesigning operating models around agentic work.[12]

These developments make one conclusion clear: **hybrid human-agent operations are not by themselves a novel SDO concept.**

The narrower question is whether the *same work specification* is the stable unit that governs either actor.

---

## 9. Policy-as-code and governance-by-construction

A second major overlap comes from **policy-as-code** and runtime agent governance.

IBM describes policy-as-code as machine-readable, automatically enforced rules and constraints. For agentic AI, IBM highlights separation between model reasoning and the system that decides which actions are permitted, with policy enforcement before tools or underlying systems are touched.[13]

IBM Research's 2026 **Governance by Construction for Generalist Agents** goes further. It proposes typed governance primitives applied at multiple runtime checkpoints: intent, planning, tool calls, human approvals, and output formatting. The goal is predictable, auditable, compliance-aware agent execution.[14]

The 2026 SARC framework similarly treats constraints as first-class specification objects and compiles them into pre-action gates, runtime monitoring, post-action auditing, and escalation routing for agentic systems.[15]

These approaches overlap heavily with SDO's ideas of:

- deterministic gates;
- explicit constraints;
- runtime enforcement;
- human approval boundaries;
- auditability;
- structured exceptions and escalation.

Their principal difference is scope: they govern AI-agent execution rather than define a general organizational operating methodology applying the same contract to human and non-human executors.

**Assessment:** very strong prior art for machine-enforced governance, but not an equivalent organizational methodology.

---

## 10. Shared specifications for humans and AI agents

This area contains the strongest evidence that the actor-neutral concept has nearby precedents.

### 10.1 SpecDD

SpecDD describes specifications as a shared source of truth for humans and AI agents in software, infrastructure, automation, and documentation work.[2] This directly overlaps with the idea that multiple actor classes should consume the same specification.

Its scope is nevertheless primarily development and technical delivery.

### 10.2 Design-OS

The 2026 **Design-OS** research framework extends specification-driven execution beyond software into engineering system design. Its authors describe specifications as the shared contract between human designers and AI agents, with structured artifacts maintaining traceability and supporting agent-augmented execution.[16]

This is an important adjacent work and materially weakens any broad claim that SDO is the first attempt to extend specification-driven human-AI work beyond software development.

Design-OS is, however, a domain-specific engineering design workflow rather than a general organizational operations methodology.

### 10.3 Engineering execution under a common specification

A 2026 engineering operating model described by FTT explicitly states that humans and agents operate against the same specification, tickets, and definition of done, with agents able to claim work and escalate to human specialists.[17]

This is extremely close to the proposed SDO hybrid-workforce idea. Its scope remains software engineering, and it does not establish the broader lifecycle, exception taxonomy, handoff contract, or generic organizational Execution Specification proposed by SDO.

### 10.4 Agent-neutral assurance

The **ae-framework** describes itself as an "agent-neutral assurance control plane" in which coding agents, human maintainers, CI jobs, and formal tools are replaceable producers while specifications, verification evidence, policy gates, and release judgments remain stable.[18]

Conceptually, this is one of the closest analogues to SDO's actor-neutral thesis. Again, the domain is the software-development lifecycle.

**Assessment:** actor-neutral or actor-shared specification concepts clearly exist in technical domains. SDO's potential novelty depends on generalizing and formalizing the model for arbitrary organizational operations.

---

## 11. Framework-agnostic agent specifications

The **Open Agent Specification** introduced in 2026 provides a shared declarative representation for AI agents and workflows across heterogeneous runtime frameworks. It holds the agent/workflow design constant while allowing multiple runtimes to execute the same specification.[19]

This is analogous to SDO's separation between a specification and the executor/runtime, but the executor classes are AI-agent frameworks rather than humans, teams, systems, and agents under one organizational methodology.

The conceptual lesson is still valuable: **specification portability** is a credible architectural principle. SDO can extend this idea from runtime portability to executor portability, subject to eligibility and authority.

---

## 12. Emerging human-agent collaboration research

Recent research increasingly treats human-agent collaboration as an organizational and workflow-design problem rather than merely a user-interface problem.

A 2025 paper proposed a layered architecture for sustained human-agent collaboration in which process becomes an explicit, inspectable, adaptable layer.[20]

A September 2026 framework for AI augmentation argues that workplace analysis should move beyond isolated tasks to entire workflows and includes human control, accountability, recovery, learning, and durable value as conditions for meaningful augmentation.[21]

A 2026 paper on agentic business process management studies how autonomy, traceability, tractability, correctness assurance, and process technology can be combined in different orchestration designs.[22]

These sources confirm that the research frontier is rapidly moving toward hybrid human-agent operations. They also mean SDO must be defined precisely enough to distinguish itself from the generic claim that "humans and agents collaborate in workflows."

---

## 13. Comparison matrix

| Approach | Explicit specification/constraints | Runtime gates | Evidence/trace | Exceptions/escalation | Humans + AI in same process | Same contract across executor classes | General organizational methodology |
|---|---:|---:|---:|---:|---:|---:|---:|
| Traditional BPM/BPMN | Partial | Yes | Yes | Yes | Increasingly | Usually no | Yes, process-centric |
| Declare | Yes | Yes | Conformance-focused | Constraint violation | Actor-agnostic at model level | Not its central thesis | Process-modeling formalism |
| Artifact-centric / GSM | Yes | Yes | State/data-centric | Event/condition driven | Possible | Not central | Process/data paradigm |
| CMMN | Yes | Yes | Case history | Flexible/adaptive | Human-centric | No | Case-management standard |
| WS-HumanTask | Task contract | Lifecycle controls | Yes | Task lifecycle | Human + services | No | Integration standard |
| Policy-as-code | Yes | Yes | Strong | Approval/escalation | Often | Usually policy applies primarily to systems/agents | Governance mechanism |
| Camunda agentic orchestration | BPMN/process model | Yes | Strong | Strong | Yes | Different BPMN task semantics commonly used | Platform/process approach |
| SpecDD / agent-neutral SDLC frameworks | Yes | Yes | Strong | Varies | Yes | **Yes, in technical delivery** | Domain-specific |
| Design-OS | Yes | Stage-driven | Strong | Varies | Yes | Shared contract | Engineering-design framework |
| **SDO proposal** | **Yes** | **Yes** | **Yes** | **First-class controlled exceptions** | **Yes** | **Yes, as a core organizational abstraction** | **Target: general-purpose** |

The table illustrates why SDO should be described as a **distinct synthesis** rather than as an invention of each individual mechanism.

---

## 14. The strongest defensible SDO contribution

The research supports positioning the SDO contribution around four connected ideas.

### 14.1 The Execution Specification as the organizational source of truth

The specification is not supporting documentation. It is the operational contract against which readiness, authority, execution, verification, and handoff are evaluated.

### 14.2 Actor-neutral execution

The core specification describes the obligation independently of the executor where possible.

The actor is selected according to capability, authority, risk, availability, cost, policy, or other eligibility rules.

This allows a process to evolve from human execution to AI-assisted execution to autonomous execution without rewriting the business obligation itself.

### 14.3 One governance semantics for humans and machines

Validation gates, acceptance criteria, evidence, exception records, versioning, and handoffs should have the same semantic meaning regardless of whether work is performed by a person or software.

Actor-specific execution profiles may add controls, but they do not silently redefine the core contract.

### 14.4 Controlled substitution

If multiple executor classes satisfy the required capabilities and authority, an Execution Unit may be reassigned without redefining its intended outcome.

This is potentially important for future hybrid organizations because it moves the design question from:

> "Is this a human task or an AI task?"

Toward:

> "What must be achieved, what constraints apply, and which eligible executor is appropriate for this execution?"

That is a materially different organizational abstraction from many current workflow systems, which model human tasks, service tasks, and AI-agent tasks as distinct execution types.

---

## 15. Novelty assessment

### What is clearly not novel

SDO should **not** claim invention of:

- process validation or gates;
- declarative constraints;
- workflow engines;
- structured handoffs;
- evidence or audit trails;
- exception management;
- human-in-the-loop AI;
- humans and AI agents participating in one process;
- specifications used by humans and AI in software/engineering;
- policy-as-code or machine-enforced governance.

### What appears differentiated

Based on the sources reviewed, the following combination appears comparatively underdeveloped as a named, general-purpose methodology:

> **A specification-driven organizational operating model in which a bounded unit of work is defined independently from its executor, and the same versioned contract governs validation, authorization, execution outcome, evidence, verification, controlled exceptions, traceability, and handoff for humans, AI agents, systems, or hybrid executors.**

### Confidence

**Moderate confidence** that this is a meaningful conceptual differentiation.

**Low confidence** in any absolute claim of first invention. The relevant literatures are broad, terminology is fragmented, and the agentic-work landscape is changing weekly in 2026.

The correct current language is therefore:

> "SDO proposes..."

or:

> "A distinguishing principle of SDO is..."

not:

> "SDO is the first methodology ever to..."

---

## 16. Research implications for the methodology

The research suggests four refinements that should be incorporated into SDO.

### 16.1 Make actor neutrality explicit

Actor-neutral execution should become a named foundational principle rather than a secondary implementation detail.

Proposed principle:

> **Actor-Neutral Specification:** Define the obligation before selecting the executor. Where capability and authority permit, the same core Execution Specification should govern human, agentic, automated, or hybrid execution.

### 16.2 Separate capability from authority

AI agents make this distinction especially important. An actor can be technically capable of performing an action while lacking organizational authority to do it.

The Execution Specification should therefore model both.

### 16.3 Use execution profiles rather than separate process definitions

Where human and AI executors need different safeguards, actor-specific profiles should extend the common specification rather than duplicate the process.

### 16.4 Preserve human-control requirements as contract rules

Actor neutrality must not become "automation by default." A specification can explicitly require human judgment, independent verification, segregation of duties, or mandatory human authorization.

This allows SDO to support both autonomy and governance without treating either as universal.

---

## 17. Falsifiable test of the SDO thesis

The SDO actor-neutral claim should eventually be tested empirically.

A useful pilot would select a real process containing several Execution Units and implement the same specifications under different executor configurations:

- human-only;
- human + deterministic automation;
- human + AI agent;
- AI agent with human exception/authorization;
- mixed dynamic assignment.

Metrics should include:

- rework rate;
- invalid handoffs;
- exception frequency;
- time to detect missing information;
- cycle time;
- evidence completeness;
- specification changes required when executor class changes;
- number of business rules duplicated across executor-specific workflows;
- auditability and recovery from failed execution.

The most important architectural metric may be **executor substitution cost**: how much the work contract must change when execution moves from one eligible actor class to another.

If SDO is truly actor-neutral, substitution should primarily change executor profiles and assignment policy, not the core business specification.

---

## 18. Recommended positioning

For the current Concept Draft, the recommended positioning is:

> **Specification-Driven Operations (SDO) is a proposed methodology for governing organizational work through explicit, versioned execution specifications. Its distinguishing objective is to separate the work contract from the executor, allowing people, teams, systems, automations, and AI agents to operate under a common lifecycle of validation, authorization, execution, verification, controlled exception, evidence, and handoff.**

A shorter formulation is:

> **Define the work once. Govern every executor by the contract.**

This formulation is more defensible than presenting SDO as simply "SDD applied to business processes" and more differentiated than generic human-AI orchestration.

---

## Sources

1. Mamdouh Alenezi. "Specification-Driven Development as the Foundation of AI-Native Enterprise Software Engineering." arXiv, July 2026. https://arxiv.org/abs/2607.16680
2. SpecDD. "Spec-Driven Development framework." GitHub. Accessed September 2026. https://github.com/specdd/specdd
3. Fabrizio Maria Maggi et al.; overview in "Declarative Process Specifications: Reasoning, Discovery, Monitoring." Springer, 2022. https://link.springer.com/chapter/10.1007/978-3-031-08848-3_4
4. Richard Hull et al. "Business artifacts with guard-stage-milestone lifecycles: Managing artifact interactions with conditions and events." IBM Research / DEBS 2011. https://research.ibm.com/publications/business-artifacts-with-guard-stage-milestone-lifecycles-managing-artifact-interactions-with-conditions-and-events
5. IBM Research. "Automatic verification of data-centric business processes." ICDT 2009. https://research.ibm.com/publications/automatic-verification-of-data-centric-business-processes
6. OASIS. "Web Services – Human Task (WS-HumanTask) Specification Version 1.1." 17 August 2010. https://www.oasis-open.org/standard/ws-humantask-1-1/
7. Object Management Group. "Case Management Model and Notation (CMMN)." https://www.omg.org/cmmn/index.htm
8. Kan Ngamakeur and Sira Yongchareon. "A contract-based workflow execution framework for realizing artifact-centric business processes in a dynamic and collaborative environment." International Journal of Web Information Systems 16(4), 2020. DOI: 10.1108/IJWIS-04-2020-0020.
9. Camunda. "Agentic orchestration." Camunda 8 Documentation, version 8.9. https://docs.camunda.io/docs/components/agentic-orchestration/agentic-orchestration-overview/
10. Camunda. "AI agents." Camunda 8 Documentation, version 8.9. https://docs.camunda.io/docs/components/agentic-orchestration/ai-agents/
11. Microsoft. "Agentic AI maturity model — Business strategy." Microsoft Learn, updated May 20, 2026. https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/maturity-model-business-process
12. McKinsey & Company. "The agentic organization: contours of the next paradigm for the AI era." 2025–2026. https://www.mckinsey.com/capabilities/people-and-organization/our-insights/the-agentic-organization-contours-of-the-next-paradigm-for-the-ai-era
13. IBM. "What is policy as code?" June 18, 2026. https://www.ibm.com/think/topics/policy-as-code
14. Segev Shlomov et al. "Governance by Construction for Generalist Agents." IBM Research / ACM Conference on AI and Agentic Systems, 2026. https://research.ibm.com/publications/governance-by-construction-for-generalist-agents
15. Gaston Besanson. "SARC: A Governance-by-Architecture Framework for Agentic AI Systems." arXiv, May 2026. https://arxiv.org/abs/2605.07728
16. H. Sinan Bank, Daniel R. Herber, Thomas H. Bradley. "Design-OS: A Specification-Driven Framework for Engineering System Design with a Control-Systems Design Case." arXiv, March 2026. https://arxiv.org/abs/2603.20151
17. FTT. "New Engineering Model." August 2026. https://www.ftt.ai/post/new-engineering-model
18. ITDO Inc. "ae-framework: Agent-Neutral Assurance Control Plane for Agent-Driven SDLC." GitHub, 2026. https://github.com/itdojp/ae-framework
19. "Open Agent Specification: Enabling Cross-Framework Comparison of AI Agents." ACM Conference on AI and Agentic Systems, 2026. https://doi.org/10.1145/3786335.3813130
20. Yun Wang and Yan Lu. "Interaction, Process, Infrastructure: A Unified Architecture for Human-Agent Collaboration." arXiv, June 2025. https://arxiv.org/abs/2506.11718
21. CIVIC-AI Collaboration et al. "When Does AI Augment Work? A Workflow-Level Framework for Human-Agent Collaboration." arXiv, September 2026. https://arxiv.org/abs/2609.12482
22. Stefanie Rinderle-Ma et al. "Design and Implementation of Agentic Orchestrations and Orchestration of Agents." arXiv, June 2026. https://arxiv.org/abs/2606.31518

---

## Research status

**Version:** Research Draft v0.1  
**Assessment date:** September 2026  
**Status:** Working literature and landscape review. Additional academic database, standards, trademark, and patent research is recommended before any formal claim of originality or public launch.
# Executor Independence — Differentiation Note v0.1

## Executive conclusion

The refinement from **hybrid human–agent execution** to **executor-independent execution** materially strengthens the conceptual differentiation of Specification-Driven Operations (SDO).

SDO should not claim that declarative workflows, result validation, agent-neutral protocols, human-in-the-loop controls, or specification-driven execution are individually novel. Existing systems and research already cover important parts of that territory.

The more defensible SDO proposition is broader:

> **The operational obligation is defined independently from the executor. Execution success is determined by conformance of the result to the applicable specification.**

Under this model, the executor is a property of a concrete Execution Instance, not a defining property of the work obligation.

## The distinction

Many existing approaches separate *what* from *how* at some level, but they are usually bounded by a specific technical domain:

- declarative workflow systems separate workflow descriptions from programmatic implementation;
- agent protocols separate decision intent from particular agent implementations;
- scientific workflow systems separate analysis definitions from execution backends;
- software specification approaches separate expected product behavior from implementation technology;
- orchestration platforms coordinate humans, services, and agents as different execution components.

SDO generalizes the abstraction to **organizational execution itself**.

The canonical relationship is:

```text
EXECUTION SPECIFICATION
        ↓
EXECUTION INSTANCE
        ↓
RESULT
        ↓
CONFORMANCE CHECK
```

The executor may be recorded for accountability, authority, safety, law, certification, segregation of duties, or traceability, but the executor does not define the semantic meaning of the obligation.

## Why this differs from a hybrid model

A hybrid model normally begins with multiple actor classes and asks how to coordinate them:

```text
Human + AI + System → Workflow
```

SDO instead begins with the obligation:

```text
Specification → Execution → Result → Conformance
```

Only after the obligation is defined does an actual execution acquire an executor.

This makes human/AI collaboration a possible implementation of SDO rather than a defining characteristic of SDO.

## Nearby prior art

### Microsoft Agent Framework — Declarative Workflows

Microsoft's declarative workflows define workflow logic in YAML and emphasize describing what the workflow should do rather than implementing workflow control programmatically. This is a strong precedent for declarative execution but remains a software/agent workflow framework rather than a general organizational methodology.

Source: https://learn.microsoft.com/en-us/agent-framework/workflows/declarative

### FAST-HEP / Flow

FAST-HEP separates scientific workflow description from implementation and execution backends. Its authors explicitly describe replaceable execution capabilities and backend-independent plans. This is conceptually close to executor independence, but its object is computational/scientific workflow execution.

Source: https://arxiv.org/abs/2608.18745

### SDEP / Spice

The SDEP protocol describes itself as executor-agnostic and separates a decision about what should be done from execution of that decision. Different agents can implement the same wire contract. This is strong prior art for executor-agnostic technical execution interfaces, but it is an agent-system protocol, not a general organizational execution methodology.

Source: https://github.com/Dyalwayshappy/Spice

### Google Agent Executor

Google's Agent Executor provides durable execution for different runtime actors such as agents, agent harnesses, skills, tools, and sandboxes. It abstracts runtime execution infrastructure but remains specifically an agent runtime standard.

Source: https://cloud.google.com/blog/products/ai-machine-learning/agent-executor-googles-distributed-agent-runtime

### Open Specification

Open Specification defines technology-agnostic software specifications that describe outcomes and constraints while allowing different implementation technologies. This demonstrates the portability of specifications across implementations, but its scope is software development.

Source: https://open-specification.org/

### Agentic Execution Protocol

AEP defines a vendor-neutral execution protocol in which the same contract can govern agents, workflows, tools, and remote calls. Its focus is execution context, provenance, cost, and governance across AI workflows rather than organizational methodology.

Source: https://aceteam.ai/docs/aep-whitepaper

## Current differentiation hypothesis

The research so far supports the following cautious proposition:

> SDO appears differentiated not because it invents executor-agnostic contracts or specification-driven execution, but because it elevates **executor independence + specification conformance** into a general-purpose methodology for organizational operations, independent of industry, workflow platform, software stack, and executor class.

The combination currently being developed includes:

1. specification before execution;
2. executor-independent work obligations;
3. result-based conformance;
4. explicit validation and authorization;
5. evidence-based verification;
6. controlled exceptions;
7. governed handoffs;
8. immutable traceability;
9. proportional governance;
10. technology-independent applicability to organizational work.

## What SDO should not claim yet

SDO should not currently claim:

- to be the first executor-agnostic execution model;
- to be the first specification-driven workflow approach;
- to be the first system where humans and agents can satisfy a common contract;
- that no equivalent academic or industrial approach exists anywhere.

A stronger and more defensible claim is:

> **SDO is being developed as a universal organizational execution methodology in which the specification defines the obligation and successful execution is determined by result conformance, independent by default from the executor used to produce that result.**

## Research status

This is a conceptual differentiation assessment, not a patent novelty search, legal opinion, trademark clearance, or exhaustive proof of historical priority.

Further research should include BPM literature, declarative process modeling, artifact-centric BPM, workflow patterns, outcome-based contracting, formal specification, policy-as-code, autonomous-agent governance, industrial automation, and management-control methodologies before any public claim of originality is made.
# Wing Type System

## Overview

The **Wing Type System** defines the primary functional categories used in Multi-Wing architectures.

Its purpose is not to impose an unnecessarily rigid taxonomy, but to provide a stable and interoperable way to describe how distributed intelligence is composed from specialized units.

A Wing Type System is necessary because multi-agent systems often fail in one of two ways:

- every component becomes vaguely general-purpose
- every component becomes ad hoc and incomparable

Multi-Wing avoids both extremes by defining a minimal, extensible type model.

---

## Design Goals

The Wing Type System is designed to support:

- explicit role differentiation
- capability discovery
- structured composition
- coordination predictability
- interoperability across implementations
- conformance testing
- extensibility without semantic collapse

The type system is therefore both descriptive and operational.

---

## What Is a Wing Type

A **Wing Type** is a formal category describing the expected role and behavioral boundary of a Wing.

A Wing Type does not define implementation internals.  
It defines:

- functional purpose
- coordination expectations
- access patterns
- expected inputs and outputs
- trace and accountability implications where relevant

A conforming Multi-Wing implementation should be able to identify the type of each Wing it exposes.

---

## Type Model

Multi-Wing v0.2 uses a layered type model:

1. **Primary Type**
2. **Secondary Traits**
3. **Composition Rules**

### Primary Type
The Primary Type defines the dominant operational role of the Wing.

### Secondary Traits
Secondary Traits refine how the Wing behaves.

Examples include:

- synchronous
- asynchronous
- stateful
- stateless
- trace-emitting
- policy-restricted
- review-gated
- latency-sensitive
- edge-optimized
- human-oversight-required

### Composition Rules
Composition Rules define how Wings may be combined safely into larger structures.

A Wing Type is therefore not only a label.  
It is part of a larger coordination grammar.

---

## Primary Wing Types

Multi-Wing v0.2 recommends the following initial registry:

- `generation`
- `verification`
- `routing`
- `memory`
- `governance`
- `interface`
- `composite`

This set is intentionally compact.  
It is broad enough for real use, but small enough to remain interoperable.

---

## 1. Generation Wing

A **Generation Wing** produces candidate outputs.

Typical functions include:

- drafting
- proposing hypotheses
- synthesizing source material
- transforming inputs into candidate artifacts
- generating structured responses
- producing revisions of existing artifacts

Generation Wings are useful, but they should not automatically be treated as authoritative.

Typical output characteristics:

- provisional
- revisable
- traceable to inputs where possible

### Coordination Implication
Generation Wings expand possibility space.  
They should normally be paired with review-capable or routing-capable structures in non-trivial workflows.

---

## 2. Verification Wing

A **Verification Wing** checks whether an output satisfies relevant constraints.

Typical functions include:

- factual checking
- consistency checking
- evidence alignment
- policy verification
- contradiction detection
- structural validation
- approval or revision request decisions

Verification Wings are responsible for reducing silent error propagation.

They are especially important in architectures where Generation Wings are fast, creative, weakly constrained, or high-volume.

### Coordination Implication
A Verification Wing should be distinguishable from a Generation Wing even if they use similar underlying models.  
Otherwise review becomes nominal rather than operational.

---

## 3. Routing Wing

A **Routing Wing** manages structured flow across the system.

Typical functions include:

- selecting which Wing should act
- sequencing interaction steps
- maintaining task transitions
- triggering rebalance
- triggering escalation
- resolving basic coordination conflicts
- enforcing lifecycle order

This type should not be confused with absolute centralized control.  
Its function is orchestration, not sovereignty.

### Coordination Implication
Routing Wings shape coordination paths.  
They should remain inspectable, especially when they interact with finalization or governance paths.

---

## 4. Memory Wing

A **Memory Wing** manages continuity across interactions.

Typical functions include:

- retrieving past artifacts
- preserving task state
- maintaining reference continuity
- managing shared context objects
- supplying relevant context during coordination
- performing freshness or conflict checks

This type is essential for systems that would otherwise degrade into stateless message passing.

### Coordination Implication
Memory Wings help stabilize continuity, but they should not silently become universal authority over context mutation without explicit policy or review constraints.

---

## 5. Governance Wing

A **Governance Wing** handles accountability-oriented functions.

Typical functions include:

- provenance capture
- policy traceability
- audit logging
- review state preservation
- dispute hooks
- contribution references
- authority trace recording
- integrity-related trace handling

This type becomes increasingly important as systems move from experimentation to deployment.

### Coordination Implication
Governance Wings should normally strengthen inspectability rather than dominate substantive content generation.  
If they materially alter outputs, that authority should be explicit.

---

## 6. Interface Wing

An **Interface Wing** mediates between external systems and the Multi-Wing field.

Typical functions include:

- user-facing interaction
- protocol-facing adaptation
- tool-facing normalization
- transport translation
- request intake
- representation conversion

This type is useful when the architecture must interact with external ecosystems while preserving internal coordination coherence.

### Coordination Implication
Interface Wings sit at the boundary of the system.  
They should convert inputs into structured internal coordination rather than silently bypassing the architecture.

---

## 7. Composite Wing

A **Composite Wing** combines multiple functional roles under a controlled composition rule.

Examples:

- generation + lightweight self-check
- routing + interface mediation
- memory + trace support
- routing + policy gating

Composite Wings are allowed in Multi-Wing, but they must remain structurally legible.  
A Composite Wing should not become a hidden monolith.

### Minimum Declaration Requirement
A Composite Wing should declare:

- component roles
- precedence or ordering rules
- context access implications
- trace implications
- review limitations, if any
- increased authority concentration, if applicable

### Coordination Implication
Composite Wings are useful when they reduce overhead or improve local coordination, but they become risky when they absorb too many critical roles.

---

## Secondary Traits

Wing Types can be refined through traits.

These traits are not full types by themselves.  
They modify operational behavior.

Illustrative traits include:

- **synchronous**
- **asynchronous**
- **stateful**
- **stateless**
- **trace-emitting**
- **review-gated**
- **policy-restricted**
- **latency-sensitive**
- **edge-optimized**
- **human-oversight-required**

Traits allow the type system to stay compact while still supporting deployment realism and operational nuance.

---

## Type Compatibility

Not all Wings should be combined arbitrarily.

A type system is useful only if it can express some compatibility logic.

### Compatible Patterns
Examples of common compatible patterns:

- Generation Wing -> Verification Wing
- Memory Wing -> Generation Wing
- Routing Wing -> Generation Wing
- Routing Wing -> Verification Wing
- Verification Wing -> Revision Path
- Governance Wing -> Finalization Check
- Interface Wing -> Routing Wing

These patterns generally improve coordination clarity.

### Risky Patterns
Examples of risky patterns:

- Generation Wing acting as final authority without meaningful review
- Governance Wing materially rewriting substantive outputs without trace clarity
- Routing Wing holding hidden finalization authority
- Memory Wing dominating both context mutation and closure
- Composite Wings accumulating multiple critical authorities without disclosure

These are not always forbidden, but they should be treated as design risks.

---

## Type Boundaries

A useful Wing Type System must help preserve boundaries, not just categories.

A type declaration should make it possible to understand:

- what this Wing is primarily responsible for
- what it may do
- what it should not silently assume
- what kinds of handoffs it is expected to participate in
- what review or trace expectations apply to it

If a Wing is declared but its operational boundary cannot be explained, the type declaration is weak.

---

## Minimum Type Declaration

A minimal type declaration should be able to answer:

- What does this Wing primarily do?
- What capabilities does it declare?
- What constraints apply to its operation?
- What context can it access?
- What outputs can it emit?
- What accountability hooks apply?

If these questions cannot be answered, the Wing is not sufficiently typed for interoperability.

---

## Type System and Composition

Wing types are not meaningful in isolation.  
They become architecturally useful through composition.

A proper type system should therefore support:

- sequential composition
- parallel composition
- nested composition
- composite role declaration
- review reachability
- bounded authority concentration

This is why the Wing Type System should be read together with:

- `docs/wing-composition-rules.md`
- `docs/kazene-operational-semantics.md`

Type without composition is classification.  
Type with composition becomes coordination structure.

---

## Type System and Trace

Wing types also shape trace expectations.

Examples:

- a Generation Wing should typically emit or preserve source-related trace when producing artifacts
- a Verification Wing should typically emit review-related trace when evaluating artifacts
- a Governance Wing should typically preserve audit or authority trace where such claims are made
- a Routing Wing may preserve assignment or escalation trace in stronger profile implementations

This means the Wing Type System is relevant not only to function, but also to provenance behavior.

---

## Type System and Profiles

Different interoperability profiles may place different expectations on the same Wing type.

For example:

- a `generation` Wing in a `minimal` profile may emit only shallow artifact references
- a `generation` Wing in an `auditable` profile may preserve deeper source continuity
- a `routing` Wing in a `federated` profile may require explicit cross-boundary handoff semantics
- a `governance` Wing in a `signed-trace` profile may expose signature-aware trace structures

Type meaning should remain stable across profiles, but operational obligations may deepen.

---

## Type System and Conformance

The Wing Type System is part of the conformance surface of Multi-Wing.

A conforming implementation should be able to:

- declare Wing types consistently
- expose capabilities in a structured way
- preserve type meaning across interactions
- distinguish core roles from optional traits
- avoid collapsing all Wings into one generic role label

Future versions may define stricter registries and canonical type identifiers.

---

## Extension Policy

Multi-Wing v0.2 encourages a conservative extension strategy.

New types may be added, but extensions should:

- solve a clear coordination need
- remain distinguishable from existing types
- preserve interoperability
- avoid semantic duplication
- document trace and context implications

A type system becomes weaker, not stronger, when every implementation invents nearly identical categories under different names.

---

## Type Smells

The following are warning signs that a Wing Type model is becoming unhealthy:

- every Wing is labeled `composite`
- one role is used as a catch-all for unrelated behavior
- verification is declared but operationally absent
- routing is declared but indistinguishable from final authority
- governance is used as a vague label for any meta-behavior
- traits are used to replace missing primary types
- the system cannot explain why a given Wing has its declared type

These are not always proof of invalidity, but they are strong architectural warnings.

---

## Operational Definition

The operational meaning of the Wing Type System may be stated as follows:

> **A Wing Type is a structured declaration of role, capability boundary, coordination expectation, and accountability implication for a functional unit in a Multi-Wing system.**

---

## Final Note

The purpose of the Wing Type System is not to freeze intelligence into rigid boxes.

Its purpose is to make distributed specialization **explicit enough to coordinate, inspect, and standardize**.

That is what turns a multi-agent pattern into a reusable architecture.

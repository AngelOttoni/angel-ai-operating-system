# ADR-002 — Project Documentation Hierarchy

**Status:** Accepted

**Date:** 2026-08-06

---

# Context

As the Angel AI Operating System evolved, multiple engineering artifacts were introduced to describe different aspects of the system.

The project now contains behavioral specifications, operational specifications, architectural decisions and architecture documents. Without a formally defined documentation hierarchy, the authority and responsibilities of each artifact become ambiguous, increasing the risk of redundancy, inconsistency and architectural drift.

A permanent documentation hierarchy is therefore required to govern how every engineering artifact relates to the others.

---

# Decision

The Angel AI Operating System adopts a hierarchical documentation architecture in which each document category possesses a single well-defined responsibility.

The hierarchy is defined as follows:

```text
Project Charter
        │
        ▼
Architecture Documents
        │
        ▼
Architecture Decision Records (ADRs)
        │
        ▼
Behavior Specifications (ABRS)
        │
        ▼
Operational Specifications (AOS)
        │
        ▼
Operational Protocols
        │
        ▼
Behavioral Patterns
        │
        ▼
Templates
```

Each layer derives from the layers above it and shall not redefine their responsibilities.

---

# Responsibilities

## Project Charter

Defines the purpose, vision, governance and long-term evolution of the Angel AI Operating System.

It establishes why the project exists and how it is organized.

---

## Architecture Documents

Describe the structural organization of the project and its engineering artifacts.

They define architectural models but do not specify behavioral requirements.

---

## Architecture Decision Records (ADRs)

Register permanent architectural decisions.

Every architectural decision that affects the evolution of the project shall be documented through an ADR.

ADRs explain why decisions were made rather than how the system behaves.

---

## Behavior Specifications (ABRS)

The Alice Behavior Requirements Specification defines Alice's behavioral identity.

It is the normative specification governing permanent behavioral requirements.

Behavioral changes shall always be introduced here before appearing elsewhere.

---

## Operational Specifications (AOS)

Operational Specifications derive exclusively from the corresponding Behavior Specification.

They integrate validated behavioral requirements into coherent operational models.

Operational Specifications shall not introduce new behavioral requirements.

---

## Operational Protocols

Protocols define repeatable operational processes for executing specific activities.

Protocols operationalize the behavior defined by the AOS without modifying it.

---

## Behavioral Patterns

Patterns capture reusable solutions for recurring situations.

Patterns are reusable operational knowledge derived from protocols and operational experience.

---

## Templates

Templates define standardized document structures and operational artifacts.

Templates represent the lowest abstraction layer of the documentation hierarchy.

---

# Authority

Authority flows downward through the documentation hierarchy.

Higher layers define the constraints governing lower layers.

Lower layers shall never redefine or silently modify concepts established by higher layers.

Whenever conflicts exist, the document located at the highest applicable level prevails.

---

# Consequences

The documentation hierarchy establishes a clear separation of responsibilities throughout the project.

Architectural decisions become traceable.

Behavioral identity remains centralized within the ABRS.

Operational behavior remains centralized within the AOS.

Operational procedures become independent from behavioral specification.

Future agents developed within the Angel AI Operating System shall adopt the same documentation hierarchy unless superseded by a future architectural decision.

---

# Related Decisions

- ADR-001 — ABRS is the Normative Specification
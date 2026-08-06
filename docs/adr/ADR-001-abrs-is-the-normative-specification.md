<!--
Architecture Decision Records
-->

# ADR-001

## Title
ABRS is the Normative Specification

### Status
Accepted

### Context

The Angel AI Operating System contains multiple engineering artifacts,
including the ABRS and the AOS.

A decision was required regarding which artifact defines the canonical
behavior of Alice.

**Decision**

The ABRS is the normative specification.

The AOS is a derived operational specification.

Whenever a conflict exists, the ABRS prevails.

**Consequences**

• Behavioral changes must be introduced in the ABRS.
• The AOS may reorganize and integrate requirements but shall not create
  new behavioral requirements.
• Traceability between both documents becomes mandatory.
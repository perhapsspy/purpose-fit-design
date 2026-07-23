---
name: purpose-fit-design
description: Reopen early design or implementation-planning direction from user/domain purpose, explicit constraints, current evidence, and verifiable success before existing code, precedent, fallback/default logic, or a first solution closes the design space. Use when those pressures, rejected constraints, or meaning-affecting fallback could steer design. Skip mechanical edits, read-only owner discovery, clear specialist cases, and coding after direction is settled.
---

# Purpose-Fit Design

## Job

Before planning or coding starts, express the user/domain purpose and smallest observable success without inheriting the current implementation shape. Start from the responsibilities and relationships required by that success, explicit constraints, and confirmed owner boundaries. Treat existing implementation, copied behavior, fallback/default logic, and future possibilities as evidence to evaluate, not as the default design shape.

End with a provisional direction, the smallest useful probe, or one specialist question that genuinely blocks the choice. Explore and propose broader possibilities freely, but do not treat discovery alone as authority to expand implementation scope.

Do not prove source ownership, assign semantic owners, or shape code here when a specialist trigger is already clear.

## Orientation

Answer only what affects the decision. For small tasks, one compact paragraph is enough.

1. **Ground:** state the user/domain outcome, smallest observable success, explicit corrections or rejected concepts, and the current evidence or unknowns that affect the choice.
2. **Open:** identify whether existing structure, precedent, fallback/default logic, shortcut pressure, or an abstract security/consistency claim is taking over the direction. Only for a material choice, find one credible contrast or the smallest probe that could distinguish the directions.
3. **Choose:** state the provisional direction and evidence that would change it, name the smallest useful probe, or hand off one concrete specialist question that blocks comparing the candidates.

If purpose, constraints, evidence status, or success condition are unknown and affect the design, investigate or ask one focused question. Do not fill the gap with the current implementation shape.

When the role of current implementation or precedent matters, classify it as `source owner`, `derived caller`, `legacy/compatibility`, `evidence candidate`, or `unknown`.

Do not create alternatives merely to perform a process. A material choice is one that would add or change meaningful responsibility, persistent state, policy, dependency, lifecycle, public contract, compatibility, or hard-to-reverse coupling.

Treat explicit user corrections as binding direction and scope constraints. Determine their reach from the correction and surrounding request: neither widen a local correction into a redesign nor narrow a broad correction into a local patch. Preserve unaffected purpose, constraints, and known owner boundaries. Do not reintroduce a rejected field, status, UI pattern, schema, timeout, policy, or fallback under another layer name unless the user asks to revisit it.

Treat lower-layer fallback as a potential design decision when it can affect command meaning, visible state, retries, audit, persistence, tests, policy, or another caller. If it recreates a rejected constraint, do not introduce it. If unresolved meaning ownership would change the current direction or prevent candidate comparison, hand off that concrete question to a semantic-boundary workflow.

For fallback chains that compute domain/status identity in route, UI, adapter, realtime, or presentation code, do not treat the problem as scope control only. Use source-owner or semantic-boundary discovery before planning edits when the unresolved ownership affects current behavior or the design choice; an unnamed owner by itself does not require a specialist chain.

A transport watchdog or infrastructure guard may proceed without semantic-boundary work when it is owned by the transport/infra layer, limited to liveness or resource protection, introduces no domain field/status/policy/default, changes no accepted user-visible state, and cannot become business meaning for callers.

Urgency is not evidence of fit. When the user asks for a shortcut, offer the smallest slice that preserves purpose, constraints, and owner boundaries now. Do not present "copy now, clean later" as a design strategy. A temporary implementation needs a credible reversal story; add an adapter, wrapper, or rollback boundary only when current coupling would otherwise make reversal or containment materially difficult.

## Specialist Routing

Skip this skill and use a specialist workflow directly when its trigger is already clear. Otherwise, after this check:

- Use source-owner discovery when the source of truth is unproven.
- Use semantic-boundary design when one meaning can drift across layers.
- Use structure-focused exploration after direction is settled when relevant behavior or decision ownership is hard to trace, effects obscure verification, boundaries are multiplying, or a proposed structure may displace complexity.
- Use interactive-state flow analysis when user intent, presentation, async work, or freshness can mix.

Do not start a specialist chain merely because an owner is unnamed or a broad smell is present. Hand off only when the unresolved specialist question can change current meaning or direction, or blocks comparing the viable candidates.

## Red Flags

- "This component already exists, so reuse it" without checking fit to the current purpose.
- "Security/consistency suggests adding a schema/catalog/timeout" without user goal or owner evidence.
- Reintroducing a rejected field, status, UI pattern, schema, timeout, policy, or fallback as a lower-level implementation detail.
- Accepting "copy now, clean later" when the copied surface owns another domain's state, layout, policy, or lifecycle.
- UI, route, adapter, or realtime code deciding domain meaning through `x || y || z` fallback chains.
- Tests proving helper internals while caller-boundary behavior remains unprotected.
- A design explanation that mostly describes why the current implementation is acceptable.
- Moving directly to edits after the user asks to rethink design, ownership, purpose, or fit.

## Final Check

Before implementation or final recommendation, confirm:

- The purpose is not merely "make the current implementation work."
- The selected direction fits the user/domain purpose and observable success condition.
- Explicit user corrections or rejected concepts were not reintroduced.
- The reach of each correction matches the request; unaffected purpose, constraints, and known owner boundaries remain intact.
- Urgency did not override constraints, owner boundaries, a credible reversal story, or verification.
- Existing code has been classified by evidence status, not convenience.
- Any semantic decision has one owner or a named unknown.
- Process weight matches task size.

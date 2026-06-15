---
name: academic-writing-write
description: Use when drafting, rewriting, revising, or polishing academic and technical prose after the intended claim is known. Trigger for requests to make paragraphs clearer, more academic, more coherent, less list-like, less implementation-specific, more claim-driven, or better connected across sentences while preserving the existing endpoint, evidence, scope, and causal strength.
---

# Academic Writing Write

Use this skill to write or revise prose while preserving the planned argument.

A rewrite is valid only if it improves clarity without changing the endpoint, argument axis, evidence, scope, or causal strength unless the user explicitly asks for an argument change.

## Revision Invariants

Before rewriting argumentative prose, identify what must survive:

```text
paragraph endpoint
argument axis
scientific consequence
cause layers
evidence type
baseline or reference condition
metric
scope
causal strength
terminology for the same concept
```

Reject rewrites that sound better but change the claim structure.

## Prose Rules

- Start with the claim or role of the unit.
- Use old-to-new flow when needed: known context -> new claim or emphasis.
- Move shallow-to-deep: orientation -> mechanism -> evidence -> consequence -> scope.
- Keep the causal chain alive until the paragraph endpoint is reached.
- Save downstream method advantages, convenience claims, or implementation details for the correct paragraph.
- Use domain-level wording, not repository or local workflow surfaces.
- Keep implementation details only when they affect reproducibility or interpretation.
- State positive requirements: `X requires Y`, `X enables Y`, `X constrains Y`, `X supports Y under Z`.
- Use weak verbs only when the evidence is weak: `help`, `improve`, `serve as`, `allow`.
- Control lists. Keep lists only when distinctions matter scientifically, experimentally, theoretically, or methodologically.
- Split train-car sentences that chain several operations with commas and `and`.

## Dangerous Endpoint Conversions

Do not convert:

```text
validity / comparability -> convenience
objectivity / consistency -> speed
reproducibility -> ease of use
scientific limitation -> implementation complaint
manual decision dependence -> workflow burden only
```

## Examples

Bad:

> Figure 3 shows ray-tracing outputs for three indoor layouts.

Better:

> Indoor layout changes systematically alter the predicted coverage pattern.

Bad:

> An RT-based wireless DT cannot start from the solver alone.

Better:

> An RT-based wireless DT first requires a radio-ready scene that represents the physical site as simulation input.

Bad:

> Results become difficult to reproduce, compare, and extend.

Better:

> Results become difficult to reproduce as a research practice.

## Semantic-Diff Guard

After drafting, check:

```text
Original endpoint:
Revised endpoint:
Same endpoint?

Original argument axis:
Revised argument axis:
Same axis?

Lost cause layer:
Added unsupported claim:
Changed scope:
Changed causal strength:
```

## Response Contract

For prose revision:

```text
Intended endpoint:
Revision strategy:
Revised text:
Preservation check:
```

For small copy edits, return only the revised text when the endpoint is obvious and unchanged.

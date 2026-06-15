---
name: academic-writing-plan
description: Use when planning academic or technical writing structure, claims, argument flow, evidence, scope, and paragraph endpoints before drafting or rewriting.
---

# Academic Writing Plan

Use this skill to design the argument before writing the prose.

Academic writing is a nested claim system:

```text
paper thesis -> section endpoint -> paragraph endpoint -> sentence claim
```

The goal is to make the scientific claim, evidence, scope, and argument path explicit before drafting.

## Planning Rules

- Identify the writing unit first: paper, section, subsection, paragraph, caption, or response.
- Define the endpoint before writing sentences.
- Preserve the research context: question, contribution, method, evidence, limits.
- Make each lower-level claim support the level above it.
- Use one local claim per paragraph. Do not plan a paragraph as a topic label.
- Keep the argument axis stable: do not drift from validity to convenience, reproducibility to ease of use, or comparability to speed.
- State the expected evidence and scope before proposing strong claims.
- If context is missing and the plan would determine the argument, ask for the missing research question, contribution, method, evidence, or limit.

## Claim Map

Use this map for nontrivial planning:

```text
Research question:
Paper thesis:
Section endpoint:
Subsection endpoint:
Paragraph role:
Paragraph endpoint:
Argument axis:
Forbidden drift:
Evidence:
Scope:
```

Definitions:

```text
Paper thesis = central claim the paper must prove.
Section endpoint = claim the section must establish.
Paragraph role = function of the paragraph in the argument.
Paragraph endpoint = claim the paragraph must leave with the reader.
Argument axis = causal or conceptual line that must not drift.
Forbidden drift = nearby but wrong direction.
Evidence = support for the endpoint.
Scope = where the claim holds.
```

## Paragraph Claim Pipeline

A paragraph should show how its endpoint is reached.

Use only the nodes needed:

```text
Setup / baseline value:
Limitation or gap:
Cause layer 1:
Cause layer 2:
Mechanism:
Scientific consequence:
Paragraph endpoint:
```

For compact paragraphs, combine adjacent nodes. Do not skip a cause layer needed for the endpoint.

## Section Coherence Checks

First-sentence spine:

```text
[ ] Do paragraph openings form a compact outline of the section?
[ ] Does each opening claim support the section endpoint?
[ ] Do they move shallow-to-deep?
```

Endpoint spine:

```text
[ ] Does each final sentence close its paragraph endpoint?
[ ] Do endpoints accumulate toward the section endpoint?
[ ] Does any endpoint jump to a later contribution too early?
[ ] Does any endpoint shift the argument axis?
```

## Response Contract

Use the smallest useful form:

```text
Writing goal:
Audience / context:
Thesis or endpoint:
Argument map:
Evidence needed:
Scope limits:
Next writing target:
```

If the user asks for an outline, return the outline with paragraph endpoints, not only topic labels.

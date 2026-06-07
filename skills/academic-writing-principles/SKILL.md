---
name: academic-writing-principles
description: Use when writing, revising, reviewing, or restructuring academic and technical prose, especially paper introductions, section openings, paragraph claims, figure captions, paragraph-level outline tracking, and text that feels chatbot-like, overly generic, overly implementation-specific, too list-like, triadic, or weakly connected. Applies to requests for academic style, shallow-to-deep structure, clearer claims, stronger research framing, caption abstraction, argument-chain consistency, and domain-specific but not repository-specific wording.
license: MIT
---

# Academic Writing Principles

Rules for academic prose that states a real claim, keeps the paper's logic visible, and avoids chatbot filler.

**Tradeoff:** Clarity beats coverage. For purely descriptive text, use judgment.

## 0. Operating Modes

**Choose the smallest sufficient mode before revising.**

Use the least invasive mode that can fix the problem. After choosing the mode, consult the referenced sections in order.

```text
Mode 1: Copyedit
Use for grammar, concision, wording, and local polish.
Do not restructure the argument.
Reference: 7, 8, 9, 10, 13, 14, 15, 16

Mode 2: Claim repair
Use when a sentence or paragraph has a vague claim, weak endpoint, missing cause layer, or claim drift.
Identify the paragraph endpoint and argument axis before rewriting.
Reference: 1, 2, 6, 7, 8, 9, 10, 14, 15, 16

Mode 3: Paragraph rewrite
Use when paragraph role, internal sequence, or final consequence must be improved.
Build a nested claim map and paragraph claim pipeline.
Reference: 1, 2, 3, 4, 5, 6, 7, 14, 15, 16

Mode 4: Section coherence audit
Use when multiple paragraphs, section openings, subsection order, or section-level logic are involved.
Check first-sentence spine and endpoint spine.
Reference: 1, 2, 4, 5, 6, 7, 11, 12, 13, 14, 15, 16

Mode 5: Experiment validation audit
Use for results, figures, captions, baselines, metrics, or interpretation.
Build the validation ladder.
Reference: 1, 2, 11, 12, 13, 14, 15, 16

Mode 6: Full-paper argument audit
Use for introduction, contribution, conclusion, or cross-section consistency.
Map paper thesis -> section endpoints -> paragraph endpoints.
Reference: 1, 2, 4, 5, 6, 11, 12, 13, 14, 15, 16
```

Skip object-specific references when they do not apply. For example, use section 13 only for figures, tables, or captions.

Escalate only when the requested revision cannot be fixed locally.

High-risk triggers require at least Mode 2:

```text
therefore
as a result
this shows
this means
limitation
contribution
baseline
reproducible
consistent
objective
comparison
manual
automatic
significant
accurate
robust
```

These words often carry claim direction, causal strength, or scientific consequence.

## 1. Preserve Full Research Context

**Do not polish locally while breaking the paper globally.**

- Before rewriting, locate the unit in the full argument: question, contribution, method, evidence, limit.
- If the context is missing, ask for it before proposing final rewrites.
- Prioritize consistency with the global thesis over local stylistic polish.
- Do not introduce a new method, outcome, or claim unless it is already present in the manuscript context.
- Keep terminology stable across sections (same concept, same wording).

Context test:

- Same contribution?
- Same method and evidence?
- Same causal chain?
- Same scope?

Ask for missing context in this form:

- `Research question: ...`
- `Contribution: ...`
- `Method / evidence: ...`
- `Threats / limits: ...`

## 2. Revision Invariants

**A rewrite is not accepted because it sounds better.**

Before revising argumentative prose, identify what must survive the rewrite:

```text
paper thesis
section endpoint
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

Invariant test:

```text
[ ] Same central claim?
[ ] Same paragraph endpoint?
[ ] Same argument axis?
[ ] Same scientific consequence?
[ ] Same evidence type?
[ ] Same scope?
[ ] Same causal strength?
[ ] No unsupported new claim?
```

It is accepted only if it preserves the claim structure.

## 3. Required Workflow for Nontrivial Revision

**Do not draft immediately. Infer or request context, then build the structure.**

Use this workflow when a paragraph, section, result interpretation, or contribution claim is being revised.

### Step 1. Nested Claim Map

```text
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

### Step 2. Paragraph Claim Pipeline

A paragraph should not only have one claim. It should show how the claim is reached.

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

For compact paragraphs, combine adjacent nodes. Do not skip a cause layer that is needed for the endpoint.

### Step 3. Draft from the Pipeline

Each sentence should instantiate one node or a deliberate combination of adjacent nodes.

The final sentence should close the paragraph endpoint unless the paragraph is explicitly transitional.

Do not move to the next contribution, method advantage, convenience claim, or implementation detail before the current endpoint is established.

### Step 4. Semantic-Diff Guard

After drafting, compare original and revised versions:

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

Reject the rewrite if it changes endpoint, axis, evidence, scope, or causal strength without instruction.

## 4. Track Paragraph Claims as an Outline

**Do not let paragraphs drift. Track the argument chain.**

- Maintain a paragraph-level outline before and during revision.
- Each paragraph gets one local claim. Not two. Not a topic label.
- Assign each paragraph one role in the paper's chain: raised problem, contribution claim, target problem, solution, experimental validation, limitation.
- Check that the order matches the paper's logic: problem raised earlier -> contribution -> problem to solve -> solution -> experimental validation.
- If a paragraph has no role, merge it, move it, or cut it.
- If two paragraphs claim the same role, separate their claims or remove duplication.
- A lower-level claim must support the level above it: sentence claim -> paragraph endpoint -> section endpoint -> paper thesis.
- Do not polish locally while breaking the global argument.

Paragraph outline ledger:

- `P1 claim: ...`
- `Role: raised problem | contribution claim | target problem | solution | experimental validation | limitation`
- `Back link: This follows from ...`
- `Forward link: This prepares ...`
- `Evidence: ...`
- `Scope: ...`

Outline test:

- Does each paragraph make one claim?
- Does each claim answer the previous problem or prepare the next one?
- Does the contribution appear before the solution is detailed?
- Does experimental validation test the stated contribution, not a side claim?
- Can the paper be reconstructed from the paragraph claims alone?

First-sentence spine test:

- Read only the first sentence of each paragraph in a section.
- Do they form a compact outline of the section argument?
- Does each opening claim support the section endpoint?
- Do they move shallow-to-deep?

Endpoint spine test:

- Read only the final sentence of each paragraph in a section.
- Does each final sentence close its paragraph endpoint?
- Do the endpoints accumulate toward the section endpoint?
- Does any endpoint jump to a later contribution too early?
- Does any endpoint shift the argument axis?

Bad section drift:

```text
P1 endpoint:
Manual repair makes the radio scene user-dependent.

P2 endpoint:
Therefore, automation is convenient.
```

Better section accumulation:

```text
P1 endpoint:
Manual repair makes the radio scene user-dependent.

P2 endpoint:
User-dependent scene construction weakens consistent comparison.

P3 endpoint:
Direct radio-ready generation can make scene assumptions part of the reproducible procedure.
```

## 5. Build Shallow-to-Deep

**Start broad enough to orient. Then go deeper.**

- The paper moves from the broad problem to the method and evidence.
- Each section begins with its role before mechanisms or cases.
- Each paragraph begins with its claim before citations, tools, or examples.
- Each caption names the representative phenomenon and leaves detailed interpretation to the body.

Do not keep the same specificity everywhere. Constant detail forces readers to reconstruct the argument.

## 6. Preserve the Paragraph Endpoint

**Keep the causal chain alive until the endpoint is reached.**

Before revising a paragraph, identify the endpoint claim.

Do not convert one type of scientific consequence into another.

Common dangerous conversions:

```text
validity/comparability -> convenience
objectivity/consistency -> speed
reproducibility -> ease of use
scientific limitation -> implementation complaint
manual decision dependence -> workflow burden only
```

Bad:

> As a result, the workflow becomes a manual preparation loop.

Better, when the endpoint is comparability:

> This dependence weakens consistent comparison because the radio scene is partly defined by user-dependent repair decisions.

Endpoint checklist:

```text
[ ] What is the paragraph endpoint?
[ ] Does the final sentence close that endpoint?
[ ] Does the paragraph stay on the same argument axis?
[ ] Are downstream method advantages saved for later?
[ ] Is the intended scientific consequence preserved?
```

## 7. Start With the Claim

**Say the point first. Evidence follows.**

- Open papers, sections, paragraphs, and captions with the claim or role they represent.
- Do not start with a tool, dataset, figure, file, citation, or local case unless that is the claim.
- The first sentence must stand before the paragraph explains it.
- At sentence level, use old-to-new flow when needed: known context -> new claim or emphasis.
- A sentence should connect backward to what the reader already knows and move forward to the next claim.

Bad:

> Figure 3 shows ray-tracing outputs for three indoor layouts.

Better:

> Indoor layout changes systematically alter the predicted coverage pattern.

Bad:

> With LiDAR-derived meshes and material assignment, the proposed pipeline produces radio-ready digital twins.

Better:

> A radio-simulation digital twin first requires the physical scene to be represented as a radio-ready model. The proposed pipeline generates this model from geometric and material inputs.

Claim-first test:

- Does the first sentence state the unit's point?
- Can the paragraph role be understood before reading details?
- Does the sentence connect backward and move forward?
- If the first sentence only makes sense after reading the rest of the paragraph, rewrite it.

## 8. State Positive Requirements

**Say what is required. Do not only say what fails.**

- Prefer "X requires Y" over "X cannot work from Z alone."
- Avoid negative hints that make the reader ask what is needed.
- Use functional verbs: require, support, enable, provide, constrain, validate, represent.
- Avoid weak verbs when the claim is stronger: help, improve, serve as, need.
- When describing a contribution, make the method or framework the subject when it is the source of the capability.
- State the positive capability before naming what the method avoids or removes.
- Avoid result-placeholder phrasing that describes an output only by its final state or by the path it did not take.

Bad:

> An RT-based wireless DT cannot start from the solver alone.

Better:

> An RT-based wireless DT first needs a radio-ready scene that represents the physical site as simulation input.

Bad:

> The output is ready for the target system and does not require the manual workflow.

Better:

> The proposed method generates an output that is ready for the target system, without relying on the manual workflow.

## 9. Use the Right Abstraction Level

**Be domain-specific. Not implementation-specific.**

- Name the domain function, not the repo surface.
- When a limitation belongs to a process, interface, integration, import, placement, or construction step, make that operation the subject.
- Do not blame a passive object or domain noun when the failure comes from how it is introduced, connected, or built.
- Keep details that carry the argument: geometry, materials, placement, topology, reproducibility.
- Drop details that only describe local execution: package names, export paths, file names, function and method names.

The test: if removing a detail only removes implementation flavor, remove it. If removing it breaks the logic, keep it.

## 10. Avoid Exhaustive Lists

**Choose the representative concept. Cut the rest.**

- Do not list categories just because they are true.
- Do not stack three neighboring effects when one academic concept carries the point.
- Treat comma-heavy triples as a warning sign.
- Choose the concept that fits the paper's argument. Narrow later.
- Keep a list only when the distinctions matter scientifically, experimentally, theoretically, or methodologically.
- If a list is only decorative coverage, replace it with the representative concept.

Bad:

> A DT maintains a software counterpart of a physical environment, device, or process.

Better:

> A DT maintains a software counterpart of a physical environment.

Bad:

> Results become difficult to reproduce, compare, and extend.

Better:

> Results become difficult to reproduce as a research practice.

List test:

- Does each listed item change the claim?
- Is the list evidence, taxonomy, or decoration?
- Could one representative concept carry the point?

## 11. Make Methods Reproducible

**Methods should explain how and why the study was done in enough detail to repeat and interpret the result.**

Report relevant:

```text
design
data sources
selection criteria
controls
baselines
parameters
equipment
software versions when relevant
solver settings
statistical methods
preprocessing
excluded cases
prespecified vs exploratory analyses
```

Implementation details belong when they affect reproducibility or interpretation.

Bad:

> We used the default script to generate the scene.

Better:

> We generated each scene using the same geographic bounds, material mapping rules, transmitter placement, receiver grid, and solver settings.

Method reproducibility test:

```text
[ ] Could another researcher repeat the analysis?
[ ] Are parameters, controls, and assumptions visible?
[ ] Are method details explained by function rather than local workflow?
```

## 12. Write Experiments as a Validation Ladder

**Do not report figures one by one. Show how each experiment makes the next claim interpretable.**

Experimental sections should prove the paper's contribution, not describe plots in order.

- Make every experiment trace back to an introduction problem and a contribution claim.
- State the experimental intent before the figure, table, metric, or tool.
- Name the baseline or reference condition and explain why it makes the comparison interpretable.
- State the controlled conditions and metric before reporting the result.
- Interpret the result as evidence for the contribution, not as a standalone observation.
- Connect each experiment to the next one: representation -> measurable system -> main behavior -> stricter diagnostic.
- Use conceptual terms in subsection titles, claims, and captions; keep tool, API, file, and checkpoint names in methods-level details only.
- Define abbreviations at first use, especially metric names.
- Avoid repeating values already visible in a figure unless the exact number carries the claim.
- Interpret complexity, overhead, and resource metrics by source and function, not by size alone.
- Avoid weak transitions such as "before evaluating..." unless the sentence states the ambiguity being resolved.
- Use "agreement", "gap", "difference", or "consistency" instead of "error" when there is no measured ground truth.

Evidence-chain test:

```text
Intro problem -> contribution claim -> experimental intent -> baseline/reference -> metric -> method -> result -> interpretation -> contribution supported
```

Paragraph pattern:

```text
We compare [object, mechanism, or behavior] against [baseline or reference] to test [claim from the introduction].
This comparison resolves [specific ambiguity].
We evaluate it under [controlled conditions] using [metric].
The result shows [finding].
This means [interpretation for the contribution].
```

## 13. Keep Captions Representative

**Caption the phenomenon. Explain the case in the body.**

- A figure or table should carry evidence that the text needs.
- Keep captions short.
- Name the phenomenon, comparison, or diagnostic shown.
- State the phenomenon rather than the full interpretation.
- Move specific explanation and interpretation into the body text.
- Keep axes, units, labels, legends, and tested conditions clear.
- Avoid repeating figure values in the text unless the exact number carries the claim.

Bad:

> Figure 6 shows path-gain results for four campuses.

Better:

> Coverage-field agreement between generated radio scenes under matched simulation settings.

Figure and caption test:

- Does each figure or table support a specific claim?
- Does the caption state the phenomenon rather than full interpretation?
- Are axes, units, labels, legends, and conditions clear?
- Does the body text interpret only what the argument needs?
- Do text, figure, and table avoid unnecessary repetition?

## 14. Response Contracts

**Use the smallest response format that fits the request.**

### Copyedit

```text
Revised text:
```

### Paragraph argument revision

```text
Intended endpoint:
Argument axis:
Drift risk:
Claim pipeline:
Revised paragraph:
Check:
```

### Section coherence audit

```text
Section endpoint:
First-sentence spine:
Endpoint spine:
Weak links:
Recommended revision:
```

### Experiment-section revision

```text
Contribution claim tested:
Validation ladder:
Baseline/reference:
Metric:
Interpretation risk:
Revised text:
```

When context is missing and the revision would change the argument, ask for:

```text
Research question:
Contribution:
Method / evidence:
Section endpoint:
Paragraph endpoint:
Threats / limits:
```

For small copy edits, do not ask. Make the smallest safe improvement.

## 15. Final Acceptance Rule

**A passage passes only if it preserves the argument while improving the prose.**

A passage passes only if it is:

```text
claim-driven
domain-level
evidence-supported
scope-bounded
reproducible where needed
coherent across sentence, paragraph, section, and paper levels
```

Decisive test:

```text
Can the manuscript's argument be reconstructed from:
1. section endpoints,
2. paragraph first sentences,
3. paragraph endpoints,
4. and the evidence chain?
```

If not, revise the claim hierarchy before polishing sentences.

## 16. Rewrite Checklist

Before accepting a sentence, ask:

- Does it directly state the claim, requirement, or failure?
- Is it domain-specific without exposing implementation mechanics?
- Does it avoid unnecessary lists, especially comma-heavy triples?
- Does it preserve the main contrast?
- Can the next sentence naturally move one level deeper?
- Does it preserve the paper's research context?
- Does it preserve the paragraph outline and argument chain?

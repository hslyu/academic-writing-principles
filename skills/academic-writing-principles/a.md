---
name: academic-writing-principles
description: Use when writing, revising, reviewing, or restructuring academic and technical prose. Applies especially to introductions, section openings, paragraph claims, figure captions, experiment sections, claim drift, weak argument flow, overly generic prose, implementation-specific wording, list-heavy writing, and chatbot-like rewrites that sound fluent but change the scientific point.
license: MIT
---

# Academic Writing Principles

Academic prose is a nested claim system.

A sentence supports a paragraph endpoint.  
A paragraph endpoint supports a section endpoint.  
A section endpoint supports the paper thesis.

A rewrite is valid only if it makes the prose clearer while preserving the endpoint, argument axis, evidence, scope, and causal strength unless the user explicitly asks to change them.

**Core rule:**  
Claim first. Evidence traceable. Scope bounded. Method reproducible. Logic coherent across sentence, paragraph, section, and paper levels.

---

## 0. Operating Modes

Before applying the skill, choose the smallest sufficient mode.

```text
Mode 1: Copyedit
Use for grammar, concision, wording, and local polish.
Do not restructure the argument.

Mode 2: Claim repair
Use when a sentence or paragraph has a vague claim, weak endpoint, missing cause layer, or claim drift.
Identify the paragraph endpoint and argument axis before rewriting.

Mode 3: Paragraph rewrite
Use when paragraph role, internal sequence, or final consequence must be improved.
Build a nested claim map and paragraph claim pipeline.

Mode 4: Section coherence audit
Use when multiple paragraphs, section openings, subsection order, or section-level logic are involved.
Check first-sentence spine and endpoint spine.

Mode 5: Experiment validation audit
Use for results, figures, captions, baselines, metrics, or interpretation.
Build the validation ladder.

Mode 6: Full-paper argument audit
Use for introduction, contribution, conclusion, or cross-section consistency.
Map paper thesis -> section endpoints -> paragraph endpoints.
```

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

---

## 1. No-Invention Rule

Do not introduce a new method, dataset, metric, baseline, result, limitation, contribution, or claim unless it is present in the manuscript context or explicitly requested by the user.

Allowed:

```text
clarify an existing claim
make an implicit causal link explicit
separate collapsed cause layers
tighten scope
replace vague wording with precise domain wording
improve order and emphasis
```

Not allowed:

```text
add a new experimental result
change the scientific consequence
change the argument axis
replace comparability with convenience
replace consistency with speed
replace reproducibility with ease of use
claim accuracy without ground truth
claim causality without a causal design
```

Bad:

> This shows that the proposed method accurately reproduces the real wireless environment.

Better, when no measurement ground truth exists:

> This supports agreement between the two generated scene pipelines under the tested solver configuration.

---

## 2. Revision Invariants

Before revising argumentative prose, identify what must survive the rewrite.

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

A rewrite is not accepted because it sounds better.  
It is accepted only if it preserves the claim structure.

---

## 3. Required Workflow for Nontrivial Revision

Do not draft immediately.

First infer or request the argument context. Then build the structure. Then write.

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

Example:

```text
Paper thesis:
Radio-ready scene generation can be made reproducible without manual visual-authoring repair.

Section endpoint:
The key distinction is whether radio readiness is repaired after visual authoring or generated directly.

Paragraph role:
Limitation of the existing Blender-centered pipeline.

Paragraph endpoint:
Manual geometry and material repair make the radio-simulation input user-dependent, weakening objective and consistent comparison.

Argument axis:
manual repair decisions -> user-dependent radio-scene definition -> weak comparability

Forbidden drift:
manual workflow -> inconvenient -> automation benefit
```

### Step 2. Paragraph Claim Pipeline

A paragraph should not only have one claim.  
It should show how the claim is reached.

Use only the nodes needed.

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

Example pipeline:

```text
Setup:
The Blender pipeline is useful because it gives an inspectable city model.

Limitation:
The same visual scene is not guaranteed to produce the same radio-simulation input.

Cause layer 1:
The software/import/export environment must be preserved.

Cause layer 2:
The same manual geometry-grouping and radio-material repair decisions must be repeated.

Scientific consequence:
Different users or regenerations can produce different RT inputs.

Endpoint:
This weakens objective and consistent comparison across wireless-DT studies.
```

### Step 3. Draft from the Pipeline

Each sentence should instantiate one node or a deliberate combination of adjacent nodes.

The final sentence should close the paragraph endpoint unless the paragraph is explicitly transitional.

Do not move to the next contribution, method advantage, convenience claim, or implementation detail before the current endpoint is established.

### Step 4. Semantic-Diff Guard

After drafting, compare original and revised versions.

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

---

## 4. Claim-First, Old-to-New

Open papers, sections, paragraphs, and captions with the claim or role they represent.

Do not start with a tool, dataset, figure, file, citation, or local case unless that is the claim.

The first sentence must stand before the rest explains it.

At sentence level, use old-to-new flow when needed:

```text
known context -> new claim or emphasis
```

Bad:

> Figure 3 shows ray-tracing outputs for three indoor layouts.

Better:

> Indoor layout changes systematically alter the predicted coverage pattern.

Bad:

> With LiDAR-derived meshes and material assignment, the proposed pipeline produces radio-ready digital twins.

Better:

> A radio-simulation digital twin first requires the physical scene to be represented as a radio-ready model. The proposed pipeline generates this model from geometric and material inputs.

Test:

```text
[ ] Does the first sentence state the unit's point?
[ ] Can the paragraph role be understood before reading details?
[ ] Does the sentence connect backward and move forward?
```

---

## 5. Preserve Nested Claim Coherence

A lower-level claim must support the level above it.

```text
sentence claim -> paragraph endpoint -> section endpoint -> paper thesis
```

Do not polish locally while breaking the global argument.

### First-Sentence Spine

Read only the first sentence of each paragraph in a section.

```text
[ ] Do they form a compact outline of the section argument?
[ ] Does each opening claim support the section endpoint?
[ ] Do they move shallow-to-deep?
```

### Endpoint Spine

Read only the final sentence of each paragraph in a section.

```text
[ ] Does each final sentence close its paragraph endpoint?
[ ] Do the endpoints accumulate toward the section endpoint?
[ ] Does any endpoint jump to a later contribution too early?
[ ] Does any endpoint shift the argument axis?
```

A section passes only when both spines are coherent.

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

---

## 6. Preserve the Paragraph Endpoint

Before revising a paragraph, identify the endpoint claim.

Keep the causal chain alive until the endpoint is reached.

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

Checklist:

```text
[ ] What is the paragraph endpoint?
[ ] Does the final sentence close that endpoint?
[ ] Does the paragraph stay on the same argument axis?
[ ] Are downstream method advantages saved for later?
[ ] Is the intended scientific consequence preserved?
```

---

## 7. Use the Right Abstraction Level

Be domain-specific, not implementation-specific.

Name the domain function, not the repository surface.

Keep details that affect:

```text
claim
method
validity
reproducibility
baseline
metric
scope
interpretation
```

Remove details that only describe local execution:

```text
file names
export paths
helper functions
temporary scripts
package internals
local directory structure
```

Exception: implementation details belong when they affect reproducibility or interpretation.

Bad:

> The script converts `scene.obj` using `convert_mesh.py`.

Better:

> The pipeline converts geometric scene models into radio-simulation-ready inputs.

Test:

```text
[ ] Would the detail matter to a reviewer?
[ ] Does removing it only remove implementation flavor?
[ ] Does keeping it clarify the scientific logic?
```

---

## 8. State Positive Requirements

Say what is required, enabled, constrained, supported, represented, or validated.

Prefer:

```text
X requires Y.
X enables Y.
X constrains Y.
X supports Y under Z.
X validates Y under Z.
```

Avoid only saying what fails.

Use functional verbs:

```text
require
support
enable
provide
constrain
validate
represent
determine
preserve
separate
quantify
bound
```

Use weak verbs only when the claim is genuinely weak:

```text
help
improve
serve as
need
allow
```

Bad:

> An RT-based wireless DT cannot start from the solver alone.

Better:

> An RT-based wireless DT first requires a radio-ready scene that represents the physical site as simulation input.

Test:

```text
[ ] Does the sentence state the positive condition?
[ ] Is the capability stated before the avoided limitation?
[ ] Is the verb strength appropriate to the evidence?
```

---

## 9. Control Lists

Do not list categories just because they are true.

Choose the representative concept that carries the argument.

Treat comma-heavy triples as a warning sign.

Lists are allowed only when the distinctions matter scientifically, experimentally, theoretically, or methodologically.

Bad:

> A DT maintains a software counterpart of a physical environment, device, or process.

Better:

> A DT maintains a software counterpart of a physical environment.

Bad:

> Results become difficult to reproduce, compare, and extend.

Better:

> Results become difficult to reproduce as a research practice.

Test:

```text
[ ] Does each listed item change the claim?
[ ] Is the list evidence, taxonomy, or decoration?
[ ] Could one representative concept carry the point?
```

---

## 10. Build Shallow-to-Deep

Move from orientation to claim, then to mechanism, evidence, consequence, and scope.

Paper pattern:

```text
broad problem
-> specific gap
-> contribution
-> method principle
-> evidence
-> interpretation
-> limitations
```

Section pattern:

```text
section role
-> main distinction
-> mechanism or evidence
-> endpoint
```

Paragraph pattern:

```text
claim
-> cause or mechanism
-> evidence
-> consequence
-> endpoint
```

Test:

```text
[ ] Does each unit begin broad enough to orient?
[ ] Does each sentence move one level deeper?
[ ] Does the unit avoid staying at constant specificity?
```

---

## 11. Separate Claim, Evidence, and Interpretation

Distinguish:

```text
what was done
what was observed
what was inferred
what remains uncertain
```

Scientific claim pattern:

```text
We test [claim] by comparing [condition] against [baseline/reference].
The result shows [finding].
This supports [interpretation] within [scope].
```

Bad:

> The method proves that the digital twin is accurate.

Better:

> The agreement between simulated and reference-generated received power supports solver-regime consistency under the tested conditions.

Test:

```text
[ ] Is the evidence behind each major claim visible?
[ ] Is interpretation separated from observation?
[ ] Is the claim scoped to tested conditions?
[ ] Is causal language justified by the study design?
```

Use:

```text
agreement
gap
difference
consistency
deviation
```

instead of `error` when there is no measured ground truth.

---

## 12. Make Methods Reproducible

Methods should explain how and why the study was done in enough detail that another competent researcher could reproduce the result.

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

Test:

```text
[ ] Could another researcher repeat the analysis?
[ ] Are parameters, controls, and assumptions visible?
[ ] Are method details explained by function rather than local workflow?
```

---

## 13. Write Experiments as a Validation Ladder

Do not report figures one by one.

Each experiment should test a claim and prepare the next claim.

Evidence chain:

```text
intro problem
-> contribution claim
-> experimental intent
-> baseline/reference
-> controlled conditions
-> metric
-> result
-> interpretation
-> contribution supported
-> scope
```

Bad:

> Figure 5 shows mesh complexity. Figure 6 shows coverage fields.

Better:

> We first examine whether semantic surfaces become solver-visible geometry, because the coverage comparison is interpretable only if added complexity has a known structural source.

Test:

```text
[ ] Does every experiment trace back to a contribution claim?
[ ] Is experimental intent stated before figure/table/metric details?
[ ] Is the baseline or reference condition named and justified?
[ ] Are controlled conditions and metrics stated before results?
[ ] Is the result interpreted as evidence for the contribution?
[ ] Does each experiment prepare the next one?
```

---

## 14. Quantify Carefully and Bound Scope

Avoid unsupported qualitative claims:

```text
better
robust
efficient
accurate
significant
strong
clear
```

When possible, report:

```text
effect size
absolute value
relative change
sample size
confidence interval
variance
error bound
reference condition
unit
```

Bad:

> The method significantly improves accuracy.

Better:

> The method reduces median localization error from 1.8 m to 1.1 m under the same receiver placement conditions.

Test:

```text
[ ] Are comparison, metric, unit, and scope visible?
[ ] Is numerical precision justified?
[ ] Are p-values not the only evidence of importance?
[ ] Does the conclusion stay within the evidence?
```

---

## 15. Use Figures and Captions as Evidence

A figure or table should carry evidence that the text needs.

Captions should name the phenomenon, comparison, or diagnostic.  
The body text should interpret the figure.

Bad caption:

> Figure 6 shows path-gain results for four campuses.

Better caption:

> Coverage-field agreement between generated radio scenes under matched simulation settings.

Test:

```text
[ ] Does each figure/table support a specific claim?
[ ] Does the caption state the phenomenon rather than full interpretation?
[ ] Are axes, units, labels, legends, and conditions clear?
[ ] Does the body text interpret only what the argument needs?
[ ] Do text, figure, and table avoid unnecessary repetition?
```

---

## 16. Calibrate Novelty, Contribution, and Limitations

State what is new, relative to what, and under what scope.

Avoid strong labels unless proven:

```text
first
novel
universal
general
robust
complete
accurate
optimal
state-of-the-art
```

Limitations should state:

```text
boundary
cause
consequence
effect on interpretation
remaining question
```

Bad:

> We present a universal digital-twin framework.

Better:

> We present a pipeline for constructing radio-ready scenes from geographic bounds, map semantics, and optional terrain data.

Bad:

> This study has some limitations.

Better:

> Because the evaluation does not use measured propagation data, the results support solver-regime agreement rather than real-world calibration.

Test:

```text
[ ] Is the contribution strong but defensible?
[ ] Is the scope explicit?
[ ] Are limitations boundaries rather than apologies?
[ ] Are alternative explanations considered when relevant?
```

---

## 17. Citation, Reporting, and Integrity

Citations should support the exact sentence they attach to.

Before final revision, check venue instructions and reporting requirements.

Report when required:

```text
data availability
code availability
funding
conflicts of interest
ethics approval
consent
author contributions
AI/tool use
registration or protocol
```

Test:

```text
[ ] Does each citation support the attached claim?
[ ] Are key methods, datasets, and prior claims cited?
[ ] Are references accurate and relevant?
[ ] Are required availability, ethics, funding, conflict, and contribution statements present?
[ ] Is AI/tool use disclosed when required?
```

---

## Response Contracts

Use the smallest response format that fits the request.

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

---

## Final Acceptance Rule

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

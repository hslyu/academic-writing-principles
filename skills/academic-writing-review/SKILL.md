---
name: academic-writing-review
description: Use when reviewing, auditing, or final-checking academic and technical prose after text exists. Trigger for final polish, submission checks, AI-like expression cleanup, overclaiming, causal-strength calibration, scope and limitation checks, unsupported novelty claims, abbreviation checks, figure and caption consistency, citation support, and engineering-style review that removes dramatic rhetorical frames.
---

# Academic Writing Review

Use this skill to audit existing prose before accepting or submitting it.

The review should preserve the argument while checking whether the text is defensible, scoped, coherent, and free of mechanically generated surface patterns.

## Scientific Integrity Checks

A passage passes only if it is:

```text
claim-driven
domain-level
evidence-supported
scope-bounded
reproducible where needed
coherent across sentence, paragraph, section, and paper levels
```

Check for unsupported changes or overclaims:

```text
[ ] No new method, dataset, metric, baseline, result, limitation, contribution, or claim is invented.
[ ] Evidence type is visible behind each major claim.
[ ] Observation, interpretation, and uncertainty are separated.
[ ] Causal language is justified by the study design.
[ ] Scope stays within the tested conditions.
[ ] Novelty wording is strong but defensible.
```

Avoid unsupported qualitative claims:

```text
better
robust
efficient
accurate
significant
strong
clear
universal
general
complete
optimal
state-of-the-art
```

Use stronger wording only when the evidence supports it.

## Engineering Style Checks

Before accepting a rewrite, scan for AI-like surface markers:

- repeated nontechnical words in adjacent sentences
- repeated sentence openings such as `This ...`, `We ...`, or `Because ...`
- filler logical adverbs such as `therefore`, `consequently`, `ultimately`, and `specifically`
- vague demonstratives such as `this`, `it`, or `such an approach` without a fresh antecedent
- promotional adjectives or verbs stronger than the evidence supports
- rhetorical frames that dramatize the claim instead of stating the engineering relation directly
- train-car sentences that chain several operations with commas and `and`
- abbreviations introduced late, left undefined, or used only once

Do not fix AI-like prose by adding dramatic rhetoric, forced synonyms, or hidden limitations. Preserve stable technical terms, evidence strength, and scope. Remove only surface patterns that make the prose mechanically generated.

## Methods, Results, and Evidence Checks

Methods should let another competent researcher repeat and interpret the result.

Check whether relevant details are visible:

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

Results should form a validation ladder:

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

Use `agreement`, `gap`, `difference`, `consistency`, or `deviation` instead of `error` when there is no measured ground truth.

## Figures, Captions, Citations, and Reporting

Check only when relevant to the user's request or the provided text:

```text
[ ] Does each figure or table support a specific claim?
[ ] Does the caption state the phenomenon rather than the full interpretation?
[ ] Are axes, units, labels, legends, and tested conditions clear?
[ ] Are abbreviations defined before first use?
[ ] Is an abbreviation avoided when it is not reused?
[ ] Does each citation support the attached claim?
[ ] Are required data, code, funding, conflict, ethics, contribution, or AI/tool-use statements present when required by the venue?
```

## Response Contract

Prioritize findings over summary:

```text
Findings:
Required fixes:
Suggested edits:
Final acceptance check:
```

If no substantive issues are found, state that explicitly and mention residual risks or missing context.

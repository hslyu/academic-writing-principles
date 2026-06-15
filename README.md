# Academic Writing Skills

Codex skills for planning, writing, and reviewing academic and technical prose while preserving claim structure, evidence, scope, causal strength, and engineering-style clarity.

## Layout

```text
skills/
├── academic-writing-plan/
│   ├── SKILL.md
│   └── agents/openai.yaml
├── academic-writing-write/
│   ├── SKILL.md
│   └── agents/openai.yaml
└── academic-writing-review/
    ├── SKILL.md
    └── agents/openai.yaml
```

## Skill Roles

- `academic-writing-plan`: design the argument before drafting; use for outlines, claim maps, contribution framing, section endpoints, paragraph endpoints, evidence plans, and scope boundaries.
- `academic-writing-write`: draft or revise prose after the intended claim is known; use for paragraph rewrites, academic style, flow, abstraction level, list control, and endpoint-preserving edits.
- `academic-writing-review`: audit existing prose before acceptance or submission; use for overclaims, causal strength, scope, abbreviations, figures, captions, citations, AI-like surface markers, and rhetorical-frame removal.

## Local Install

From `~/dotfiles/codex`, run:

```bash
./install-skills.sh
```

The installer copies the three skills into `~/.codex/skills/`.

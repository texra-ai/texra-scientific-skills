# texra-scientific-skills

Agent skills for scientific writing, reviewing, and figure work — built around the TeXRA research assistant. Distributed as a [Claude Code plugin](https://docs.claude.com/en/docs/claude-code/plugins) and as a [Codex](https://github.com/openai/codex) skills bundle. Skills follow the standard `SKILL.md` format, so any agent that reads it can use them.

## Skills

| Skill | Purpose |
| --- | --- |
| [`inline-paper-critic`](skills/inline-paper-critic/SKILL.md) | Leave compile-safe inline review comments on derivation-heavy LaTeX manuscripts. |
| [`literature-search`](skills/literature-search/SKILL.md) | Discover, verify, and synthesize academic literature with primary-reference grounding. |
| [`manuscript-review`](skills/manuscript-review/SKILL.md) | Audit technical manuscripts for math correctness, notation consistency, and evidence quality. |
| [`math-ocr`](skills/math-ocr/SKILL.md) | Convert handwritten or image-based math into notation-consistent, compilable LaTeX. |
| [`mathematical-enhancer`](skills/mathematical-enhancer/SKILL.md) | Strengthen the math itself — better proofs, sharper results, cleaner derivations. |
| [`scientific-presenter`](skills/scientific-presenter/SKILL.md) | Build and iterate on scientific talks, posters, and Beamer decks. |
| [`scientific-simplifier`](skills/scientific-simplifier/SKILL.md) | Simplify scientific code, LaTeX, and prose while preserving exact behavior. |
| [`tikz-figure-builder`](skills/tikz-figure-builder/SKILL.md) | Create or refine TikZ figures, iteratively compile-and-look. |
| [`writing-commenter`](skills/writing-commenter/SKILL.md) | Annotate drafts with inline comments on logic, notation, narrative flow, and editorial impact. |

## Install

### Claude Code

```
/plugin marketplace add texra-ai/texra-scientific-skills
/plugin install texra-scientific-skills@texra-scientific-skills
```

Update: `/plugin marketplace update texra-scientific-skills`.

### Codex

```bash
git clone https://github.com/texra-ai/texra-scientific-skills.git ~/.codex/texra-scientific-skills
mkdir -p ~/.codex/skills
ln -sfn ~/.codex/texra-scientific-skills/skills ~/.codex/skills/texra-scientific-skills
```

Restart Codex. Update: `cd ~/.codex/texra-scientific-skills && git pull`.

### Any other agent

Clone and copy or symlink individual skill directories into your agent's skill location.

```bash
git clone https://github.com/texra-ai/texra-scientific-skills.git
ln -s "$PWD/texra-scientific-skills/skills/manuscript-review" ~/.claude/skills/manuscript-review
```

## Layout

```
skills/<skill-name>/
├── SKILL.md           # frontmatter + workflow / quality bar
├── references/        # deeper checklists referenced from SKILL.md
└── agents/            # optional sub-agent definitions
```

## Related

- [`texra-ai/texra-lean-skills`](https://github.com/texra-ai/texra-lean-skills) — companion collection for Lean 4 / Mathlib formalization.

## License

[MIT](LICENSE) © texra-ai

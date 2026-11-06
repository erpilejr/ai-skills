# ai-skills

My personal library of AI agent skills. Each one is a folder under `skills/` with a `SKILL.md`, in the
[Agent Skills](https://agentskills.io/specification) format that Claude Code and other agents read.

## Use it

```bash
git clone git@github.com:erpilejr/ai-skills.git ~/projects/ai-skills
ln -s ~/projects/ai-skills/skills ~/.claude/skills
```

## Add a skill

In any Claude session, say **"add the pattern to our skill set"**. The `adding-to-skill-set` skill writes
the new skill, updates the index below, commits, and pushes.

## Index

| Skill | Use when | Origin |
|-------|----------|--------|
| [adding-to-skill-set](skills/adding-to-skill-set/SKILL.md) | You ask to capture a pattern from the conversation as a skill | Repo bootstrap |
| [council-review](skills/council-review/SKILL.md) | You want 5 independent adviser takes, anonymous peer review and a Chairman verdict on a design or plan | Mobile App Factory design council (2026-11-06) |
| [business-review](skills/business-review/SKILL.md) | You want a product or tool reviewed as a business: SWOT, SaaS gaps, go/no-go gates | Mobile App Factory SaaS review (2026-11-06) |
| [goldfish-review](skills/goldfish-review/SKILL.md) | You want a design doc or plan stress-tested by zero-context reviewers in staged rubrics (Google's Elephant-Goldfish Model) | Agent Harness MVP plan EGM review (2026-11-07) |

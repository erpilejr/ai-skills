---
name: adding-to-skill-set
description: Use when the user says "add the pattern to our skill set", "add this to our skills", "make this a skill", or otherwise asks to capture a working method, prompt pattern, or process from the conversation as a reusable AI skill in their skills repo.
---

# Adding to the skill set

## Overview
The user keeps a personal skills repo at `~/projects/ai-skills` (GitHub: `erpilejr/ai-skills`, private).
`~/.claude/skills` is a symlink to its `skills/` folder, so a skill pushed there is live in every session.
When they ask you to add a pattern, turn it into a skill, commit it, and push it. Do the whole thing in one go.

## Steps
1. **Find the pattern.** Use the conversation's recent work: what method, prompt shape, or process worked?
   If "the pattern" could mean two different things, offer both readings in one question and wait.
   Otherwise go ahead.
2. **Check for overlap.** `ls ~/projects/ai-skills/skills` and grep the descriptions. If a skill already
   covers it, update that skill instead of adding a near-duplicate.
3. **Write `skills/<name>/SKILL.md`:**
   - `name`: short and hyphenated, 1–3 words naming the thing (`council-review`, `spec-interview`)
   - `description`: third person, starts with "Use when…", gives only the triggers and symptoms, never the
     steps. Keep it under 500 characters.
   - Body: Overview (1–2 sentences), When to use / when not to, the steps or rules, Common mistakes.
     Keep it under 500 words. Make it general: no project names, dates, or "in this session we…" stories.
   - Add supporting files only for scripts or long reference material.
4. **Update the index** table in `README.md` (skill, when to use, where it came from).
5. **Commit and push:**
   ```bash
   cd ~/projects/ai-skills && git add -A && git commit -m "Add <name> skill" && git push
   ```
6. **Report** the skill name, its one-line trigger, and the GitHub link to the file.

## Common mistakes
- Writing a description that summarizes the steps. Agents then follow the description and skip the body.
- Copying the conversation verbatim. Pull out the reusable method instead.
- Leaving the change unpushed, or pushing without updating the README index.
- Asking for permission to push. This request is the permission.

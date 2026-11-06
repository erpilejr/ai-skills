---
name: goldfish-review
description: Use when the user asks for an "elephant-goldfish", "goldfish", or EGM review, or wants a design doc, spec, or implementation plan stress-tested by zero-context reviewers before building, especially when the author (human or agent) has been deep in the conversation and may be reading assumptions into the text that the page does not state.
---

# Goldfish review (Elephant-Goldfish Model)

## Overview
The **elephant** (you, with the whole conversation) wrote the doc. **Goldfish** reviewers are fresh sub-agents
that see only the doc and the files it cites, so they catch what the page never says. The method and reviewer
personas come from Google's open-source EGM (`github.com/google/elephant-goldfish-model`, Apache 2.0).

**When not to use:** small fixes or one-right-answer questions. For a business or strategy verdict with
debate, use `council-review` instead; this skill judges the *document*.

## Setup
1. If the EGM plugin is installed (`/egm:egm-review`), use it. Otherwise shallow-clone the repo into the
   scratchpad: personas are in `agents/*.md`, rubrics in `resources/document_standards/*.md`.
2. Find the split: the feature spec (what and why) versus the implementation plan (tasks, files). If the
   plan lives in another file, review that file in stage 9.
3. Pick the mode. Default to the **consolidated** run (all stages, one report) unless the user wants to
   stop after each stage.

## Stages
Each reviewer is a separate fresh sub-agent. Give it its persona path, its rubric path, the target file
(and line range), and a report path. **Never** give it your summary, opinions, or other reports. Tell it to
skip git history and process logs. Run independent stages in parallel.

| Stage | Reviewers (persona file) | Rubric | Reads |
|---|---|---|---|
| 5 Zoom out | `zoom_out`, `inventive_catalyst` | zoom-out | whole doc + cited files |
| 6 Comprehension | `comprehension` | none | **doc only** |
| 7 Critic | `design_critic`, `structural`, `style` | feature-spec | feature range |
| 8 Second zoom out | `zoom_out`, with stage 5 report | zoom-out | whole doc, after 5–7 |
| 9 Readiness | `implementation_readiness`, `codebase_details` | implementation-readiness | plan range + the real code |

Stage 6 is a self-containment test: the reviewer paraphrases the doc. Show the user that paraphrase, since
a wrong paraphrase points to the gap.

## Synthesis (the elephant's job)
1. **Verify every finding** against the doc and code before keeping it. Goldfish are wrong often, because
   they lack context. Mark each one *confirmed*, *contested* (give the reason), or *already handled at §x*.
2. Merge duplicates into actions by priority: 🔴 Blocker, 🟡 Major, 🟢 Nit.
3. Write `consolidated_review_report.md`: verdict line, prioritized actions with file:line, contested
   findings with reasons, the stage-6 paraphrase, and a traceability table (raw finding → action).
   Keep raw stage reports beside it.
4. Say so near the top if you wrote the doc being reviewed.
5. Ask which actions to apply. Apply only approved ones, then allow at most **one** re-review per stage.

## Common mistakes
- Reviewing in your own context. That is not a goldfish review; stop if sub-agents are unavailable.
- Pasting your summary into the prompt "to save time". The reviewer inherits your blind spots.
- Passing every finding through unchecked. Contest the wrong ones, with reasons.
- Skipping stage 8. Reading the other reports, it reconciles their conflicting fixes and often finds what all
  of them missed.
- Taking severities at face value. Rubric-driven reviewers mark "doc differs from code" or "missing section"
  as Blockers. Re-rate them by what actually breaks.
- Endless review loops. One re-audit per stage, then record what is left as accepted trade-offs.
- Flattery or chat dumps. Write reports to files and lead with what is wrong.

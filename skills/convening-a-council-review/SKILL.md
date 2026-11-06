---
name: convening-a-council-review
description: Use when the user asks for a "council", a panel of advisers, or several independent sub-agent opinions on a design, spec, plan, or business idea, especially before committing to build, when a document feels too big, or when the author may be too close to their own work to see its gaps.
---

# Convening a council review

## Overview
Five sub-agents with different lenses review a document **independently**. Then they peer-review each other's
takes **anonymously**. Then a Chairman writes one synthesis with a verdict and an **exact kill condition**.
The value comes from independence and disagreement, so protect both.

**When not to use:** small changes, or questions with one right answer. Use a single reviewer for those.

## The five advisers
| Adviser | Lens |
|---|---|
| **Contrarian** | What breaks, contradicts itself, or is unsafe? What's the biggest risk? |
| **First-Principles Thinker** | What's the core problem? Which load-bearing assumptions are untested? What's the minimal rebuild? |
| **Expansionist** | What upside, adjacent opportunities, or cheap additions are being missed? |
| **Outsider** | Explain it in one line, as a smart non-expert would. Is it realistic for the people who'll do it? |
| **Executor** | What blocks starting on Monday? What's the smallest slice to ship, and in what order? |

## Steps
1. **Independent takes (in parallel).** Start five fresh sub-agents. Give each one the document paths, its own
   lens, and the output shape: findings, biggest risk, and a recommendation. Don't give them your own opinion or
   another adviser's take.
2. **Anonymous peer review (in parallel).** Shuffle the five takes and label them A–E so letters don't match the
   order above. Each adviser, keeping its own lens, reports which take it weighs most and why, **what all five
   missed**, and any factual corrections.
3. **Chairman synthesis.** Write it yourself, in this order:
   - **Verdict** in one line (e.g. proceed / proceed re-scoped / stop), followed by numbered next moves
   - **Exact kill condition**: measurable conditions under which the plan is abandoned, and what to fall back to
   - **Strongest points** in a table: point, and who raised it (including peer-review catches)
   - **Contradictions to fix** in a table: where, what, suggested fix (only ones checked against the doc)
   - **Main dissent**: each real disagreement, both sides, and the Chairman's ruling with a reason
   - **Monday-morning actions**: who does each one, in order
   - Appendix: summaries of the five takes, the peer-review table, and the letter key
4. **Disclose bias.** If the Chairman also wrote the document, say so near the top.
5. **Deliver** as one document (PDF if the user wants something shareable, with any wireframes attached).
   Then ask whether to apply the fixes.
6. **Apply only after approval.** Mark each change in the source document "(council fix)" and log it.

## Common mistakes
- Running advisers in one context, or showing them earlier takes. Independence is gone and they converge.
- Skipping peer review. The "what all five missed" question often finds the most important point (e.g. "no
  baseline to compare against").
- A vague kill condition ("if it isn't working"). It must be a number or a check you can test.
- Letting the Chairman overrule a decision the owner made explicitly. Keep the decision, and let the kill
  condition test it.
- Accepting every Expansionist addition. Rule on each one, and park any that grow the scope.

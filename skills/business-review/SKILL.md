---
name: business-review
description: Use when the user asks to review a product, design, or internal tool "businesswise", as a SaaS, for viability, market fit, or with a SWOT analysis, or asks whether something they're building for themselves could be sold.
---

# Business review

## Overview
Test whether the thing holds up as a business, using current market evidence. End with a verdict and
**measurable go/no-go gates**, not just a SWOT grid. Feed any finding that affects the product as it stands
today back into the design.

**When not to use:** a pure technical design review. Use `council-review` for that.

## Steps
1. **Frame the question in one line.** Example: "if this were sold as a SaaS to other X, does the business hold
   up?" Note anything in the design that supports or blocks that framing (e.g. a "single user in v1" non-goal).
2. **Research current facts** with a few targeted web searches, sent in parallel:
   - competitors and their pricing
   - market size and growth
   - platform or regulatory rules that could hit this category (app store policies, data laws)
   Record a source for every number.
3. **Write the report** in this order:
   - **Verdict** in one line (e.g. "promising as a niche, not yet a business"), followed by a short paragraph:
     where the real gap is, and why it's hard or costly to serve
   - **SWOT** as a 2×2. Each item is a bold claim plus one line of evidence.
     - Strengths and weaknesses come from the design.
     - Opportunities and threats come from the market research.
   - **What a commercial version would need that the design doesn't have**, as a table of gap and why.
     Typical gaps: pricing and spend caps, multi-tenant infrastructure, key or secret custody, customer
     onboarding, terms and liability, unit-economics tracking.
   - **Go / no-go gates**: say "only sell when all are true" and give 2–3 measurable conditions, such as cost
     per unit under ⅓ of price, N outside users succeeding without help, or the core already proven. Add a
     drop condition.
   - **Sources**, grouped by topic
4. **Feed back now-rules.** If a finding constrains even the personal or v1 version (e.g. a store rule against
   running generated code inside an app), add it to the design document, not only the report.
5. **Deliver** it as a section of the findings document or PDF, and log it.

## Rules
- **Be honest about weak numbers.** Market figures from vendor blogs and aggregators often disagree. Say so,
  give ranges ("reportedly ~$400–500M"), and cite them. Never present one figure as fact.
- **Personal choices don't carry over to customers.** A choice the owner made for themselves (e.g. "no
  budgets") becomes a weakness or a gap for paying customers. Call it out.
- **Treat cost to serve as a first-class item.** Name the big cost drivers (compute, licences, minimum lease
  terms) and compare them with competitor prices.

## Common mistakes
- A SWOT with no verdict or gates. The reader can't act on it.
- Opportunities and threats written from memory, not current searches.
- Leaving a constraint that applies today in the report only.

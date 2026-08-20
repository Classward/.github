<!--
  Drafting this description with an AI agent? Read ./ai_pr_guidelines.md first.
  https://github.com/Classward/.github/blob/main/.github/ai_pr_guidelines.md

  Short version: delete the "PR Title" section below (it is guidance, not a section to fill),
  keep it brief, list only tradeoffs actually weighed, write "None." under Next Steps when
  there are none, and only tick etiquette boxes that are genuinely true.
-->

## References
_Link the Jira ticket this work came from._

[TICKET-100](https://your-jira/browse/TICKET-100)

## PR Title 
At most 1 sentence in plain English

Prefixed correctly e.g. `feat:`, `fix:`, `docs:`. View the prefixes [here](https://github.com/Classward/.github/blob/main/pr_prefix_guidelines.md)

Example - BAD: `Fix bug in invoice system`

Example - GOOD: `Fix: misplaced decimal point miscalculates invoice subtotal`

## Context
_~200 words: why this ticket exists. What tradeoffs did you weigh, and why this choice? Does it need an ADR? New or updated docs?_

## Next Steps
_Anything this PR needs outside of code — tasks or updates on the server._

## Testing
_Manual steps if they apply. One sentence per test added (or a summary block for a whole new file). Are these tests redundant with coverage up/downstream?_

## Screenshots
_Required if you are resolving something visual._

## Etiquette
- [ ] **LOC cap: 500** — an extreme upper bound, not a target.
- [ ] The description and the committed code effectively explain and show what this PR is changing.
- [ ] If the change had to exceed 500 lines, it was split into smaller PRs against an integration branch.
- [ ] Opened as a draft and self-reviewed in the GitHub UI first.
- [ ] Ran an AI code review before opening for review.

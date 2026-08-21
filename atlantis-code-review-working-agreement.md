
# Atlantis Code-Review Working Agreement

This is a living document. It sets the expectations for code review on Atlantis codebases so the process is explicit rather than assumed, and it will change as the team learns what works.

## Why we review

The primary purpose of code review is to keep the overall code health of Atlantis codebases improving over time. Every tool and process here works toward these goals:

1. Build trust between team members
2. Fewer bugs in production
3. More maintainable codebases
4. Better architectural design
5. Knowledge distributed across the team
6. Mentorship opportunities

## Scope

This agreement covers changes to Atlantis codebases with two exceptions.

**Dependency bumps** don't need review.

**Hotfixes are break-glass.** Skipping review is sanctioned when production is broken and waiting on a reviewer makes it worse. Two things are still required:

1. **Say it out loud.** Announce the hotfix to the team while you're doing it, so nobody is surprised to find an unreviewed change in production.
2. **Leave a record.** Open a PR after the fact if you can, so the change is documented and can still be reviewed. If you can't, file a ticket.

A hotfix nobody knew about is the failure mode this exception exists to avoid.

## Authors

Submit a PR that stays inside the scope of the change requested, and that you can argue improves the health of the codebase.

Review your own pull request in GitHub's UI, and run an agentic review, before you ask for human review.

### Prefer small PRs

1. Reviewed faster
2. Reviewed more thoroughly
3. Less likely to introduce bugs
4. Less wasted work if rejected outright
5. Easier to merge with other developers' work
6. Easier to design well
7. Less work blocked on this one review

If the scope touches many files or spans the full stack, use an integration branch and open smaller sequential PRs into it. Merge the integration branch into development once every PR has been reviewed. You can also stack PRs on top of each other so a reviewer walks down the tree one at a time.

### When a large PR is acceptable

1. Deleting entire files or large sections of dead code
2. Generated output from linting or formatting tools
3. A feature that genuinely cannot be broken up. State this at the top of the summary and describe what you tried. A reviewer may be able to help you split it.

### What a manageable PR looks like

1. Focuses on one atomic change or feature
2. Includes only the files that change needs
3. Splits separable parts into separate reviews
4. Can be reviewed in 10 to 20 minutes
5. Typically under 500 lines
6. Typically fewer than 20 files
7. Summary is plain English and human readable
8. Uses one of the approved tag prefixes `[link to the GitHub artifact]`
9. Provides the context a reviewer needs: screenshots where they apply, and test names with one sentence each saying what the test covers
10. Has been reviewed by an agent before human review was requested

## Reviewers

You have ownership of the code you review. Your job is to keep each change at a quality where the overall code health of the codebase is not decreasing. Codebases degrade through small losses in code health, especially when a team is under pressure and feels it has to take shortcuts.

You also have to let people make progress. If nobody can land an improvement, the codebase never improves. A reviewer who makes changes hard to land teaches the team to stop trying.

1. Approve once the PR definitely improves the overall code health of the system. This is the key principle of these guidelines.
2. There is no perfect code, only better code. Do not ask the author to polish everything. Weigh the importance of each suggestion against the cost of another round trip. Seek continuous improvement, not perfection.
3. Leave the comment when something could be better, but prefix it with `Nit:` when it is only polish, so the author knows they can skip it.
4. Comments that teach are always welcome. Sharing knowledge is part of improving code health over time. Make it clear when a comment is purely educational.
5. Technical facts and data overrule opinions and personal preferences.
6. The style guide is the authority. Where it is silent, accept the author's choice and open a conversation about adding it to the guide.
7. Where nothing else applies, ask the author to be consistent with the established patterns in the codebase.

### What to look at

`[TBD: confirm this list with the team.]` Design, functionality against the ticket, test coverage for the paths that matter, naming, comments that explain why rather than what, and consistency with surrounding code.

## Comment prefixes

`[TBD: agree on the final set.]` Prefixing a comment tells the author how to treat it without them having to guess.

| Prefix | Means |
|---|---|
| `Nit:` | Polish. Ignore it if you disagree. |
| `Question:` | I need to understand this before I can judge it. |
| `Blocking:` | I need this changed before I approve. |
| `FYI:` | Educational, no action needed. |

## Response times

`[TBD: the team needs to agree on real numbers here. This is the gap most likely to make the rest of the document fail.]`

- First response to a review request: `[TBD]`
- Follow-up response after the author pushes changes: `[TBD]`
- Approvals required to merge: `[TBD]`

## Comment tone and disagreement

**Don't take it personally.**

A review protects the quality of our codebases and our products. When a reviewer critiques your code, it is an attempt to help you, the codebase, and the company. It is not an assessment of your ability.

As an author:

1. Don't express frustration in the comments. It adds noise to a process that doubles as a decision log.
2. Never respond in anger. Responses live forever in GitHub. Take a few breaths and come back when you can respond kindly.
3. If a reviewer isn't giving polite, constructive feedback, tell them in person or over private message. Explain what you didn't like and what you'd prefer instead. If that doesn't resolve issues, escalate to your manager.
4. Ask for clarification in the comments when you need it.
5. Think collaboratively. Getting a piece of work across the finish line and then receiving change requests is frustrating, especially requests you disagree with. Ask clarifying questions and push back where it's warranted.
6. Fix the code. If you believe it shouldn't be fixed, back that with data, industry standards, or the team style guide.

Responding to a request you disagree with:

Bad:

```
No, I won't do that.
```

Good:

```
I went with X because of the following tradeoffs... My understanding is that Y
would be worse for these reasons... Are you suggesting Z would be better? Do you
mind explaining?
```

**Courtesy and respect come first.**

## Agent-authored code

Most of us are using agents, so the agreement has to account for it.

1. Run an agentic review before you request human review. This is a requirement, not a suggestion.
2. The summary must be plain English and human readable. A reviewer should be able to tell what the PR exists to achieve from the summary alone. 
3. If you have an agent writing your PR summaries for you, it's your responsibility to make sure those summaries don't read like slop.
4. It is forbidden to use an agent to respond to PR comments. All interactions are human interactions. Using an agent to bypass team communication is antithetical to the process.
5. Agent output is yours once you open the PR. "The agent wrote it" is not an answer to a review comment.
6. Agents make it trivial to generate a 5,000-line PR. The size guidance above applies with more force, not less.

## Resolving disagreement

Author and reviewer are expected to reach consensus using this document and the ones it points to.

If that is hard, call a face-to-face meeting or start a Slack thread. Take it off GitHub once a single subject runs past a handful of exchanges.

If you still can't agree, escalate: a broader team discussion, or a three-way meeting with the team lead or engineering manager.

**Don't let a pull request sit because you can't reach a timely agreement.**

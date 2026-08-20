# AI PR Instructions

How to fill in [`pull_request_template.md`](./pull_request_template.md) when an AI agent is
drafting the pull request description.

These are corrections to real mistakes, not style preferences. Read them before writing the body.

---

## Always fetch the template fresh

Pull the template from GitHub immediately before writing the body — never from memory, never from
a copy made earlier in the session. A stale copy silently drops sections added upstream.

Use `gh api` rather than a raw URL, since the repo is private:

```bash
gh api repos/Classward/.github/contents/.github/pull_request_template.md --jq '.content' | base64 -d
```

Fetch this instructions file the same way when you need it:

```bash
gh api "repos/Classward/.github/contents/.github/AI PR Instructions.md" --jq '.content' | base64 -d
```

## Drop the `## PR Title` section from the body

It is instruction to the developer on how to name the PR, not a section to fill in. Its guidance
goes into the actual PR title; the heading itself never appears in the description.

This is the only section that gets removed outright.

## Be concise

The word counts in the template are ceilings, not targets. Most PRs need a few sentences per
section. A long description is not a thorough one.

## Context — only real tradeoffs

List alternatives that were **actually weighed**. Never invent a rejected option to make the
section look considered. If the fix was obvious and no alternative was seriously entertained, say
what changed and why, then stop.

## Next Steps — write "None." when there are none

Do not pad with deploy suggestions, follow-up ideas, or out-of-scope observations dressed up as
next steps. This section is for work outside the code that someone actually has to do.

## Testing — the tests, and manual steps only if a human must run them

One line per test. Include manual steps only when the reviewer genuinely has to perform them to
evaluate the PR; otherwise write "No manual steps."

No RED/GREEN narration, no verification transcripts, no recounting of how the work was validated
during development.

## Screenshots — required for anything visual

Otherwise "N/A" with a short reason.

## Etiquette — only check what is actually true

- Leave **"Opened as a draft and self-reviewed in the GitHub UI first"** unchecked. That one
  belongs to the human opening the PR.
- Leave **"Ran an AI code review before opening for review"** unchecked unless a review actually
  ran.
- Say which boxes were left unchecked when handing over the link.

## Sections that do not apply get an explicit "N/A" plus a reason

Never delete a section silently. The one exception is `## PR Title`, which is always removed.

## No Jira ticket?

Say so in References and link the real origin instead — a Honeybadger fault, a Sentry issue, a
Slack thread.

## Titles are `type(scope): summary`

The repo squash-merges, so the PR title becomes the commit message on `main` and feeds the
changelog. Scope is an optional noun, never an issue id.

Types: `fix`, `feat`, `build`, `chore`, `docs`, `test`, `refactor`, `ci`, `localize`, `bump`,
`revert`.

Full rules: [`pr_prefix_guidelines.md`](../pr_prefix_guidelines.md)

## Base branch

Hotfixes go to `main`. Feature work goes to `development`. Check recent merged PRs if unsure.

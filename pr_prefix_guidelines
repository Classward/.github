# PR Naming Convention

Because we **squash & merge** pull requests, the PR title becomes the commit message on `main` — and that commit message is what generates our changelog and release notes.

To make those readable, every PR title must follow this format:

```
type(scope): summary of changes
```

- `type` — **required**
- `(scope)` — optional
- `summary` — **required**

**Examples**

```
fix: allow useHref on synthetic links
docs: fix typo in usePress docs
feat(virtualization): add support for custom collection renderers
```

---

## Type

Every PR title must start with one of the following types:

| Prefix | Meaning |
| --- | --- |
| `fix` | Fixing a bug |
| `feat` | Adding a new feature |
| `build` | Updates that affect the build system or process |
| `chore` | Miscellaneous commits that do not affect the meaning of the code (whitespace, formatting, missing semi-colons, typos in code, comment adjustments, etc.) |
| `docs` | A change to documentation only |
| `test` | Adding or fixing existing tests |
| `refactor` | A code change that neither fixes a bug nor adds a feature |
| `ci` | Changes to the CI config |
| `localize` | Changes related to translations and localization |
| `bump` | Increase the version of some dependency |
| `revert` | Undoing a previous commit |

## Scope

Optional. If included, it should be a **noun** that gives context about the part of the codebase affected by the change.

```
feat(RAC)
fix(virtualization)
```

> **Do not** use issue identifiers as the scope.

## Summary of Changes

A concise summary of what changed, readable at a glance.

---

> **Note**
> The contents of this guide are subject to change as we roll out this new convention across the repo. Feedback and suggestions are welcome.

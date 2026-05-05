# Contributing to Peptimus Infra

Thank you for your interest in contributing to the Peptimus infrastructure repository. This document outlines the process for submitting changes to this repository.

## Getting Started

1. Fork the repository and clone your fork locally.
2. Install dependencies with `pnpm install`.
3. Create a new branch from `main` for your change.

## Repository Structure

| Path | Purpose |
|---|---|
| `.github/workflows/` | GitHub Actions CI configuration |
| `.github/ISSUE_TEMPLATE/` | Issue templates for all Peptimus repos |
| `.github/PULL_REQUEST_TEMPLATE.md` | PR template for all Peptimus repos |
| `.github/CODEOWNERS` | Code ownership definitions |
| `pnpm-workspace.yaml` | Monorepo workspace configuration |
| `package.json` | Root scripts and shared devDependencies |
| `tsconfig.base.json` | Shared TypeScript base configuration |

## Branch Naming

| Type | Pattern | Example |
|---|---|---|
| CI | `ci/<short-description>` | `ci/add-lint-step` |
| Chore | `chore/<short-description>` | `chore/upgrade-node` |
| Docs | `docs/<short-description>` | `docs/update-codeowners` |
| Fix | `fix/<short-description>` | `fix/ci-pnpm-cache` |

## Development Guidelines

- All CI workflows must use **pinned action versions** (e.g. `actions/checkout@v4`).
- Workflows must not reference any Replit-specific environment variables.
- The clean-ref scan in CI checks for: `@replit`, `REPL_ID`, `REPLIT_DOMAINS`, `REPLIT_DEV_DOMAIN` in source files — do not introduce these.
- Changes to `tsconfig.base.json` affect all packages — test compilation across all repos before submitting.
- Changes to `pnpm-workspace.yaml` must not introduce `@replit/*` catalog entries.
- CODEOWNERS entries must point to `@peptimusdev` for all paths.

## CI Workflow Standards

All CI workflows across Peptimus repos follow this pattern:

1. `actions/checkout@v4` with built-in token
2. `pnpm/action-setup@v4` for pnpm
3. `actions/setup-node@v4` with Node.js 24 and pnpm cache
4. `pnpm install --frozen-lockfile`
5. Type check, lint, and clean-ref scan

When modifying CI, ensure all four repos remain consistent.

## Pull Request Process

1. Ensure CI passes on this repo.
2. Consider whether the change needs to be replicated across other Peptimus repos.
3. Fill out the pull request template completely.
4. Link any related issues using `Closes #<issue>`.
5. Request a review from `@peptimusdev`.

## Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org):

```
ci: pin node version to 24.x in all workflows
chore: upgrade pnpm action to v4
fix: restore frozen-lockfile flag in install step
docs: update CODEOWNERS format
```

## Reporting Issues

Use the issue templates available in the repository:
- **Bug Report** — for reproducible defects
- **Feature Request** — for new functionality proposals

## Code of Conduct

Be respectful and constructive. Contributions that are disrespectful toward maintainers or other contributors will not be accepted.

---

**Maintainer:** [peptimusdev](https://github.com/peptimusdev)

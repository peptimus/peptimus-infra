# Peptimus Infrastructure

[![CI](https://github.com/peptimus/peptimus-infra/actions/workflows/ci.yml/badge.svg)](https://github.com/peptimus/peptimus-infra/actions/workflows/ci.yml)
[![License](https://img.shields.io/badge/license-MIT-00f5ff?style=flat-square&labelColor=0a0f1c)](LICENSE)
[![Author](https://img.shields.io/badge/author-peptimusdev-8b5cf6?style=flat-square&labelColor=0a0f1c)](https://github.com/peptimusdev)
[![pnpm](https://img.shields.io/badge/pnpm-workspace-F69220?style=flat-square&logo=pnpm&logoColor=white&labelColor=0a0f1c)](https://pnpm.io)
[![Node](https://img.shields.io/badge/Node.js-24-339933?style=flat-square&logo=node.js&logoColor=white&labelColor=0a0f1c)](https://nodejs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?style=flat-square&logo=typescript&logoColor=white&labelColor=0a0f1c)](https://www.typescriptlang.org)

Monorepo root, infrastructure configs, deployment scripts, and CI setup for the [Peptimus](https://github.com/peptimus) platform.

**Author:** [peptimusdev](https://github.com/peptimusdev)

---

## Repositories

| Repository | Description |
|---|---|
| [peptimus/peptimus](https://github.com/peptimus/peptimus) | Web frontend (React + Vite + Solana) |
| [peptimus/peptimus-api](https://github.com/peptimus/peptimus-api) | REST API server and database (Express + PostgreSQL) |
| [peptimus/peptimus-shared](https://github.com/peptimus/peptimus-shared) | Shared TypeScript packages |
| [peptimus/peptimus-infra](https://github.com/peptimus/peptimus-infra) | This repository |

---

## Monorepo Structure

```
peptimus-infra/
  artifacts/
    peptimus/          # Web frontend
    api-server/        # API server
    peptimus-video/    # Marketing video
  lib/
    api-spec/          # OpenAPI specification
    api-client-react/  # React Query hooks (generated)
    api-zod/           # Zod schemas (generated)
    db/                # Drizzle ORM schema and client
    integrations/      # Integration utilities
    integrations-openai-ai-server/
    integrations-openai-ai-react/
  .github/
    app.yml            # GitHub App manifest
    workflows/         # CI pipelines
    ISSUE_TEMPLATE/    # Issue forms
    profile/           # Organization profile README
```

---

## Quick Start

```bash
pnpm install
pnpm run typecheck
pnpm run build
```

```bash
pnpm --filter @workspace/api-server run dev
pnpm --filter @workspace/peptimus run dev
```

```bash
pnpm --filter @workspace/api-spec run codegen
pnpm --filter @workspace/db run push
```

---

## GitHub App Setup

This monorepo uses a GitHub App for CI authentication instead of a personal access token.

1. Go to [github.com/organizations/peptimus/settings/apps/new](https://github.com/organizations/peptimus/settings/apps/new)
2. Use the manifest at `.github/app.yml` to configure permissions
3. After creating the app, add two secrets to each repository:
   - `PEPTIMUS_APP_ID` (repository variable)
   - `PEPTIMUS_APP_PRIVATE_KEY` (repository secret)

---

## Stack

| Layer | Technology |
|---|---|
| Monorepo | pnpm workspaces |
| Runtime | Node.js 24 |
| Language | TypeScript 5.9 |
| Frontend | React 18 + Vite + Tailwind CSS |
| API | Express 5 |
| Database | PostgreSQL + Drizzle ORM |
| Blockchain | Solana Mainnet + Metaplex |
| AI | OpenAI GPT |
| CI | GitHub Actions + GitHub App |

---

**Built by [peptimusdev](https://github.com/peptimusdev)**

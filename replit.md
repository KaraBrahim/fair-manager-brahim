# Workspace

## Overview

pnpm workspace monorepo using TypeScript. Each package manages its own dependencies.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **API framework**: Express 5
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

## Workflows (Replit)

- `Backend API` (console) — `PORT=5000 pnpm --filter @workspace/api-server run dev` on port 5000.
- `Start application` (webview) — `PORT=5173 pnpm --filter @workspace/book-fair run dev` on port 5173. Vite proxies `/api/*` to the backend on `localhost:5000`.

PostgreSQL is provisioned via Replit; `DATABASE_URL` is auto-injected.

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.

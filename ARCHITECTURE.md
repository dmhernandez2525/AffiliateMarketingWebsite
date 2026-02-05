# AffiliateMarketingWebsite Architecture

**Version:** 1.0.0
**Last Updated:** February 03, 2026

---

## System Overview

**Affiliate Marketing Website** is a platform for managing affiliate marketing campaigns, tracking referral links, calculating commissions, and processing payouts. Currently only has a basic CRA scaffold - all affiliate functionality needs to be built.

## High-Level Diagram

```
Users / Operators
        │
        ▼
AffiliateMarketingWebsite Core
        │
        ├── Local State / Data Storage
        └── External Integrations / APIs
        │
        ▼
Outputs (UI, Reports, Exports, Logs)
```

## Technology Stack

| Layer | Technology |
|-------|------------|
| Frontend | React 18, TypeScript, Vite (migrate from CRA) |
| Styling | Tailwind CSS + shadcn/ui |
| State | Zustand + TanStack Query |
| Backend | Node.js + Express (to be added) |
| Database | PostgreSQL + Prisma |
| Auth | Clerk |
| Payments | Stripe Connect (affiliate payouts) |
| Analytics | Custom tracking + PostHog |
| Hosting | Render |

## Directory Structure (Top-Level)

```
docker-compose.yml
Dockerfile
package.json
public/
README.md
render.yaml
ROADMAP.md
src/
tsconfig.json
yarn.lock
```

## Data Flow

1. User initiates action (UI/CLI/task).
2. Core logic processes input, validates rules, and triggers integrations.
3. State is persisted (local files, DB, or external systems).
4. Output is rendered to UI, exported, or logged.

## Deployment & Runtime

- Docker Compose
- Render deployment
- Node.js/JavaScript
- Dockerfile

## Security & Quality

- Follow global forbidden/required patterns and lint/typecheck rules
- No hardcoded secrets; use environment variables
- Log errors through approved logger patterns (no console.*)

## Observability

- Structured logs for key workflows
- Health checks for integrations and background tasks

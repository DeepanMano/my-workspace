# Product Workspace

Shared workspace configuration and product briefs for two products:

- **Universal Billing & Inventory** — React 19, Vite, TypeScript
- **Dear Diary** — Next.js, TypeScript, IndexedDB, Web Crypto API, and user-owned cloud storage

This repository is intentionally a planning and development-rules workspace. Backend work with NestJS and PostgreSQL is deferred until a later phase.

## Start here

1. Read [`AGENTS.md`](AGENTS.md) before making changes.
2. Read [`docs/AI-WORKSPACE.md`](docs/AI-WORKSPACE.md) for the complete development rules.
3. Read the relevant product brief under [`products/`](products/).

## Repository layout

```text
.
├── AGENTS.md
├── docs/
│   └── AI-WORKSPACE.md
├── products/
│   ├── universal-billing-inventory/
│   │   └── README.md
│   └── dear-diary/
│       └── README.md
└── .github/
    └── pull_request_template.md
```

## Scope rule

The two product briefs define the current scope. Do not introduce backend services, database migrations, authentication servers, or cloud-provider-specific infrastructure unless a product brief is updated first.

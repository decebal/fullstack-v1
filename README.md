<p align="center">
  <img src="./docs/images/logo.svg" alt="Fullstack V1" width="200" />
</p>

<p align="center">
	<h1 align="center"><b>Fullstack V1</b></h1>
<p align="center">
    A production-ready full-stack SaaS monorepo starter
    <br />
    <br />
    <a href="#whats-included"><strong>What's included</strong></a> ·
    <a href="#prerequisites"><strong>Prerequisites</strong></a> ·
    <a href="#getting-started"><strong>Getting Started</strong></a>
  </p>
</p>

Everything you need to build a production-ready full-stack SaaS. An opinionated stack using the latest Next.js framework with TanStack Query, Supabase, and modern tooling. This monorepo focuses on code reuse and best practices that will grow with your business.

> **Note:** This is a fork and evolution of the [Midday V1](https://github.com/midday-ai/v1) starter kit, enhanced with TanStack Query for robust server state management and additional full-stack features.

## What's included

[Next.js](https://nextjs.org/) - Framework<br>
[Turborepo](https://turbo.build) - Build system<br>
[Biome](https://biomejs.dev) - Linter, formatter<br>
[TailwindCSS](https://tailwindcss.com/) - Styling<br>
[Shadcn](https://ui.shadcn.com/) - UI components<br>
[TypeScript](https://www.typescriptlang.org/) - Type safety<br>
[Supabase](https://supabase.com/) - Authentication, database, storage<br>
[TanStack Query](https://tanstack.com/query) - Server state management<br>
[Upstash](https://upstash.com/) - Cache and rate limiting<br>
[React Email](https://react.email/) - Email templates<br>
[Resend](https://resend.com/) - Email delivery<br>
[i18n](https://next-international.vercel.app/) - Internationalization<br>
[Sentry](https://sentry.io/) - Error handling/monitoring<br>
[Dub](https://dub.sh/) - Sharable links<br>
[Trigger.dev](https://trigger.dev/) - Background jobs<br>
[PostHog](https://posthog.com/) - Product analytics and feature flags<br>
[Playwright](https://playwright.dev/) - End-to-end testing<br>
[react-safe-action](https://next-safe-action.dev) - Validated Server Actions<br>
[nuqs](https://nuqs.47ng.com/) - Type-safe search params state manager<br>
[next-themes](https://next-themes-example.vercel.app/) - Theme manager<br>

## Directory Structure

```
.
├── apps                         # App workspace
│    ├── api                     # Supabase (API, Auth, Storage, Realtime, Edge Functions)
│    ├── app                     # App - your product
│    ├── web                     # Marketing site
│    └── ...
├── packages                     # Shared packages between apps
│    ├── analytics               # PostHog analytics integration
│    ├── email                   # React email library
│    ├── jobs                    # Trigger.dev background jobs
│    ├── kv                      # Upstash rate-limited key-value storage
│    ├── logger                  # Logger library
│    ├── react-query             # TanStack Query hooks and providers
│    ├── supabase                # Supabase - Queries, Mutations, Clients
│    └── ui                      # Shared UI components (Shadcn)
├── tooling                      # Shared configuration used by apps and packages
│    ├── e2e                     # Playwright end-to-end tests
│    └── typescript              # Shared TypeScript configuration
├── .cursorrules                 # Cursor rules specific to this project
├── biome.json                   # Biome configuration
├── turbo.json                   # Turbo configuration
├── LICENSE
└── README.md
```

## Prerequisites

- [Bun](https://bun.sh/) - JavaScript runtime & package manager
- [Docker](https://www.docker.com/) - For local Supabase development
- [Supabase](https://supabase.com/) - Backend services
- [Upstash](https://upstash.com/) - Redis for caching and rate limiting
- [Resend](https://resend.com/) - Email delivery
- [Sentry](https://sentry.io/) - Error monitoring
- [PostHog](https://posthog.com/) - Product analytics
- [Trigger.dev](https://trigger.dev/) - Background jobs
- [Dub](https://dub.sh/) - Link management

## Getting Started

1. Install dependencies using bun:

```sh
bun install
```

2. Copy `.env.example` to `.env` and update the variables.

```sh
# Copy .env.example to .env for each app
cp apps/api/.env.example apps/api/.env
cp apps/app/.env.example apps/app/.env
cp apps/web/.env.example apps/web/.env
```

3. Start the development server:

```sh
bun dev              # Start all apps in development mode
bun dev:web          # Start the web app only
bun dev:app          # Start the app only
bun dev:api          # Start Supabase locally
```

## Available Scripts

```sh
bun build            # Build all apps
bun lint             # Lint all apps
bun typecheck        # Type check all apps
bun format           # Format all files with Biome
bun clean            # Clean all node_modules
bun clean:workspaces # Clean all build outputs
```

## Package Structure

### Apps
- `apps/app` - Main SaaS application with authentication and dashboard
- `apps/web` - Marketing website
- `apps/api` - Supabase local development setup

### Packages
- `packages/analytics` - PostHog analytics integration
- `packages/email` - Email templates using React Email
- `packages/jobs` - Background jobs with Trigger.dev
- `packages/kv` - Upstash Redis for caching and rate limiting
- `packages/logger` - Logging utilities
- `packages/react-query` - TanStack Query configuration and hooks
- `packages/supabase` - Supabase client setup, queries, and mutations
- `packages/ui` - Shared UI components built with Shadcn

### Tooling
- `tooling/e2e` - Playwright end-to-end tests
- `tooling/typescript` - Shared TypeScript configurations

## Key Features

- **Full-stack TypeScript** - Type safety across the entire stack
- **Monorepo architecture** - Shared code between apps with Turborepo
- **Server state management** - TanStack Query for data fetching and caching
- **Authentication** - Supabase Auth with Google OAuth
- **Database** - PostgreSQL with Supabase
- **Type-safe actions** - Server actions with validation using next-safe-action
- **Internationalization** - Built-in i18n support
- **Dark mode** - Theme switching with next-themes
- **Product analytics** - PostHog for analytics and feature flags
- **Error monitoring** - Sentry integration
- **Email** - Transactional emails with Resend and React Email
- **Background jobs** - Trigger.dev for async tasks
- **Rate limiting** - Upstash Redis-based rate limiting
- **E2E testing** - Playwright for reliable end-to-end testing

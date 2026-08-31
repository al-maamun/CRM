# Lumen Architecture

Lumen is a Next.js App Router application. UI composition lives in `src/app`, shared infrastructure lives in `src/lib`, and database schema plus migrations live in `src/db`.

## Boundaries

- Every organization-owned table includes `organization_id` and is queried through an authenticated organization context.
- Authentication is server-owned through Better Auth. The browser never receives database credentials or service secrets.
- Feature modules should validate input with Zod and perform authorization before database mutations.
- External actions such as email, payments, and AI tools will be added behind server-side adapters in later phases.

PHASE 0 intentionally stops before CRM, projects, billing, AI, and other business modules.
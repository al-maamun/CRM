# Security Baseline

- Copy `.env.example` to `.env.local`; never commit credentials.
- Tenant context must be established from the authenticated session, never from an unchecked client value.
- Database access must use parameterized Drizzle queries and explicit organization filters.
- Add audit logging and permission checks before enabling sensitive mutations.
- File storage, payments, OAuth providers, and AI tools require server-side authorization in their respective phases.
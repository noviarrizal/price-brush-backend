# Code quality standards — price-brush-backend

Last updated: 16/10/2026 · Owner: pricebrush-lead · Starter version; no code yet.

## Definition of Done (every task)

- [ ] Acceptance criteria from the plan / PRD are met.
- [ ] Typecheck and tests pass (Workers: Vitest with the Workers pool once configured; Go later: `gofmt -l`, `go vet ./...`, `go test ./...`).
- [ ] Every new endpoint is documented in `docs/codebase/architecture.md` (method, path, auth, request, response, errors) — this is the frontend's contract.
- [ ] Input validation and auth on every non-public endpoint; consistent error shape.
- [ ] Secrets only via `wrangler secret`; names listed in `overview.md`, never values.
- [ ] Every database query is authorised for the signed-in account (Worker checks and/or Postgres RLS); Polar webhooks verify signatures.
- [ ] Rate limits on AI/speech endpoints; usage stays within free tiers (estimate in the handoff).
- [ ] No client personal data in logs.

## Tooling

| Tool | Purpose | Status |
| --- | --- | --- |
| TypeScript strict | Types | Recommended — not configured (no code yet) |
| Vitest + `@cloudflare/vitest-pool-workers` | Worker unit/integration tests | Recommended — not configured |
| ESLint (or Biome) + Prettier | Lint and formatting | Recommended — not configured |
| `golangci-lint`, `go test` | Go quality (Q1 2027) | Later |

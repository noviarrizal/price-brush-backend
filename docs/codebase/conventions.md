# Conventions — price-brush-backend

Last updated: 16/10/2026 · Owner: pricebrush-lead

No code yet. Agreed rules that apply from the first commit:

- Secrets only as Cloudflare Workers secrets (`wrangler secret put`), never in code, `wrangler` config or git. Document names and purpose in `overview.md`.
- Every endpoint: input validation, explicit auth (except documented public endpoints), consistent JSON error shape (to be defined with the first endpoint and recorded in `architecture.md`).
- Rate limits on AI/speech endpoints to stay inside free quotas.
- Neon (Postgres): every query is scoped to the signed-in user's account in the Worker; use Postgres RLS where the access pattern allows. Connect with Neon's serverless driver (or Hyperdrive) — confirm against current Neon + Cloudflare docs.
- Polar webhooks: verify the signature before acting.
- No client personal data in logs.
- UTF-8 files; pnpm for the Workers project; `gofmt`/`go vet`/`go test` once Go arrives.
- Feature work on `feat/<slug>` branches; reviews in `docs/reviews/`; commits only when the founder asks; never deploy without the founder.

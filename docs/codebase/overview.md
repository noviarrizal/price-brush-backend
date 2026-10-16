# Codebase overview — price-brush-backend

Last updated: 16/10/2026 · Owner: pricebrush-lead · Describes the code as it is now (plans live in `docs/plan/`).

## Current state

**No code yet.** The repo contains only `README.md` and these docs. Nothing is deployed.

## Planned stack (from README and decisions — not implemented)

| Phase | Stack | Purpose |
| --- | --- | --- |
| MVP (from 1 Nov 2026) | Cloudflare Workers, TypeScript, pnpm | AI proxy (audio → Groq Whisper transcript → LLM structured quote), Polar webhook, Free-plan limit, public quote links, export/delete |
| MVP | Neon (serverless Postgres) | Data |
| MVP | Auth provider + file storage (to be chosen) | Google sign-in, logo uploads |
| Q1 2027 | Go, in this repo | Sync and Making Tax Digital (HMRC APIs) |

When code lands, this file must list: real versions (from lockfiles/`go.mod`), commands (install, dev, typecheck, test, deploy dry-run), and environment variables / Workers secrets by **name and purpose only, never values**.

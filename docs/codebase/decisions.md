# Technical decisions (ADR log) — price-brush-backend

Last updated: 16/10/2026 · Owner: pricebrush-lead

| Date | Decision | Why | Alternatives considered |
| --- | --- | --- | --- |
| 15/10/2026 | MVP backend on Cloudflare Workers (TypeScript, pnpm); Go added in this repo from Q1 2027 | £0 hosting, fastest path to the first payment by 31 Dec 2026; Go needed later for MTD/HMRC | Go from day one on Render/Koyeb free tier (cold starts, card verification, slower MVP) |
| 17/10/2026 | Neon (serverless Postgres) instead of Supabase | Founder's decision | Supabase (Postgres + auth + storage in one) |
| 15/10/2026 | Polar as merchant of record | Handles UK VAT for a non-UK seller; payout to Indonesia listed in Polar docs | Lemon Squeezy (backup), Stripe (no Indonesian merchants) |

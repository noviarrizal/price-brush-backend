# Architecture — price-brush-backend

Last updated: 16/10/2026 · Owner: pricebrush-lead

## Module map

None yet.

## API endpoints

None yet. When added, document each one here — this table is the contract the frontend relies on:

| Method | Path | Auth | Request | Response | Errors |
| --- | --- | --- | --- | --- | --- |

## Data model

No tables yet. When added, list each Neon (Postgres) table, its columns, indexes, and how access is authorised (in Worker code and/or Postgres RLS).

## External services

| Service | Used for | Status |
| --- | --- | --- |
| Neon | Serverless Postgres | Not set up |
| Auth provider (Google login) | Sign-in | Not chosen — Neon has no auth built in |
| File storage (logos) | Business logo uploads | Not chosen (e.g. Cloudflare R2) |
| Groq Whisper | Speech-to-text | Not set up |
| LLM API | Turn transcript into a structured quote | Not chosen (PRD open question) |
| Polar | Checkout, subscriptions, UK VAT as merchant of record | Not set up |

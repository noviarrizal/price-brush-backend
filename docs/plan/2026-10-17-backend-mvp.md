# Plan — backend MVP (stub: first task only)

Date: 17/10/2026 · Owner: pricebrush-lead · Repo: `price-brush-backend` · Status: **stub.** It holds the first backend task, moved here from the frontend launch plan. The full MVP backend plan (AI proxy, auth, Neon, Polar webhook, limits, public quote links, export/delete) comes later, after the MVP system design. That design must settle the auth provider and file storage first (role brief; Neon has neither).

Why this file exists: CEO memo `price-brush-frontend/docs/ceo/decisions-2026-10-18.md` P4, accepted in `price-brush-frontend/docs/PRD.md` "Keputusan 18 Okt 2026" P4. **The event counter Worker is the first backend task, live by Sun 08/11/2026.** It was removed from `price-brush-frontend/docs/plan/2026-10-17-launch-31-oct.md` ("Out of scope").

## B1 · Anonymous event counter Worker · live Sun 08/11/2026 · about 3–4 h [estimate from 17/10, not yet broken down]

- **Goal:** count free-tool use for the PRD §9 target (≥ 500 tool uses by 31/12, counted from 08/11; 31/10–08/11 uses Web Analytics page views, PRD P4).
- **Events** (from `price-brush-frontend/docs/seo/measurement.md` "Anonymous event counter" and `price-brush-frontend/docs/specs/paint-calculator.md` §11): `calc_used`, `calc_room_added`, `mist_coat_on`, `quote_prefilled`, `pdf_downloaded`.
- **Contract (proposed in `measurement.md`, to be confirmed in a short system design before building):**
  - `POST /api/e` with the body `{ "n": "<event>", "p": "<path>" }`.
  - It stores only the event name, the page and the date, as daily counts.
  - **No IP, no user ID, no form contents, no cookies.**
- **Open choices for the design (not decided):**
  - storage: D1 or Workers Analytics Engine, against the current free-tier limits (check the official docs on the day);
  - where it's served: same origin through Pages, or a `*.workers.dev` host with CORS limited to our origins (this depends on the domain plan, L4 after 23/10);
  - an allow-list of event names and paths;
  - a rate limit, so the free tier can't be drained;
  - how the founder reads the counts (no dashboard needed).
- **Frontend part (small, November):** a `track(name)` helper using `navigator.sendBeacon`, called where spec §11 says. That task goes in the November frontend plan.
- **Order:**
  1. A short system design (`docs/system-design/`).
  2. The Workers project scaffold, with `wrangler` and Vitest using `@cloudflare/vitest-pool-workers`.
  3. B1.
  4. A review.
  5. The founder deploys.

  This is also the founder's first, low-risk Worker (CEO P4).

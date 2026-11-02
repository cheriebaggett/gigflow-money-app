# Repo notes for automated agents

## What this is
A single static page (`index.html`) — no build step, no package manager, no backend
(the README's `npm install` / `npm start` instructions are stale; there is no `package.json`).

## Running it (Base44 sandbox)
- `docker compose -f docker-compose.base44.yml up -d` — nginx serves the repo root on host port 3000.
- The repo is bind-mounted read-only, so edits to `index.html` are visible on refresh; there is no
  live-reload dev server, so call `reload_preview` after a change.
- `base44/nginx.conf` runs nginx workers as root because the sandbox checkout directory can be
  mode 0700 for root, which the default `nginx` user cannot traverse (symptom: 403 Forbidden).
- Health: `curl -sS -o /dev/null -w '%{http_code}' http://localhost:3000/` must print 200.
- Verify in the preview by loading `/` and asserting the "Gigflow Money App" heading and the three
  pricing/donation buttons render. The page is not a SPA, so `navigate('/')` reports a false
  "route did not render" error — assert against the already-loaded document instead.

## Known gap (not a setup problem)
The Buy / Subscribe / Donate buttons POST to `https://your-server.com/create-checkout-session`,
a placeholder that does not exist, and there is no server-side code in this repo. They also
reference Stripe price IDs that are not real. Making checkout work requires a backend that
creates Stripe Checkout sessions (secret key supplied as a Base44 secret) plus real price IDs.

# CH Patches on this fork

This is `jordankrueger/mazanoke-ch`, a CampaignHelp fork of [civilblur/mazanoke](https://github.com/civilblur/mazanoke). Served at https://tools.campaign.help/image/.

## What's different from upstream

- **Branding layer:** `ch-branding.css`, `ch-header.js`, `ch-footer.html`, `ch-logo.png` — a thin overlay injected into `index.html` via two added tags. Adds the CampaignHelp header + footer used across the tools site.
- **Absolute paths converted to relative:** `/manifest.json` → `./manifest.json`, `/service-worker.js` → `./service-worker.js` in `index.html`. Makes the build portable under any path prefix.

## What's NOT different

- Dockerfile is untouched — the upstream env-script + nginx setup works fine when Traefik strips the `/image` path prefix at the edge.
- nginx config is untouched.
- No upstream business logic was modified.

## Upstream sync

Sync workflow is the standard ch-patches branch pattern (Phase 5 of tools-site). Watch upstream `main` for changes to `index.html` (where CH tags are inserted) and `manifest.json`/`service-worker.js` references.

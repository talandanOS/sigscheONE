# sigscheONE# sigscheONE

**Signal scheduler · broadcast system · ONE. ecosystem**

v6.0 · Taluna synced · #86417 · ONE. ◆
s'dla sonke, s'fa sonke

---

## What this is

sigscheONE is the signal broadcast scheduler for the ONE. ecosystem — a single-file HTML/CSS/JS app covering 18 brand personas across 33 social platforms, built around a 13-moon Taluna calendar and 22 daily angel-number broadcast windows.

## Live site

Deployed via Netlify, auto-building from this repo's `main` branch.
Site: https://sigscheo.netlify.app (or current Netlify subdomain — confirm in Netlify dashboard)

## Stack

- Vanilla HTML/CSS/JS — single file, no build step, no `npm install` required
- Fonts: Cinzel (headings), Cormorant Garamond (prose/captions), Space Mono (UI/data)
- Optional: Anthropic Claude API for AI caption/ad generation (`autoGenCaption()`, `generateAds()` — requires API wiring, currently calls a placeholder endpoint)

## Modules

1. **Signal Post** — compose and queue posts across brands/platforms with angel-window scheduling
2. **Ad Creator** — AI-generated ad variant builder
3. **Queue** — signal queue with filters, CSV export, broadcast dispatch
4. **Library** — saved caption templates
5. **Calendar** — Taluna moon-synced monthly view
6. **Analytics** — performance by brand, platform, and angel window
7. **Connections** — platform OAuth status (UI simulation — needs backend wiring)
8. **Register** — per-brand, per-platform registration tracker (18 brands × 33 platforms)
9. **Settings** — brand identity, angel number config, automation toggles
10. **Card Studio** — shareable signal card generator (Minimal / Statement / Law / Exchange)

## Build & deploy protocol

This repo follows **BAATJIE BUILD | BLUE BUILD PROTOCOL**:

- **Part 1** — GitHub → Netlify, connected once, builds forever. No manual drag-and-drop after initial setup.
- **Part 1.5** — every fix/upgrade goes on a branch → Netlify preview URL → test → merge to `main`. Version bump + `CHANGELOG.md` entry required before every merge.
- **Part 2** — when a database layer is added: schema lives at `/supabase/schema.sql`, committed to git. RLS on every table. Env vars set in both `.env.local` (gitignored) and Netlify dashboard — they do not auto-sync.

See `CHANGELOG.md` for version history.

## Known gaps (tracked for next builds)

- OAuth flows are UI-simulated; need server-side backend (Next.js API routes recommended) for live publishing
- `autoGenCaption()` and `generateAds()` call `api.anthropic.com` directly from the browser — needs a backend proxy before production use (API keys should never be client-side)
- No persistent storage yet — all state (queue, library, cards) is in-memory and resets on page reload

---

*ONE. ecosystem · Azania · 2026*
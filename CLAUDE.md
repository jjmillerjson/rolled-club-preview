# Rolled Club Card — Customer App

Customer-facing React PWA for the Rolled digital loyalty platform. Stamp collection, rewards, QR codes, and wallet pass integration.

## Architecture
- **Repo:** `jjmillerjson/rolled-frontend`
- **Hosting:** Netlify → `club.eatrolled.com`
- **Framework:** React PWA (single `index.html` + service worker)
- **Deploy:** Push to `main` → Netlify auto-deploys
- **Rollback:** Netlify → Deploys → click previous deploy → Publish
- **Backend:** `rolled-club-card-production.up.railway.app`

## What's Built
- Sign-up, login, email verification, forgot/reset password
- Stamp card display, QR code for scanning, loyalty history
- Privacy policy, source attribution
- Service worker with cache busting (`?v=${Date.now()}` on SW registration)

## What's Next
- Visual polish, animations, Add to Wallet prep (Phase 3c)
- Apple Wallet and Google Wallet integration (Phase 4)
- Admin dashboard (Phase 5)
- Tiered loyalty, special edition cards, gift cards (Phases 6-8)

## Style
- Colours: Nori `#00392C`, Wasabi `#D4FB6F`, Kewpie `#FEFAF0`
- Fonts: Gelica (Adobe Fonts `htl2spk`) for titles, Manrope (Google Fonts, standing in for Graphik) for body
- Stamp icons: soy sauce fish
- Tone: Australian, casual, fun. "Welcome to the Club, mate!"

## Rules
- **Check backend routes before writing fetch calls** — the #1 bug source
- **Frontend edit pattern:** Fresh clone → targeted changes → verify components/references/declaration order/no duplicates → push → check browser before telling JJ to test
- **Never use incremental sed on index.html for complex changes** — use an Agent with explicit verification checklist
- **After every Agent edit, verify:** all function definitions present, all component refs resolve, no temporal dead zone, no duplicate functions
- No API keys in frontend code
- No destructive commands without explicit confirmation
- Commit messages in plain English

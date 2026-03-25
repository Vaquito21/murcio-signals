# PolyOmega Landing Page — CLAUDE.md

## What this is
Landing page for PolyOmega (formerly Murcio Signals) — a Polymarket algorithmic trading signal service. Static HTML deployed on Vercel, connected to polyomega.com.

## Files
- `index.html` — entire site, single file, 893 lines
- No build step, no framework — pure HTML/CSS/JS

## Deploy
- GitHub repo: https://github.com/MortyC21/murcio-signals
- Vercel project: murcio-signals (mortyc21's projects)
- Domain: polyomega.com (purchased on Cloudflare)
- To deploy: git add . && git commit -m "..." && git push

## Live stats integration
- Bot (murcio_bot.go) pushes JSON to GitHub Gist every 5 minutes
- Landing page fetches from Gist every 5 minutes via JS
- Gist URL: https://gist.githubusercontent.com/MortyC21/464eb4fe8440192b9d814b74734cc5f4/raw/murcio-stats.json
- GIST_URL constant is set in index.html around line 812

## JSON fields the page expects (from bot)
- win_rate, net_pnl, total_trades, winning_trades, losing_trades
- last_updated (RFC3339), recent_trades[] (ts, coin, tf, side, outcome, pnl)

## Pending placeholders in index.html
- `INVITE_LINK` — Discord server invite URL (footer + nav button)
- `PLACEHOLDER_BASIC` — crypto payment link for $49/mo Basic plan
- `PLACEHOLDER_PRO` — crypto payment link for $99/mo Pro plan
- Payment processor: Coinbase Commerce (crypto, not Stripe)

## Branding
- Public name: PolyOmega
- Internal bot name: Murcio (never shown publicly)
- Tagline: "The bot that beats Polymarket"
- Color scheme: dark (#060608 bg), green (#00ff88 accent), JetBrains Mono + Inter fonts
- Language: English (international audience)

## Pricing
- Basic: $49/mo — signals only
- Pro: $99/mo — signals + direct bot access
- Payments: crypto (USDC preferred via Coinbase Commerce)

## Related
- Bot: C:\Users\Sebastian\Desktop\murcio\murcio_bot.go
- Monchichi bot: C:\Users\Sebastian\Desktop\monchichi\

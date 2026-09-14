# AGENTS.md

**Security and reliability are paramount.** Prefer a correct, boring change over a clever one. Do not invent backends, credentials, tracking, or third-party services.

## Template

- **Name:** Column
- **Catalog id:** `column`
- **Repository:** `https://github.com/Little-Devs/template-column`
- **Demo:** `https://column.little.website/`
- **Stack:** Static HTML · hand CSS · `js/boot.js` · `js/motion.js` · Google Fonts Syne + Atkinson Hyperlegible
- **Catalog:** https://github.com/Little-Devs/web-templates (`templates.json`)

## Agent / LLM setup

1. Read `README.md`, `template.json`, this file, `PROMPT.md`, and `MOTION.md`.
2. Discover tokens from `site.css` `:root` — do not restyle from memory.
3. Keep static HTML/CSS; no framework unless the task explicitly migrates.
4. Work in small diffs. Match local naming and formatting.
5. Verify by serving the folder root. There is no build step.
6. Never commit secrets, `.env` files, or API keys.

## Security and reliability

- No secrets in source or docs.
- No new analytics, pixels, or third-party scripts without an explicit request.
- Forms/CTAs stay `mailto:hello@column.example` unless asked otherwise.
- Preserve `_headers` (HSTS, CSP, frame-ancestors for little.website, no X-Frame-Options, no ACAO *).
- Put JS in `/js/*.js` only — CSP `script-src 'self'` forbids inline scripts.
- Self-host photos under `/images/` — CSP `img-src 'self'` forbids remote images.
- Respect `prefers-reduced-motion` (MOTION.md intensity 5).

## Design tokens

| Token | Value | Notes |
|-------|-------|-------|
| `--ledger` | `#F7F4EF` | Ledger |
| `--ink` | `#141210` | Ink |
| `--green` | `#1F6B4A` | Green |
| `--grid` | `#D9D2C5` | Grid |
| `--accent` | `#2F5D9F` | Accent |
| Display / body | Syne + Atkinson Hyperlegible | Never Inter/Roboto/Arial/Space Grotesk |

## Copy rules

Intentional fake brand **Column**. Thesis: **Books that stay balanced.** Mailto `hello@column.example` only. No Buy. No checkout. No CMS. No auth.

## Deploy

Cloudflare Pages Direct Upload (`lw-demo-column`). Oppy maps `column.little.website`. Screenshot before listing.

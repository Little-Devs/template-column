# PROMPT.md — Column

Reproduce this site without locking to a provider or framework.

## Goal

A single-page accounting landing for the staged demo brand **Column**. Thesis: **Books that stay balanced.** Intensity 5 (see MOTION.md).

## Brand / copy rules

- Brand wordmark: **Column**
- Hero thesis: **Books that stay balanced.**
- CTAs: `mailto:hello@column.example` only — label "Start a conversation"
- No Buy, no analytics, no invented backends

## Tokens

| Ledger | `#F7F4EF` |
| Ink | `#141210` |
| Green | `#1F6B4A` |
| Grid | `#D9D2C5` |
| Accent | `#2F5D9F` |

Type: Syne display + Atkinson Hyperlegible body.

## Sections (order)

1. Sticky nav
2. Hero + ledger photo
3. Services (BAS/payroll/year-end)
4. Monthly rhythm band
5. Fee note
6. Closing CTA
7. Footer

## Quality

Skip link, one h1, focus-visible rings, prefers-reduced-motion, mobile @375. Steve Pages `_headers` (HSTS, CSP with little.website frame-ancestors, no XFO, no ACAO *). Put JS in `/js/` — no inline `<script>` blocks. Google Fonts CSS link OK unless `/fonts/` is already self-hosted. Self-host Pixabay photos under `/images/`.

## Deliver

Static files at site root: `index.html`, `site.css`, `js/*` (if needed), `images/*`, `_headers`, `favicon.svg`, `preview.png`, `MOTION.md`, `AGENTS.md`, `PROMPT.md`, `template.json`, `LICENSE`, `README.md`.

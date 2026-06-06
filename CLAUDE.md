# Miss Floss landing (Dogra white-label)

Single-page static landing for **Miss Floss**, the AI receptionist for Canadian dental clinics. White-labelled fork of the RapidX AI Voice / Dograh OSS landing.

## Structure

- `index.html` — full landing (~1700 lines, single file, inline CSS + JS)
- `signup.html` — 14-day trial signup form (mailto submit, no backend)
- `assets/` — hero-bg, service-img, pricing-img, Inter woff2
- `netlify.toml` — redirects `/app` → `/signup`, `/login` → `/signup`
- `.env.example` — placeholders for the eventual voice stack (Supabase, Gemini Live, Vobiz)

## Brand tokens (live in `:root` of `index.html`)

| Token | Value |
|---|---|
| `--bg` | `#0A1828` deep navy |
| `--accent` | `#0F766E` teal |
| `--accent-light` | `#5EEAD4` bright teal |
| `--text` | `#E8F4F8` soft cyan-white |

Type: `Instrument Serif` for headlines, `Inter` for body.

## Deploying

```bash
# Local check
python3 -m http.server 8000  # then visit localhost:8000

# Netlify (linked once)
netlify deploy --prod
```

## Linked services

- **Supabase project:** `DograMissfloss` (`uazwppofnntmdwqoqyuf`, ap-south-1) — schema not yet migrated; only relevant once the voice backend deploys
- **Voice stack:** lives in `~/Downloads/Claude Projects/Doghra/` (Dograh fork, `rapidx-rebrand` branch). This landing is the marketing layer only.

## Source provenance

- Landing copied from `~/Downloads/Claude Projects/Doghra/landing/` then rebranded:
  - Palette: purple `#8258F2` → teal `#0F766E`
  - Strings: `RapidX AI Voice` → `Miss Floss`
  - Copy: B2B SaaS → Canadian dental clinic ICP (PMS integrations, recall, insurance, PHIPA/PIPEDA)
  - 4 pricing tiers in CAD (Reception $399, Pro $699, Billing $299 add-on, Multi-Location custom)

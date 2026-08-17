# Daily Chat with Chloe — website (`site/`)

Static bilingual site, chat-first design (see /DESIGN.md). **Only this `site/` folder gets deployed**; other repository folders stay private.

## Status
Chat-first redesign + native-Vietnamese copy rewrite in place. The staging `noindex` meta stays on all three HTML pages until launch.

## Design system
Hand-written CSS at `assets/styles.css` (no Tailwind, no build step — committed file is served as-is by Cloudflare Workers static assets). Fonts: Bricolage Grotesque (display) + Be Vietnam Pro (body), both with Vietnamese subsets. Tokens and rules live in /DESIGN.md.

## Pages
- `index.html` — Vietnamese primary landing page
- `index.en.html` — English mirror (identical markup/classes; only text differs)
- `terms.html` — T&C draft

**Sync rule:** any structural/markup change must land in BOTH index files in the same commit. Check parity with:
`diff <(grep -o 'class="[^"]*"' index.html) <(grep -o 'class="[^"]*"' index.en.html)` → should be empty.
(Known intentional exception: the `.on` class in the EN|VI language switcher sits on a different anchor per page.)

## Before launch — replace placeholders (search `REPLACE_`)
| Token | What |
|---|---|
| `REPLACE_ZALO` | Zalo link / phone (nav, hero, work, enquiry, sticky bar) |
| `REPLACE_TIKTOK` / `REPLACE_FACEBOOK` / `REPLACE_INSTAGRAM` | Social URLs (footer) |
| `REPLACE_FORMSPREE` | Formspree endpoint (enquiry form) |
| og-image v2 | v1 (brand-only) ships at `assets/og-image.png`; swap in a photo version at launch |

Placeholder links carry the `.draft` class (no visual effect now); remove it as each is finalized. Also remove the `noindex` meta at launch. Photos, logo and testimonials are real as of rev 9 (assets/chloe*.jpg, student-*.jpg, logo-*.png).

## Local preview
`cd site && python3 -m http.server 8787` → http://localhost:8787 (or the repo's `.claude/launch.json` "site" config).

## Deploy
Cloudflare Workers static assets via `wrangler.jsonc` (repo root) — serves `./site` as-is on push to main. No build step.

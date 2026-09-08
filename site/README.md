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

## Contacts: ALL REAL as of 2026-08-21 (no `REPLACE_` tokens remain)
Zalo = `https://zalo.me/0376427464` (5 CTAs per index file), form = Formspree `f/mrpzjoyy` (submissions land in the owner's Formspree dashboard + email), TikTok `@dailychatwchloe`, Instagram, Facebook. og-image is v2 with the owner's photo.

## Domain + launch state (2026-09-08)
Production domain **dailychatwithchloe.com** is attached to the `english-with-chloe` Worker as a Custom Domain (her Cloudflare account). `www` = proxied A 192.0.2.0 + Redirect Rule to apex. All canonical/hreflang/OG/JSON-LD/robots/sitemap URLs use the production domain. `workers_dev: true` is kept during transition; set to `false` after launch. GitHub Pages artifacts (root CNAME/index stubs) removed; the owner (repo admin) must also disable Pages in GitHub Settings.

Remaining: 1) owner disables GitHub Pages; 2) launch switch = remove the 3 `noindex` metas (index.html, index.en.html, terms.html) on owner approval; 3) Google Search Console (Domain property, TXT in her DNS) + submit /sitemap.xml; 4) then `workers_dev: false`.

## Local preview
`cd site && python3 -m http.server 8787` → http://localhost:8787 (or the repo's `.claude/launch.json` "site" config).

## Deploy
Cloudflare Workers static assets via `wrangler.jsonc` (repo root) — serves `./site` as-is on push to main. No build step.

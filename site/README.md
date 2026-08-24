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

## Remaining launch steps (blocked on domain purchase: dailychatwithchloe.com, confirmed available)
1. Owner buys the domain in her Cloudflare account and attaches it to the worker.
2. Swap staging host in all files: `git grep -n 'english-with-chloe.serenetravel-vietnam.workers.dev' -- site` (31 occurrences: canonicals, hreflang, OG, JSON-LD, robots.txt, sitemap.xml).
3. Remove the 3 `noindex` metas (index.html, index.en.html, terms.html).
4. Google Search Console: add property, submit sitemap, request indexing.


## Local preview
`cd site && python3 -m http.server 8787` → http://localhost:8787 (or the repo's `.claude/launch.json` "site" config).

## Deploy
Cloudflare Workers static assets via `wrangler.jsonc` (repo root) — serves `./site` as-is on push to main. No build step.

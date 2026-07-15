# English with Chloe — website (`site/`)

Static site skeleton. **Only this `site/` folder gets deployed** — `research/` stays private (pricing + competitor playbook).

## Status
Phase-2 SKELETON. All copy is DRAFT, pending the one-week validation in `../research/DEEP-DIVE.md §4`.

## Before launch — replace placeholders (search `REPLACE_`)
| Token | What |
|---|---|
| `REPLACE_ZALO` | Zalo link / phone |
| `REPLACE_TIKTOK` | TikTok profile URL |
| `REPLACE_FACEBOOK` | Facebook page URL |
| `REPLACE_FORMSPREE` | Formspree endpoint (`https://formspree.io/f/xxxx`) |
| `REPLACE_PHOTO` | Chloe's photo (hero + about) — on camera |
| `REPLACE_TESTIMONIAL` | Flight-attendant student quote + name (with consent) |
| `[confirm]` | Prices/dates — lock after mystery-shop |

Draft/placeholder blocks are outlined with a dashed amber border (`.draft` class) — remove the class as each is finalized.

## Pages
- `index.html` — **Vietnamese (primary / landing page)** · EN/VI switcher in the nav
- `index.en.html` — English (secondary)
- `terms.html` — T&C draft

Vietnamese is the landing page (market-facing; the Newbie audience has low English).

## Still pending
- **Copy:** rewrite hero/about/offer in both languages with **real customer wording** — draft wording bank is in `../research/PRICING-RESEARCH.md §3`.
- **Sprint price** (~6,900,000đ) is market-researched (see PRICING-RESEARCH.md) — confirm after mystery-shopping Inspired Academy / Sivila directly.
- Keep EN and VI in sync when editing.

## Local preview
Open `index.html` in a browser, or: `cd site && python3 -m http.server 8000` → http://localhost:8000

## Deploy (Cloudflare Pages, same stack as Serene)
- Framework preset: **None** · Build command: *(none)* · Output directory: **`site`**
- Skeleton loads Tailwind via Play CDN for speed. For production, switch to a Tailwind build step (smaller, no CDN dependency).

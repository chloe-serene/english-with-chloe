# Daily Chat with Chloe — website (`site/`)

Static bilingual site. **Only this `site/` folder gets deployed**; other repository folders stay private.

## Status

The rebrand and approved site structure are in place. The staging `noindex` meta tag remains on all three HTML pages and must only be removed at launch.

## Before launch — replace placeholders

| Token | What |
|---|---|
| `REPLACE_ZALO` | Zalo link / phone |
| `REPLACE_TIKTOK` | TikTok profile URL |
| `REPLACE_FACEBOOK` | Facebook page URL |
| `REPLACE_FORMSPREE` | Formspree endpoint |
| `REPLACE_PHOTO` | Chloe's photo (hero + about) |
| `REPLACE_TESTIMONIAL_1` | Learner quote 1 + name/goal |
| `REPLACE_TESTIMONIAL_2` | Learner quote 2 + name/goal |
| `REPLACE_TESTIMONIAL_3` | Learner quote 3 + name/goal |
| `TODO REPLACE_OG_IMAGE` | Add a 1200×630 `og-image.jpg` and its meta tag at launch |

Placeholder blocks use the dashed amber `.draft` outline. It is reserved for photo blocks, testimonial cards, and contact links/forms.

## Pages

- `index.html` — Vietnamese primary landing page
- `index.en.html` — English landing page
- `terms.html` — terms and conditions draft

Both landing pages cover Daily Conversation English and English for Work & Interviews. Cabin-crew coaching is an optional specialization under Work & Interviews, not a standalone product.

## Pricing summary

- 1-on-1: from 250,000đ per lesson, sold in 10-lesson packages
- Group of maximum 4: 5,500,000đ per 30-lesson course
- Interview coaching (1-on-1): from 4,900,000đ, depending on level

## Local preview

Open `index.html` in a browser, or run `cd site && python3 -m http.server 8000`, then visit http://localhost:8000.

## Deploy

Cloudflare Pages: framework preset **None**, no build command, output directory `site`. The site uses the Tailwind Play CDN and Plus Jakarta Sans.

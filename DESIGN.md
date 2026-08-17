# DESIGN.md — Daily Chat with Chloe

Committed visual world (2026-07-31, user-pinned "Chat-first" direction). This replaces the discarded navy/amber Tailwind-template look. Applies to `site/` (VI + EN mirrors + terms).

## World
The site behaves like opening a message thread with a teacher-friend. The conversation is the interface: proof, levels, FAQ, and testimonials all speak in chat grammar (bubbles, replies, typing). Not an app mockup cosplay — a page that borrows messaging's warmth and immediacy.

## Color — strategy: Committed emerald, "EatPing" palette (rev 4; owner-pinned reference eatping.com; supersedes rev 1 cream, rev 2 mint/rose, rev 3 navy/orange)
Deep emerald owns whole regions (hero + enquiry bands); blush off-white reading ground; dark red on conversion controls only (WHITE text, 10:1); peach as warm tint accents. Sourced from eatping.com inline styles: #014B3F emerald, #8B0000 red, #FFBC99 peach, #FCF7F5/#FBEFEA grounds. Display Archivo 700/800; body Be Vietnam Pro.

```
--ink        #2E3B3A   dark slate-green (text; footer/guarantee bg)
--cream      #FCF7F5   blush off-white ground (EatPing)
--cream-deep #FBEFEA   blush band (EatPing)
--surface    #FFFFFF   cards (1px #EADFD8 border)
--teal-900   #014B3F   hero/enquiry band (EatPing emerald)
--teal-700   #01614F   links (7:1 on ground)
--teal-600   #0A5D4C   secondary buttons w/ white text
--teal-100   #D9EBE2   learner bubbles / tints
--teal-050   #EDF5F0   quiet panels
--coral-500  #8B0000   PRIMARY CTA (EatPing dark red) - WHITE text (10:1)
--coral-600  #6E0000   hover; small red text on white
--coral-100  #FBD3C0   peach tint rows (EatPing peach family)
--zalo       #0068FF   Zalo buttons only
--line       #EADFD8   warm hairlines/borders
Peach #FFBC99: hot-price-card checkmarks + footer glyph (emerald+peach = signature pairing).
On emerald #014B3F: text #F7FBF9; secondary #B9D4C9.
```

## Copy style (owner-mandated)
NO em-dashes anywhere (reads as AI); use commas, colons, periods. Titles use "|" as brand separator. No fake-presence claims ("online now"); availability statements must be truthful ("Thường phản hồi trong 1 giờ").

## Type
- Display: **Archivo** 700/800 — h1/h2 + big prices only (scarcity = identity). VN subset verified. (Bricolage Grotesque retired rev 3: too playful for the professional audience.)
- Body/UI: **Be Vietnam Pro** 400/500/600/700.
- Rules: heading line-height ≥1.22 (VN diacritics); `.06–.1em` top headroom on display sizes; NO uppercase on Vietnamese display text; `text-wrap: balance` headings; body measure ≤ 70ch; tracking never below -0.02em (diacritics).

## Component grammar
- `.bubble` family is the signature: `--in` (white/surface, left tail, from Chloe), `--out` (teal-100, right tail, from learner), tails are CSS corner-radius cuts (border-bottom-*-radius: 6px), radius 18px, padding 10px 14px.
- Section kickers = small in-bubble label (NOT tracked-uppercase eyebrows).
- Chat windows (`.chat-card`): white, 22px radius, header row (avatar/name/online dot), soft offset shadow `0 10px 30px -12px rgb(34 32 27 / .18)`.
- Buttons: pill radius; coral+ink = primary; teal-600+white = secondary; ghost = 1.5px ink/tealborder. 16px text min.
- NO uniform icon-card grids; no gradient text; no decorative glass; no >1px colored side-borders; shadows always offset+blur.
- `.draft` placeholder skin: 1.5px dashed coral at 55% alpha, offset 3px.

## Motion (one authored moment)
The typing indicator in the hero chat (3-dot pulse) + chat bubbles in hero pop in staggered once on load (240ms, exponential ease-out, from visible 0.4 opacity — content readable without JS/motion). Everything else static. `prefers-reduced-motion: reduce` kills both.

## Layout rhythm
Bands: teal-900 hero → cream → cream-deep → … → ink guarantee moment → … → teal-900 enquiry → ink footer. Varying section padding (72–120px desktop, 56–80px mobile); no border-y separators; density varies (trust strip tight, pricing roomy). Mobile-first at 375px; sticky bottom CTA bar (Zalo blue + coral) with safe-area inset, hidden while #enquiry visible (IntersectionObserver, progressive).

## Files
`site/assets/styles.css` is the single stylesheet (hand-written, committed; no Tailwind). VI/EN pages share identical markup/classes — text nodes differ only. Frozen: SEO scaffolding, section ids, REPLACE_* tokens, form field names.

## Rev 8 (2026-08-13) — Preply-style softening (owner round-8 feedback)
Layout unchanged; restyle only. Display font Archivo → Bricolage Grotesque (soft, VN subset; same face VUS uses), sentence case everywhere (kicker now "Daily Chat."). Ground lightened #FCF8E8 → #FFFDF8; hero band pale Baby Blue #EFF6FF; deep bands pale Buttercream #FBF8E9. Buttons: 12px radius, no uppercase/letter-spacing, weight 600; secondary = Baby Blue pastel + ink (Preply pattern). Citrus reserved for primary CTAs only — header and sticky bar are now light with hairlines; schedule header and hot price card use pale Buttercream. All 2px ink rules → 1px hairlines (--line #ECE7DB / --line-strong #CFC9BB); shadows removed. Reference DNA probed live from preply.com and english.vus.edu.vn.

## Rev 9 (2026-08-17) — owner's Word-doc corrections + real logo, photos, palette
Owner supplied: script logo (navy on warm white; assets/logo-navy-640.png, logo-cream-640.png), her photo (assets/chloe.jpg + chloe-sq.jpg), two student photos, two verbatim testimonials, a mood board (warm off-white / orange / black / sea blue) and a "Meet Desi" poster reference.
Palette now: ground #F6F4F1 (logo bg), sea navy #0F3473 (logo) for headings/links/lang toggle, orange #F45305 (mood board) as the single accent (kicker dots, hero highlight, "Meet" script, quote glyphs, claim numerals), --orange-ui #CF4403 for filled surfaces with white text (AA 4.69:1), ink #1B1B1B. Tints: pale blue #E9EFF8 hero band, #DCE6F5 chips/secondary buttons, warm #EFEBE4 deep bands. Still: no dark backgrounds, no shadows, hairlines, 12px buttons, Bricolage display.
Structure: demo-chat section removed, replaced by owner's 90%/4-week claim band (light, navy text, orange numerals). Hero photo = "Meet Chloe" figure (giant pale "Chloe" behind arch-cropped photo, orange script "Meet"). Trust strip = 2x2 grid on phones (no swipe). Schedule table = stacked cards under 640px via data-l labels (no swipe). Testimonials = two colour cards with round photos (pale-blue + orange). Levels renamed Newbie/Breaker/Speaker; sample-sentence bubbles removed. NO free-trial mentions anywhere (level test only); all CTAs "Nhận tư vấn ngay". Refund copy = owner's 50% flexible policy (also synced into terms.html). Footer: Terms link removed, Instagram added (REPLACE_INSTAGRAM). About uses new verbatim profile paragraph.

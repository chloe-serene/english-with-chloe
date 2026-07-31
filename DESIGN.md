# DESIGN.md — Daily Chat with Chloe

Committed visual world (2026-07-31, user-pinned "Chat-first" direction). This replaces the discarded navy/amber Tailwind-template look. Applies to `site/` (VI + EN mirrors + terms).

## World
The site behaves like opening a message thread with a teacher-friend. The conversation is the interface: proof, levels, FAQ, and testimonials all speak in chat grammar (bubbles, replies, typing). Not an app mockup cosplay — a page that borrows messaging's warmth and immediacy.

## Color — strategy: Committed teal, "Fresh & modern" skin (rev 2, owner rejected cream as "countryside")
Deep pine-teal owns whole regions (hero + enquiry bands); crisp WHITE is the reading ground with cool mint-gray bands between; vivid rose appears ONLY on conversion controls. Never cream/earth tones (owner veto). Never navy. Secondary text on colored surfaces is hue-tinted, not gray.

```
--ink        #171B21   cool near-black (text on light; dark panels/footer bg)
--cream      #FFFFFF   reading ground (var name legacy; value is white)
--cream-deep #F2F7F6   alternating cool band
--surface    #FFFFFF   cards, chat windows (1px #E3E9E8 border for crispness on white)
--teal-900   #0A3F3C   hero/enquiry band bg (deep pine)
--teal-700   #0B7A6B   links/accents on white
--teal-600   #0C7268   buttons w/ white text (AA)
--teal-100   #D7F0EA   tints, outgoing "learner" bubbles
--teal-050   #EAF4F1   quiet tint panels
--coral-500  #FF4D6D   PRIMARY CTA fill (vivid rose) — ALWAYS ink text (white fails AA)
--coral-600  #D6335A   hover; small rose text on white (AA)
--coral-100  #FFE4EA   tint rows
--zalo       #0068FF   Zalo buttons only, white text
--line       #E3E9E8   hairlines + card borders
On teal-900: text #F2F7F5; secondary #B5D3CC.
```

## Copy style (owner-mandated)
NO em-dashes anywhere (reads as AI); use commas, colons, periods. Titles use "|" as brand separator. No fake-presence claims ("online now"); availability statements must be truthful ("Thường phản hồi trong 1 giờ").

## Type
- Display: **Bricolage Grotesque** 600/700/800 — h1/h2 + big prices only (scarcity = identity). VN subset verified.
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

# DESIGN.md — Daily Chat with Chloe

Committed visual world (2026-07-31, user-pinned "Chat-first" direction). This replaces the discarded navy/amber Tailwind-template look. Applies to `site/` (VI + EN mirrors + terms).

## World
The site behaves like opening a message thread with a teacher-friend. The conversation is the interface: proof, levels, FAQ, and testimonials all speak in chat grammar (bubbles, replies, typing). Not an app mockup cosplay — a page that borrows messaging's warmth and immediacy.

## Color — strategy: Committed navy, "Executive Navy + Burnt Orange" (rev 3; owner rejected cream="countryside" and mint/rose="student-y"; reference market = navy+warm accent)
Deep navy owns whole regions (hero + enquiry bands); crisp WHITE reading ground with cool gray-blue bands; burnt orange appears ONLY on conversion controls (carries WHITE text, 4.74:1). Never cream/earth pastels or mint/rose (owner vetoes). Display font is Archivo 700/800 (Bricolage retired as too playful); body stays Be Vietnam Pro.

```
--ink        #172033   cool navy-black (text; dark panels/footer bg)
--cream      #FFFFFF   reading ground (legacy var name)
--cream-deep #F4F6F8   alternating band
--surface    #FFFFFF   cards (1px #D9E1E8 border)
--teal-900   #17324D   hero/enquiry band (executive navy)
--teal-700   #244C6A   links on white
--teal-600   #2B5D7B   secondary buttons w/ white text (7.1:1)
--teal-100   #DDE8F0   learner bubbles / tints
--teal-050   #EEF3F7   quiet panels
--coral-500  #C9481D   PRIMARY CTA (burnt orange) - WHITE text (4.74:1)
--coral-600  #A93817   hover; small orange text on white (6.4:1)
--coral-100  #FBE7DE   tint rows
--zalo       #0068FF   Zalo buttons only
--line       #D9E1E8   hairlines/borders
On navy #17324D: text #F7FAFC; secondary #C6D3DE.
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

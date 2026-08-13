# PRODUCT.md — Daily Chat with Chloe

Captured 2026-07-31 from owner decisions (see research/DECISIONS.md) and session history; not invented.

## What this is
Online conversational-English teaching by Chloe — a solo, native-level (lived and studied in Switzerland) female teacher. Vietnamese-first bilingual marketing site; the product is her lessons, sold via Zalo conversation.

## Audience
Vietnamese young professionals, 23–35, mobile-first, discovered via TikTok/Facebook reels, converting in Zalo. Secondary: job-interview candidates (any industry, incl. cabin crew).

## Offers & prices (owner-set, staging-confirmed)
- Daily Conversation English: 1-1 from 250.000đ/60-min lesson (10-lesson packs); groups of max 5, 5.500.000đ / 30 × 90-min lessons. Levels: L1 (A1), L2 (A2), L3 (A2+–B1). Free level test + free trial lesson.
- English for Work & Interviews: from 4.900.000đ (level-dependent, consult on Zalo), 1-1 only; airline options: Vietnam Airlines, Vietjet, Sun PhuQuoc Airways, Emirates, Qatar Airways, Cathay Pacific.
- Guarantees: interview students — free continued coaching until interview-ready; general — refund unused lessons after first pack. First-ever group: ~30% launch discount, once.
- Group schedule: Tue/Thu 20:00–21:30, Sat/Sun 9:30–11:00; cohort waitlist model.

## Brand voice (owner-mandated)
Name "Daily Chat with Chloe". Tagline concept: learn through real connection/conversations, NOT robotic scripts/textbooks ("không rập khuôn, không học vẹt"). Register: self = "Chloe"/"mình", reader = "bạn"; warm peer-teacher, never school-formal, never sticker-spam childish. Proof point: most recent student passed a cabin-crew interview first try.

## Conversion model
Primary action everywhere: message Chloe on Zalo (reply < 1 hour). Secondary: enquiry form (Formspree) with goal/format selects. Free trial is the hook. Mobile sticky CTA required.

## Hard constraints
- Static HTML + committed CSS only (Cloudflare Workers serves ./site as-is; no deploy-time build).
- Bilingual: index.html (VI, primary) mirrors index.en.html (EN); identical markup/classes, text differs.
- Placeholders pending: REPLACE_ZALO/TIKTOK/FACEBOOK/FORMSPREE/PHOTO, 3 testimonials (marked with .draft convention). Staging noindex stays until launch.
- SEO scaffolding frozen: hreflang, canonical, OG, JSON-LD (Org/Courses/FAQPage; FAQ text mirrors visible FAQ verbatim).
- Vietnamese diacritics must render safely at display sizes (fonts must ship VN subset).

## Platform
Web, mobile-first (375px is the primary viewport). Modes: this landing surface = Persuade.

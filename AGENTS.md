# Agent Rules — Daily Chat with Chloe

## Runtime roles

- **Codex is the primary hub:** plan work, edit the site, verify both language versions, manage GitHub, and inspect Cloudflare state.
- **Claude Code is a specialist:** use it only for a narrowly scoped implementation or review delegated by Codex. Codex must inspect the resulting diff and run the checks itself.
- **JJ and Chloe approve public copy, contact details, launch, and deployment.** Do not invent or silently replace owner decisions.

## Isolation and privacy

This repository is only for Chloe's English-teaching business. Do not read or copy material from JJ's restaurant, Candor, personal vault, or Serene Travel project unless JJ explicitly supplies it for this task.

The `research/` directory is private strategy. Never deploy or publish it. Cloudflare must serve only `site/`, as declared by `wrangler.jsonc`.

Never reveal credentials, form endpoints, private contact details, or environment values. Placeholder tokens are deliberate until the owner replaces them.

## Product and design sources

- Read `PRODUCT.md` before changing offers, prices, guarantees, positioning, or conversion flow.
- Read `DESIGN.md` before visual or copy changes.
- Read `site/README.md` before launch or deployment work.
- Vietnamese `site/index.html` and English `site/index.en.html` must keep matching structure and classes; only localized text and the active language state may differ.
- Preserve Vietnamese diacritics and the no-em-dash copy rule.

## Git, verification, and deployment

- Preserve unrelated working-tree changes. Do not commit or push unless the task explicitly includes publishing.
- A push to the deployment branch can trigger Cloudflare; treat it as a deployment action.
- Before reporting completion, check placeholder tokens, bilingual structural parity, mobile layout, links/forms, and the staging `noindex` state.
- Do not remove `noindex` or deploy publicly until the launch placeholders and owner approvals are complete.

## Connection map

- Repository: `chloe-serene/english-with-chloe` on GitHub.
- Hosting declaration: Cloudflare Worker/Pages static assets via `wrangler.jsonc`, script name `daily-chat-with-chloe`.
- No Vercel, Supabase, or PostHog dependency is currently declared by this project.

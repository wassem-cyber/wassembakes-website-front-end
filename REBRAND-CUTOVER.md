# Rebrand cutover checklist — Sensible Edibles → Sensible Bakery

This is the canonical source for **wassembakes.com** (Netlify, auto-deploys from `main`). The
personal creator brand **wassembakes** is unchanged; only the **business** brand references were
rebranded.

## Done in this branch (name text only)

- Business-brand text → **Sensible Bakery** across `index.html`, `about/index.html`,
  `links/index.html`, all ~44 `blog/*.html`, and the 3 skills
  (`.claude/skills/sensible-brand`, `blog-post`, `recipe`) + `CLAUDE.md`.
- Footer "You might also like → Sensible Bakery" text updated. The footer `href` was already
  `https://sensiblebakery.com` (a prior partial rebrand) — left as-is.

## Deferred to domain cutover (left as-is in code)

- **Shop / buy links** to `sensibleedibles.com` (~103 occurrences): the nav "Shop" link
  (`/collections/all`) on every page + product CTAs (`/products/<handle>`) in the homepage carousel
  (`index.html:1056–1072`), `about/index.html:209,228`, `links/index.html:204`, and the bottom CTA on
  most blog posts. These hit the Shopify storefront — flip to `sensiblebakery.com` once Shopify's
  primary domain is switched (the `/collections` and `/products/<handle>` paths stay the same).
- **Contact email** `info@sensibleedibles.com` — `index.html:1186` (`mailto:` + visible text).
- **Skill URL templates** that emit `sensibleedibles.com` shop links:
  `.claude/skills/blog-post/SKILL.md:75,101`, `.claude/skills/recipe/SKILL.md`. Flip these at cutover
  so newly generated posts use the new domain (the footer template already emits `sensiblebakery.com`).

## SEO — already clean
Canonical / `og:url` / `sitemap.xml` / `robots.txt` / JSON-LD are all on `wassembakes.com` — no
changes needed. The domain migration is `sensibleedibles.com` → `sensiblebakery.com` (the shop),
which does not affect this site's own SEO.

## ⚠️ Before merging to `main` (deploy caveat)
Per `CLAUDE.md`, a separate **Studio** app can publish posts straight to Netlify without touching git,
and "last deploy wins." Pull from prod first (the `_deploy.ps1` safety check) before merging this
branch, so the push can't overwrite Studio-only posts. Also apply the same brand-text swap in the
`wassembakes-app/site/` mirror (done on its own branch) so the two don't diverge.

## External steps (owner-only)
- Switch the Shopify store's **primary domain** to `sensiblebakery.com`; keep `sensibleedibles.com`
  as a 301 redirect during transition.
- Create `info@sensiblebakery.com`.

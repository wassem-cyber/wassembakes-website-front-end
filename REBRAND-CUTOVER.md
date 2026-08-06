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

## Done — domain flip (Shopify primary switched to sensiblebakery.com)

- **Shop / buy links** → `https://sensiblebakery.com` across every page, blog post, and the
  `blog-post` / `recipe` skill URL templates. The Shopify `/collections` and `/products/<handle>`
  paths are unchanged.

## Still deferred (waiting on Google Workspace)

- **Contact email** `info@sensibleedibles.com` — `index.html:1186` (`mailto:` + visible text).
  Flip to `info@sensiblebakery.com` once the address exists on the new domain (add `sensiblebakery.com`
  to Google Workspace as a domain alias/secondary — no new subscription needed).

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

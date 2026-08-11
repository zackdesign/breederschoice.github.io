# breederschoice.github.io

Jekyll site for Breeder's Choice Woodshavings, deployed to GitHub Pages by
`.github/workflows/jekyll.yml`.

## Two designs live in this repo

- **`/`** — the original site, rendered by `_layouts/default.html` and
  `index.md`. This is what the public sees. Do not break it.
- **`/preview/`** — the 2026 redesign (`_layouts/base|home|stockists.html`
  plus `_includes/`), noindexed and excluded from the sitemap so the client
  can review it live. Promoting it is a permalink change in `preview/*.md`.

Because both are built from one `_config.yml`, some keys exist only to keep
the old layout working and must not be renamed:

| Key | Read by |
| --- | --- |
| `title`, `description` | old layout via `{% seo %}` — keep byte-identical to production until the flip |
| `stockistscsv` | old layout's stockist finder (note: no underscore) |
| `phone_international` | old layout |

The redesign reads `brand_description` / `brand_tagline` / `stockists_csv`
instead, so editing those cannot affect the live pages.

## Stockists

The finder fetches the owner's Dropbox CSV in the browser at page load, so
stockist edits go live with no deploy. Do not move this to build time.
State pages (`/preview/stockists/vic/` etc.) exist so the list is indexable —
the old JS-only finder was invisible to search engines.

## Content notes

- Product range is the 14kg bale only. Wool-pack bales and Pet Flakes were
  discontinued (confirmed by Jarrod, Aug 2026), so `images/products.jpg` and
  `images/products2.jpg` are unused — they also carry the previous label art.
  `images/bale14.jpg` is a current-label crop of `images/bales.jpg`.
- Founded 1994; Superior Shavings taken on 2016; bale ~0.18 m³.
- Screening is described as "triple screened" (star screen → rotary trommel →
  airborne dust extraction), per Jarrod's own wording.
- Structured data uses `OfferCatalog`, never `Product`. Product entities
  require offers/review/aggregateRating, and these items have no published
  price — marking them up as Products caused Search Console errors.

Image provenance is documented in `images/site/README.md`.

# SingingNumbers website (`https://singingnumbers.app/`)

Static, dependency-free presentation of the app. Hostable on any static
file host (GitHub Pages, Netlify, Cloudflare Pages, plain Apache, …).

## Files

| File                       | Purpose                                                |
|----------------------------|--------------------------------------------------------|
| `index.html`               | Home page: tagline, features, screenshot gallery, default note table, privacy summary, requirements. |
| `privacy-policy.html`      | Public Privacy Policy. The URL referenced by Google Play Console. |
| `terms-of-service.html`    | Optional Terms of Service.                              |
| `style.css`                | Single stylesheet (light + dark via `prefers-color-scheme`). |
| `sitemap.xml`              | Sitemap for search engines.                             |
| `robots.txt`               | Allow-all.                                              |
| `llms.txt`                 | AI-optimised plain-text summary for LLM retrieval.      |
| `screenshots/`             | PNGs produced by `../ui/screenshots/capture-screenshots.ps1`. See `screenshots/README.md` for the expected filenames. |

## Cross-references (single source of truth: `.ai-agent/legal/`)

| HTML page                  | Source text                                            |
|----------------------------|--------------------------------------------------------|
| `privacy-policy.html`      | `../legal/privacy-policy.txt`                          |
| `terms-of-service.html`    | `../legal/terms-of-service.txt`                        |
| Hero + features in `index.html` | `../legal/store-listing.txt` (kept terminology-aligned) |

When any of those `.txt` files change in `.ai-agent/legal/`, the
corresponding HTML page **must** be updated to match.

## Cross-references (screenshots: `.ai-agent/ui/screenshots/`)

| HTML page                  | Image source                                           |
|----------------------------|--------------------------------------------------------|
| `index.html` (gallery)     | `screenshots/01-*.png` … `screenshots/10-*.png`        |

These are produced by running the `webpage` output format of the
screenshot tour and copied into `screenshots/` (see
`screenshots/README.md`).

## Hosting checklist

- [ ] Upload all files (preserve relative paths).
- [ ] Verify `https://singingnumbers.app/privacy-policy.html` returns HTTP 200.
- [ ] Verify `https://singingnumbers.app/terms-of-service.html` returns HTTP 200.
- [ ] Verify `https://singingnumbers.app/sitemap.xml` returns valid XML.
- [ ] Verify gallery images load and look correct on phone widths.
- [ ] Paste the privacy-policy URL into Google Play Console.

See `../CONTENT_MAP.md` for the full content graph across legal / website / playstore / screenshots.

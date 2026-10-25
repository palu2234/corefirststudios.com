# corefirststudios.com

The website for Core First Studios and OnTrack. GitHub Pages builds it with
Jekyll on every push to `main` and serves it at <https://corefirststudios.com>.

| Page | File | URL |
|---|---|---|
| Home | `index.html` | `/` |
| Support | `support.html` | `/support` |
| Privacy policy | `privacy.md` | `/privacy` |
| Not found | `404.html` | any missing page |

The header, footer and `<head>` are in `_layouts/default.html`. The privacy
page's layout, `_layouts/policy.html`, builds its "On this page" list from the
policy's `##` headings. Styles are in `assets/site.css`, and the fonts (Archivo
and JetBrains Mono, both SIL Open Font License) are served from `assets/fonts/`,
so the site makes no requests to other servers.

## Editing

- **Text on a page:** edit the file on GitHub (pencil icon) and commit. The site
  updates a minute or two later.
- **Privacy policy:** `privacy.md` is the same text as
  `play-store/privacy-policy.md` in the OnTrack-Android repo, below its front
  matter (the lines between the two `---`). When the policy changes, update
  both, the in-app Privacy screen, and the `ontrack-ios-privacy` README together.
- **Google Play link:** when the listing is live, replace the "Coming soon to
  Google Play" badge in `index.html` with a link to it.

To preview locally: `bundle exec jekyll serve` or `jekyll serve`, then open
<http://localhost:4000>.

## Hosting setup

- **GitHub:** Settings → Pages → Build and deployment → **Deploy from a branch**,
  `main`, `/ (root)`. Custom domain `corefirststudios.com` (also in `CNAME`),
  with **Enforce HTTPS** on.
- **DNS** (Squarespace Domains → corefirststudios.com → DNS):

  | Host | Type | Data |
  |---|---|---|
  | `@` | A | `185.199.108.153` |
  | `@` | A | `185.199.109.153` |
  | `@` | A | `185.199.110.153` |
  | `@` | A | `185.199.111.153` |
  | `@` | AAAA | `2606:50c0:8000::153` |
  | `@` | AAAA | `2606:50c0:8001::153` |
  | `@` | AAAA | `2606:50c0:8002::153` |
  | `@` | AAAA | `2606:50c0:8003::153` |
  | `www` | CNAME | `palu2234.github.io` |

  Keep the Google Workspace records (MX and TXT): they run
  `support@corefirststudios.com`. The `google-site-verification` TXT record
  keeps the domain verified in Search Console for Google Play.

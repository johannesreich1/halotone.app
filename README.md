# halotone.app

Halotone's website at https://halotone.app, served by GitHub Pages from `main` through
Cloudflare: the app's page, its support page (`/support/`), its privacy policy (`/privacy/`),
and its Community Rules (`/rules/`). The app's Support sheet, Share sheet, and App Store
listing link to these; the app opens each in the phone's language.

The support page, privacy policy and Community Rules are in all 23 app languages, one page per
language: English at `support/`, `privacy/` and `rules/`, the other 22 in `support/<lang>/`,
`privacy/<lang>/` and `rules/<lang>/`. All of them are generated: edit them in `docs/site-drafts/`
of the app's repository and run `build_pages.py`, not here. German was a part of the English
pages under `#deutsch` until 13 November 2026; app builds through 77 link there, so the English
pages send that anchor on to the German page with one line of script, the site's only script.

Plain HTML and one stylesheet, no build step. `/impressum/` is the legal notice German
law asks for, linked from every page. Support mail to support@halotone.app is forwarded to
reichjohannes@icloud.com.

DNS lives at Cloudflare since 6 November 2026. GitHub's A and AAAA records on the apex and
`www` as a CNAME to `johannesreich1.github.io` are proxied, with SSL/TLS set to Full. The IONOS
mail records and Resend's sending records are DNS only; mail itself stays at IONOS. The
`halotone` Worker answers `/s/*`, `/v1/*`, `/media/*`, `/admin*`, and the association file.

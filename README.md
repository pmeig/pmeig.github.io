# pmeig.github.io

Static pages of the **Budget** app, served by GitHub Pages on the standard HTTPS port (443). The Budget server itself is only
reachable on port 18443 (shared IPv4 of the box), and Android only verifies App Links on port 443.

| Path | What |
|---|---|
| `/cooking/join` | Mail link landing page of Cooking (password reset): on Android it redirects to Google Play, other devices see a page with the Google Play button (no token, no personal data in the URL) |
| `/budget/join?session=…&token=…` | Invitation relay: Android without the app goes to Google Play (the invitation travels in the `referrer`), iPhone and computers go to the web app (PWA) |
| `/.well-known/assetlinks.json` | Android App Links verification: the link opens the app directly when it is installed (SHA-256 of the app signing certificate) |
| `/budget/privacy.html` | Privacy policy (source of truth; it was removed from `web/public/` of pmeig/budget) |
| `/budget/delete-account.html` | Account deletion page (source of truth; it was removed from `web/public/` of pmeig/budget) |
| `/ac/join.html#code=…` | Invitation relay of AC: opens the web app with the code kept in the URL fragment; Windows devices also get a Microsoft Store button (added 2026-11-23, the link works once the app is published) |
| `/ac/confirmer-adresse#…`, `/ac/nouveau-mot-de-passe#…`, `/ac/repartir-de-zero#…` | Mail links of AC (address confirmation, password reset, restart): Android App Links open the app when it is installed; otherwise the page forwards the fragment unchanged to the same page of the AC server (no token in a query string, no secret here) |
| `/ac/privacy.html` | Privacy policy of AC (French then English; source of truth) |
| `/ac/delete-account.html` | Account deletion page of AC (French then English; source of truth) |

No secret here: the invitation token is only in the link that is shared, like before.

The privacy and account deletion pages are edited here only.

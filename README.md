# pmeig.github.io

Static pages of the **Budget** app, served by GitHub Pages on the standard HTTPS port (443). The Budget server itself is only
reachable on port 18443 (shared IPv4 of the box), and Android only verifies App Links on port 443.

| Path | What |
|---|---|
| `/budget/join?session=…&token=…` | Invitation relay: Android without the app goes to Google Play (the invitation travels in the `referrer`), iPhone and computers go to the web app (PWA) |
| `/.well-known/assetlinks.json` | Android App Links verification: the link opens the app directly when it is installed (SHA-256 of the app signing certificate) |
| `/budget/privacy.html` | Privacy policy (copy of `web/public/privacy.html` of pmeig/budget) |
| `/budget/delete-account.html` | Account deletion page (copy of `web/public/delete-account.html` of pmeig/budget) |

No secret here: the invitation token is only in the link that is shared, like before.

The two copies must follow `web/public/` in pmeig/budget.

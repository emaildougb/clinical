# NCEMS Clinical

Clinical reference page for North Country EMS crews. This used to be the Clinical tab on the NCEMS Hub. It got its own site in October 2026 (hub 2.0) so the hub could be just Operations.

**Version 1.0**

## Links

- Live: [https://clinical.northcountryems.org/](https://clinical.northcountryems.org/)
- Repo: [https://github.com/emaildougb/clinical](https://github.com/emaildougb/clinical)
- Upload: [https://github.com/emaildougb/clinical/upload/main](https://github.com/emaildougb/clinical/upload/main)
- Hub (the home button goes here): [https://hub.northcountryems.org/](https://hub.northcountryems.org/)

## Files (upload ALL of these)

- `index.html`: the page
- `apps.json`: the button list (edit this to add, remove or rename clinical apps)
- `logo.png`: NCEMS round logo (header)
- `apple-touch-icon.png`: home screen and tab icon
- `icon-512.png`: big icon for Android and the launch screen
- `manifest.json`: app mode settings (name "NCEMS Clinical")
- `CNAME`: tells GitHub Pages the address is clinical.northcountryems.org
- `README.md`: this file

## One time setup (Oct 2026)

1. On GitHub, make a new public repo named `clinical` under emaildougb
2. Upload every file in this folder
3. Repo Settings > Pages: Source "Deploy from a branch", branch `main`, folder `/ (root)`, Save
4. In GoDaddy DNS for northcountryems.org, add: Type `CNAME`, Name `clinical`, Value `emaildougb.github.io`, TTL 1 hour
5. Back in Settings > Pages, the custom domain should show clinical.northcountryems.org. Once the DNS check goes green (minutes to an hour), tick **Enforce HTTPS**
6. Open https://clinical.northcountryems.org/ and check the buttons work. Only then upload hub 2.0, because hub 2.0 removes the Clinical tab

## How it works

- No sign-in. Anyone can open it
- The yellow warning and the buttons come from `apps.json`. Phones keep the last good copy if it can't load, and the buttons built into `index.html` are the fallback
- The notice banner at the bottom is the same notice the hub shows (Doug's Cloudflare Worker). Notices are posted from the hub's (i) panel, not here
- The home button opens the NCEMS Hub
- Usage is counted in Firebase `usage/clinical` (same project as the hub)
- Bump `CLIN_VERSION` in `index.html` whenever you upload a new `index.html`. Open copies show a "New version available" bar

## Adding, removing or renaming a button (no index.html change)

1. Open `apps.json` and click the pencil
2. Copy an existing button and change `title` and `url`. `"soon": true` with no url makes a grey Coming Soon card. `"style": "dark"` is the darker green. `\n` in a title is a line break
3. Commit. Phones pick it up the next time the page opens

## Changelog

### v1.0
- New phone icon: NCEMS green and teal split corner to corner with a white Star of Life, NCEMS across the bottom (matches the Open Shifts icon). `apple-touch-icon.png` is the new icon and `icon-512.png` is the big one Android uses for the icon and the launch screen. Delete the old icon from the home screen and add it again to see it
- Split out of the NCEMS Hub (hub 2.0). Same clinical buttons, warning and notice banner as the old Clinical tab
- Header says NCEMS Clinical; the home button goes to the hub
- Own home screen name ("Clinical") so crews can save it next to the hub

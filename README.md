# orbita-data

The data the Orbita app reads, published here by scheduled jobs and served by
GitHub Pages at https://alexsxxx.github.io/orbita-data/. One file per feed;
the app asks this site, never the upstream archives per device.

| File | Job | Schedule | Source |
|---|---|---|---|
| `exoplanets.json.gz` | `exoplanets.yml` | weekly, Fridays 05:10 UTC | NASA Exoplanet Archive (`pscomppars`) |
| `light_curves.json.gz` | `light-curves.yml` | monthly, the 3rd, 06:30 UTC | TESS via MAST; ephemerides from the archive |

The generators live in the private Orbita repo (`tool/`). Each job checks
Orbita out with `ORBITA_READ_KEY` (a read-only deploy key there) and pushes
here with `PAGES_DEPLOY_KEY` (a write deploy key on this repo - a push by
GITHUB_TOKEN would not start the Pages build). The logs are public and carry
only what the published files already say. **No `pull_request` trigger,
ever**: it would hand the read key to a fork.

A job that cannot get good data fails without publishing; GitHub mails the
failure, and the app keeps the last good file.

Credits for the data are in each file's `source` field and in Orbita's
NOTICE.md.

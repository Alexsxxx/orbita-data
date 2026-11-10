# orbita-data

The data the Orbita app reads, published here by scheduled jobs and served by
GitHub Pages at https://orbita-data.kruen.app/ (the site's custom domain since
2026-11-10, a CNAME at Cloudflare; the old github.io address redirects). One file per feed;
the app asks this site, never the upstream archives per device.

| File | Job | Schedule | Source |
|---|---|---|---|
| `exoplanets.json.gz` | `exoplanets.yml` | weekly, Fridays 05:10 UTC | NASA Exoplanet Archive (`pscomppars`) |
| `exoplanets_new.json` | `exoplanets.yml` (after the catalogue) | weekly | the planets in this week's catalogue that were not in last week's, with the day first seen, 120 days kept (`tool/build_exoplanets_new.py`) |
| `neighbourhood.bin` | by hand, once per Gaia release (`tool/build_neighbourhood.py`) | - | ESA Gaia DR3 (DR4 from 2026-12-02), Hipparcos for the brightest |
| `neighbourhood-v2.bin` | by hand, once per Gaia release (`tool/build_neighbourhood.py`, format 2: with velocities) | - | ESA Gaia DR3, Hipparcos, Pulkovo and Soubiran et al. 2018 radial velocities; read by the app since the proper-motion clock. `neighbourhood.bin` (format 1) stays for builds already out |
| `neighbourhood-v3.bin` | by hand, once per Gaia release (`tool/build_neighbourhood.py`, format 3: naked-eye sky to Hp 7, open clusters from Hunt & Reffert 2023, IAU star names, links to the constellation lines) | - | as v2, plus Hunt & Reffert 2023 and the IAU WGSN list; read by the app since the landmarks. v1 and v2 stay for builds already out |
| `dust-v1.bin` | by hand, once (`tool/build_dust.py`) | - | Edenhofer et al. 2024 3D dust map (Zenodo 10658339, CC BY 4.0), 8 pc grid within 1.25 kpc; Zucker et al. 2020 clouds, Alves et al. 2020 Radcliffe Wave (CC0) |
| `light_curves.json.gz` | `light-curves.yml` | monthly, the 3rd, 06:30 UTC | TESS via MAST; ephemerides from the archive |
| `flybys.json` | `flybys.yml` | daily, 05:40 UTC | NASA/JPL: CNEOS close approaches within 10 lunar distances, Small-Body Database orbits, Horizons geocentric positions round each pass |
| `jwst.json` | `jwst.yml` | daily, 06:20 UTC | STScI JWST observing schedules (this week and next); target positions from MAST, else MAST's name resolver |
| `fireballs.json` | `fireballs.yml` | daily, 06:50 UTC | NASA/JPL CNEOS fireball data (bolides reported by US government sensors since 1988, with a place) |
| `radio.json.gz` | `radio.yml` | Tuesdays, 05:30 UTC | Internet radio stations from [Radio Browser](https://www.radio-browser.info) (public domain), placed by their own coordinates or, approximately, by the city or region they name, matched against [GeoNames](https://www.geonames.org) (CC BY 4.0) |
| `sky-v2.bin.gz` | `sky.yml` | daily, 05:20 UTC | Everything in Earth orbit with public elements, named - [CelesTrak](https://celestrak.org) GP data (active satellites and the Fengyun 1C, Iridium 33 and Cosmos 2251 debris clouds) |
| `sun-field.json.gz` | `sun-field.yml` | every 3 h, at :25 | The Sun's coronal field lines: [SDO/HMI](http://jsoc.stanford.edu)'s near-real-time synoptic magnetogram (NASA/SDO and the HMI science team), extended by a PFSS model and traced |

`privacy/` is the app's privacy policy, served at
https://orbita-data.kruen.app/privacy/ - the address given to the stores.
Its source is `PRIVACY.md` in Orbita; the page is rebuilt from it by
`tool/build_privacy_page.py` there, never edited here.

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

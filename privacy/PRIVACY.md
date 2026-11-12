# Privacy Policy — Orbita

_Last updated: 12 November 2026_

Orbita ("the app") is a space explorer: the Earth, the satellites over it,
the solar system and the galaxies, drawn from public scientific data. It is
published by **Kruen s.r.o.** This policy explains what data the app does
and does not handle.

The publisher, and the data controller for the purposes of the GDPR, is:

**Kruen s.r.o.**
K Hajku 1714, 509 01 Nova Paka, Czech Republic
Company ID (IČO): 09670157
info@kruen.cz

## We do not collect personal data

The app has **no accounts, no analytics, no advertising, and no tracking**.
The developer does not collect, store, or share any personal information
about you. What the app keeps on your device is your in-app settings (the
language, the layers you switched on, your favourite radio stations, where
you last were in the solar system, when your free trial began and whether
you bought the full version) and copies of files it has downloaded, so it
need not download them again. None of it leaves the device.

## Network connections

To draw what it shows, the app downloads public data. Every one of these is
an ordinary web request: the server at the other end sees your IP address,
as any website you visit does. No request carries an identifier of you or of
your device.

- **The developer's own data files** — satellite orbits, the exoplanet
  catalogue, the stars and dust round the Sun, asteroid flybys, fireballs,
  the Sun's magnetic field, the James Webb telescope's schedule and the
  directory of internet radio stations are downloaded from the developer's
  static site (`orbita-data.kruen.app`, hosted on GitHub Pages and served
  through Cloudflare). The three-dimensional nebulae are downloaded, the
  first time you fly to one, from the developer's file storage
  (`orbita-files.kruen.app`, Cloudflare R2). They are the same files for
  every user. The developer sees only Cloudflare's aggregate traffic
  statistics (such as the number of requests per day), not logs of
  individual visitors.
- **Earth imagery** — the satellite ground and the city lights download
  imagery tiles from NASA GIBS (`gibs.earthdata.nasa.gov`) for the part of
  the world on screen; the cloud layer downloads whole-planet cloud pictures
  from EUMETSAT (`view.eumetsat.int`); the aurora layer downloads NOAA's
  forecast (`services.swpc.noaa.gov`).
- **Planets up close** — looking closely at Mercury, Venus, the Earth or
  Mars downloads map tiles of the part on screen from NASA (`trek.nasa.gov`,
  and for the Earth `gibs.earthdata.nasa.gov`).
- **The Sun and the solar wind** — the Sun's space weather and the solar
  wind come from NOAA's Space Weather Prediction Center
  (`services.swpc.noaa.gov`), and pictures of the Sun from NASA's Solar
  Dynamics Observatory (`sdo.gsfc.nasa.gov`).
- **Deep Space Network** — which antennas are talking to which spacecraft
  comes from NASA/JPL's DSN Now (`eyes.nasa.gov`).
- **Photographs on cards** — the photograph on an object's card is
  downloaded from Wikimedia Commons (`upload.wikimedia.org`,
  `thumb.wikimedia.org`). The request
  says which picture was asked for.
- **Internet radio** — when you play a station, your device connects
  directly to that station's own streaming server, which is operated by the
  broadcaster and not by the developer. About a third of stations stream
  over plain, unencrypted http; this is the only unencrypted traffic the app
  makes. The app does not contact the Radio Browser directory itself - the
  station list reaches it through the developer's data files above.

The developer does not receive or log any of this traffic.

## Permissions

- **Internet** — required to download the data above and to play radio
  streams.
- **Approximate location** — asked for only when you open the sky view, and
  used only to put the stars over your own horizon. The app asks the system
  for approximate location only. It is used on the device, is not stored,
  and is not sent anywhere. You can decline; the sky view then says it
  cannot place the stars and the rest of the app works as before.
- **Camera** — used only in the sky view, to show the constellations over
  what the camera sees. You can decline, or switch the camera picture off
  in the sky view, and the sky is then drawn on black. The
  picture is shown on the screen and nothing else is done with it: it is not
  recorded, saved or sent anywhere. The app does not use the microphone.
- **Background audio and its notification** — keep a radio station playing,
  with a notification to stop it, when the screen is off or another app is
  in front.

## Purchases

The app is free to download. For seven days everything in it is open; after
that the globe and the internet radio stay free, and the rest can be
unlocked by a one-time in-app purchase. On iOS the free week is started by
taking a free "7-day Trial" item in the App Store.

Purchases, and restoring them on a new device, are handled entirely by
Google Play or the App Store under their own privacy policies. The app only
learns from the store whether the full version (or the trial) is owned, and
remembers that on the device. The developer receives no payment details and
no information about who bought what.

## Children

The app is a general-audience educational app. It is not directed at
children and collects no data from anyone, of any age.

## Changes

If this policy changes, the updated version will be posted at this URL with
a new "last updated" date.

## Contact

Questions about this policy: **info@kruen.cz**, or by post to Kruen s.r.o.,
K Hajku 1714, 509 01 Nova Paka, Czech Republic.

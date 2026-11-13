# NOIRVALE — The Residents' App

A concept app for a fictional luxury villa development on a forested ridge above Lake Vale, in the Kumaon hills. It opens like a landing page and works like an app.

## Opening

The loader draws the villa's bronze elevation as the site loads, with an odometer and construction-stage captions. Then the windows light, the camera pushes into the glass and the double pivot doors swing open onto a five-chapter scroll film, drawn on a canvas at full 1280×720 frame quality:

1. **Approach** — a drone descends through dusk fog towards the villa on the ridge
2. **Threshold** — through a 4.2 m bronze pivot door into a double-height travertine hall
3. **The edge** — along the deck to a 7.2 m cantilevered infinity pool
4. **The drawing** — the elevation draws itself in construction order and the real house develops behind it
5. **Nightfall** — the camera pulls back across the lake under the Milky Way

## The app

- **App shell:** a side rail on desktop and a frosted bottom tab bar on phones (Home, Residences, Estate, Location, Viewings), with a sliding indicator and a badge for upcoming viewings. The app bar shows the live Lake Vale time and light (golden hour, blue hour), worked out from the site's coordinates.
- **Home widgets:** your next viewing with a live countdown, the twelve plots and which houses are still dark, today's sunrise, golden hour and sunset, and shortcuts.
- **Residences:** ground and upper floor plans with rooms to explore, and a live site map of all twelve plots. Each open plot can be booked directly.
- **Estate:** count-up figures, a slider that lifts the night camera over the lake, and the four seasons.
- **Location:** pick a destination and its route draws on the map with the travel time.
- **My viewings:** book through a three-step sheet (house and plot, date and arrival time, your details). Upcoming viewings show a live countdown and can be rescheduled, copied, given directions, or cancelled with undo. Past and cancelled viewings are kept too. Everything is saved on the device.

## How the frames load

Each clip's 192 frames ship as four interleaved bundles in `pack/` (every 4th frame per bundle), indexed by `pack/manifest.json`. The bytes are the original WebP frames, untouched. The app opens once the first chapter's sparse pass has arrived, and the remaining bundles stream in the order you'll scroll to them.

## Run locally

Serve the folder over HTTP (the app fetches its own files):

```
python3 -m http.server 8000
```

Then open http://localhost:8000.

---

Concept app. NOIRVALE, its residences, plots and prices are fictional, and bookings are never sent anywhere. Design and build by Arqora.

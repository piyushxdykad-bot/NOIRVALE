# NOIRVALE — Private Hillside Villas

A concept website for a fictional luxury villa development on a forested ridge above Lake Vale, in the Kumaon hills.

The home page is a five-chapter scroll film, drawn on a canvas at full 1280×720 frame quality:

1. **Approach** — a drone descends through dusk fog towards the villa on the ridge
2. **Threshold** — through a 4.2 m bronze pivot door into a double-height travertine hall
3. **The edge** — along the deck to a 7.2 m cantilevered infinity pool
4. **The drawing** — a bronze elevation draws itself in construction order, the windows light, and the real house develops behind it
5. **Nightfall** — the camera pulls back across the lake under the Milky Way

Further pages: Residences (interactive floor plans), The estate (scrub the camera rising over the lake), Location (map) and Private viewing (calendar booking).

## The app version

`/app` is NOIRVALE as a residents' app that still opens like a landing page: the same loader and scroll film, then an app shell with a side rail (bottom tab bar on phones), a live Lake Vale clock with sunrise, golden hour and sunset worked out for the site's coordinates, and home widgets.

Its core feature is **My viewings**: book a walk through a three-step sheet (house and plot, date and arrival time, your details), then see it under Upcoming with a live countdown. Reschedule it, copy the details, get directions, or cancel it with undo. Bookings are kept on the device in localStorage.

## How the frames load

Each clip's 192 frames ship as four interleaved bundles in `pack/` (every 4th frame per bundle), indexed by `pack/manifest.json`. The bytes are the original WebP frames, untouched. The page opens once the first chapter's sparse pass has arrived, and the remaining bundles stream in the order you'll scroll to them.

## Run locally

Serve the folder over HTTP (the page fetches its own files):

```
python3 -m http.server 8000
```

Then open http://localhost:8000.

---

Concept website. NOIRVALE, its residences and prices are fictional. Design and build by Arqora.

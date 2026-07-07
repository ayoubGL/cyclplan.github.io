# Bergen Road Cycling Route Platform

An interactive road cycling route planner built for performance-oriented cyclists in Bergen, Norway.

The platform provides curated round-trip cycling routes starting and ending from **Rådalslien 117, Rådal/Fana**, with distance options from **20 km to 100 km**, live training estimations, heart-rate and power zone guidance, GPX export, and Google Maps integration.

## Features

### Curated Bergen/Fana Route Library

The app includes fixed round-trip routes:

* 20 km
* 30 km
* 40 km
* 50 km
* 60 km
* 70 km
* 80 km
* 90 km
* 100 km

Every route starts and finishes at:

```text
Rådalslien 117, 5239 Rådal, Bergen, Norway
```

Each route is structured with clear checkpoint labels:

```text
A → B → C → D → ... → A
```

The map only shows the letters **A, B, C, D...**, while the full searchable place names are listed under the map.

## Main Functionality

### Interactive Map

* Red route line for clear visibility
* Minimal map markers using only checkpoint letters
* Full route guideline displayed under the map
* Clickable checkpoint list with real Google Maps-searchable place names

### Route Guideline

Each active route includes:

* Start and finish point
* Checkpoint sequence
* Road guidance using real road/place names
* Scenic and tactical notes
* Distance and elevation summary

### GPX Export

Each route can be exported as a `.gpx` file and imported into:

* Garmin Connect
* Strava
* Komoot
* Wahoo
* Hammerhead Karoo
* Other cycling computers

### Open in Google Maps

The active route can be opened directly in Google Maps using the route’s checkpoint sequence.

## Training Tools

### Moving Time Estimator

The app includes sliders for:

* Average speed in km/h
* Optional target power in watts

The estimated moving time updates dynamically based on the selected route distance.

### Training Zone Decoder

The platform includes both power-based and heart-rate-based training zones.

You can adjust:

* FTP / estimated cycling power
* Max heart rate
* Resting heart rate

The app then calculates:

* Power range per zone
* Heart-rate range per zone
* Recommended effort for each route

Zones include:

* Z1 Recovery
* Z2 Easy
* Z2 Endurance
* Z3 Tempo
* Sweet Spot
* Threshold
* VO₂ / Anaerobic

This makes the platform useful even without a power meter.

## Smart Route Builder

The app also includes a dynamic route generation mode.

You can:

* Use your current GPS position
* Choose a manual start point
* Choose an end point
* Generate round-trip routes
* Select target distance
* Choose cycling profile
* Prefer road cycling, calm roads, scenic routes, or easier climbing

Supported cycling profiles include:

* Road bike / asphalt focus
* Regular cycling / bike-path focus
* E-bike friendly

## OpenRouteService API

Smart route generation uses OpenRouteService.

For personal use, paste your OpenRouteService API key into the app. The key is stored locally in your browser using local storage.

Do **not** hard-code your API key into the public GitHub repository.

Recommended production architecture:

```text
Frontend on GitHub Pages
        ↓
Small backend/proxy
        ↓
OpenRouteService API
```

Possible backend/proxy options:

* Vercel Functions
* Netlify Functions
* Cloudflare Workers
* Rust/Axum backend
* Node.js/Express backend

## How to Run Locally

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/bergen-cycling-routes.git
cd bergen-cycling-routes
```

Open the app:

```bash
open index.html
```

Or simply double-click `index.html`.

For best results, use a local server:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## How to Deploy with GitHub Pages

1. Rename the HTML file to:

```text
index.html
```

2. Push it to GitHub:

```bash
git init
git add index.html README.md
git commit -m "Initial cycling route platform"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/bergen-cycling-routes.git
git push -u origin main
```

3. Go to the GitHub repository.

4. Open:

```text
Settings → Pages
```

5. Set:

```text
Source: Deploy from a branch
Branch: main
Folder: /root
```

6. Save.

Your app will be available at:

```text
https://YOUR_USERNAME.github.io/bergen-cycling-routes/
```

## How to Use on Phone

Open the GitHub Pages link on your phone.

### iPhone

1. Open the site in Safari
2. Tap Share
3. Tap Add to Home Screen

### Android

1. Open the site in Chrome
2. Tap the three-dot menu
3. Tap Add to Home screen

The app will then behave almost like a mobile cycling route app.

## Recommended Workflow Before Riding

1. Select the target distance.
2. Check the A → B → C route guideline.
3. Review the elevation profile and steep sectors.
4. Check the recommended heart-rate zone.
5. Export GPX.
6. Import GPX into Garmin, Komoot, Strava, Wahoo, or your bike computer.
7. Validate the route before riding.

## Important Safety Note

The curated routes and generated routes are planning tools.

Before riding, always validate the GPX in a dedicated cycling navigation app such as Garmin Connect, Komoot, Strava, Ride with GPS, or Google Maps.

Road conditions, construction, ferry schedules, traffic patterns, and cycling restrictions can change.

## Current Limitations

* Some route geometries are planning-grade and should be validated before riding.
* Google Maps may adjust the route differently from the in-app route.
* OpenRouteService generated routes may not exactly match the requested target distance.
* Smart route generation depends on API availability and quota.
* Elevation and surface estimates should be treated as guidance, not absolute truth.

## Roadmap

Planned improvements:

* Save favorite generated routes
* Add route difficulty score
* Add wind direction and weather integration
* Add Garmin Connect export workflow
* Add Strava route export workflow
* Add climb segment cards
* Add ferry-aware routing
* Add surface quality scoring
* Add dark mode
* Add mobile-first PWA support
* Add offline GPX library

## Built For

This project is designed for a road cyclist training around Bergen/Fana who wants to prepare rides before clipping in:

* Endurance rides
* Z2 base rides
* Threshold climbing sessions
* Long weekend base-building rides
* Scenic road cycling loops
* Garmin-ready GPX planning

## License

Personal project. Add a license before making the repository public for reuse.

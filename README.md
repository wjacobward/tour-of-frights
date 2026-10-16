# Apex Tour of Frights route planner

A single-page planner for the Town of Apex's 2026 Tour of Frights (Oct 10–31, nightly 6–9 pm). Not affiliated with the Town of Apex.

My family loves the Tour of Frights every year, but planning routes can be tedious, even with the Google Maps links that the town provides. This tool lets you build custom routes starting from your location, remembering which houses you've already visited.

**Live:** https://wjacobward.github.io/tour-of-frights/

## Features

- All 38 houses from the town's Orange, Purple and Green routes, filterable by age rating (candy corn, pumpkin, ghost) and flashing lights
- One-tap buttons to follow a whole town route
- Opens your route in Google Maps, split into legs past 26 stops because the Maps app crashes on longer ones
- Everything is saved in your browser only; nothing is sent anywhere

## Development

Everything is in `index.html`: no build step and no dependencies to install. Open the file in a browser, or serve the folder:

```sh
python3 -m http.server
```

Leaflet is loaded from cdnjs, map tiles come from Esri, and fonts from Google Fonts. Pushing to `main` deploys to GitHub Pages.

### Updating the house list

House data is in the `HOUSES` array in `index.html`, taken from the town's flyer. Each entry gives the route, stop number, name, address, coordinates, rating, and a flash level: `0` none, `1` slow or low, `2` fast or intense. Bump `STORE_KEY` for a new year so old visited marks don't carry over.

`og-image.png` is the 1200×630 link-preview image.
